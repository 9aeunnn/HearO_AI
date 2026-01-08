# 🧠 hearO – UrbanSound8K 상업용 서브셋 기반 소리 인식 AI

청각장애인을 위한 실시간 소리 감지 프로젝트
UrbanSound8K 데이터셋 중 상업적 사용이 가능한(CC0, CC BY) 클립만 자동 필터링하여
자동차 경적(car_horn)과 사이렌(siren) 등 주요 도시 소리를 분류합니다.



## 📂 프로젝트 구조

---

```bash
hearO_AI/
├─ configs/
│  └─ config.yaml                # 학습 설정
├─ data/
│  └─ US8K_commercial_subset/    # CC0/CC BY subset
│     ├─ audio/fold1~fold10/
│     ├─ filtered_metadata.csv
│     ├─ licenses.csv
│     └─ summary.txt
├─ outputs/
│  ├─ best_fold1.pt ~ best_fold10.pt
│  ├─ kfold_report.txt
│  └─ kfold_boxplot.png
├─ src/
│  ├─ datasets/us8k.py           # UrbanSound8K 데이터 로더
│  ├─ models/cnn_small.py        # 경량 CNN 모델
│  ├─ train_kfold.py             # 10-Fold 교차검증 학습 스크립트
│  ├─ infer_file.py              # 단일 오디오 파일 추론 스크립트
│  └─ utils/...                  # metrics, augmentation 등
└─ requirements.txt

```
## ⚙️ 환경 설정

----

```bash
# 1️⃣ 가상환경 생성
python -m venv .venv
.\.venv\Scripts\activate

# 2️⃣ 라이브러리 설치
pip install -r requirements.txt
```
>GPU 사용 시, CUDA 지원 PyTorch 설치:
>```bash
>pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121
>```

## 🔊 데이터 준비

---
UrbanSound8K 전체를 다운받지 않고도 soundata 패키지를 이용해 자동 다운로드할 수 있습니다:

```bash
pip install soundata
python - << "PY"
import soundata
ds = soundata.initialize("urbansound8k")
ds.download()  # C:\Users\<username>\sound_datasets\UrbanSound8K 에 저장
PY
```
이후, 상업 사용 가능한 subset만 필터링:
```bash
python filter_urbansound8k_commercial.py `
  --urbansound_root "C:\Users\<username>\sound_datasets\UrbanSound8K" `
  --out_dir "./data/US8K_commercial_subset" `
  --include_classes "car_horn,siren" `
  --copy_audio
```

## 🧩 모델 학습

---
10-fold 교차검증을 수행합니다:
```bash
python -m src.train_kfold
```

결과물:

+ outputs/kfold_report.txt → 평균 정확도 및 표준편차

+ outputs/kfold_boxplot.png → fold별 성능 분포

+ outputs/best_fold*.pt → 각 fold별 최적 모델 가중치


예시 결과:
```bash
10-Fold ACC mean=0.9782, std=0.0156
Per-fold: [0.973, 0.981, 0.986, ...]
```

## 🔍 단일 오디오 추론

---
```bash
python -m src.infer_file --wav "data/test_samples/siren_test.wav"
```

출력 예시:
```bash
🎧 File: siren_test.wav
  car_horn      : 2.31%
  siren         : 97.69%

✅ Predicted: SIREN (model: best_fold1.pt)
```

## 📈 결과 예시

---
| 항목      | 내용                                     |
| ------- | -------------------------------------- |
| Dataset | UrbanSound8K (CC0 / CC BY subset only) |
| Classes | car_horn, siren                        |
| Model   | CNN_Small (3 conv + FC + dropout 0.25) |
| Input   | 64 Mel-bands, 16 kHz                   |
| Metric  | 10-Fold Accuracy                       |
| Result  | 97.8 ± 1.6 %                           |

![kfold_boxplot](https://github.com/hearO-org/hearO_AI/blob/sound-alert/kfold_boxplot.png?raw=true)

## 🧠 향후 계획

---
+  더 많은 클래스 (dog_bark, engine_idling, drilling 등) 확장
+ 실시간 Streamlit 데모 (마이크 입력 기반 예측)
+ Edge 환경에서 동작하는 ONNX 변환
+ Baby_cry 포함 멀티클래스 감정음 감지

## 🔐 라이선스 및 데이터 사용 고지

---
+ 본 프로젝트는 UrbanSound8K 데이터셋을 사용합니다.

+ filter_urbansound8k_commercial.py 스크립트를 통해
**상업적 사용이 허가된** (CC0, CC BY) 오디오만 포함합니다.

+ 데이터 출처:
https://urbansounddataset.weebly.com/urbansound8k.html


## 🌟 Citation

---
```yaml
@dataset{urbansound8k,
  author = {Justin Salamon, Christopher Jacoby, Juan Pablo Bello},
  title = {UrbanSound8K: A Dataset of Urban Sound Recordings},
  year = {2014},
  publisher = {Zenodo},
  doi = {10.5281/zenodo.1203745}
}
```
