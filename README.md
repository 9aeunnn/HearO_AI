
<p align="center">
  <img src="https://github.com/user-attachments/assets/ed5fe001-abc7-4786-af78-b367948183f8" width="100%" alt="banner"/>
</p>

<h1 align="center">AI 기반 청각 접근성 플랫폼, HearO (히어로) </h1>

**HearO**는 청각장애인과 비장애인의 소통 격차를 해소하기 위해 탄생한 **AI 기반 청각 접근성 플랫폼**입니다.  
AI 소리 인식, 생활 소리 인식, 수어 사전, 커뮤니티, 정보서치 기능을 통해 모두가 소리를 '보고', 대화를 '이어갈 수 있는' 세상을 만듭니다.

<br>

## 🌱 로고 의미

<table border="0" cellspacing="0" cellpadding="0">
  <tr>
    <td width="140" align="center" valign="middle">
      <img src="https://github.com/user-attachments/assets/9e9a06d4-ad56-4526-92f8-651c7eb76abb" 
           width="120" 
           alt="HearO logo"
           style="border:none; outline:none;" />
    </td>
    <td style="vertical-align: middle; padding-left: 15px;">
      <p>
        <b>HearO</b>는 <b>‘hear(듣다)’</b>와 <b>‘hero(영웅)’</b>의 합성어로,<br/>
        청각장애인에게 세상의 소리를 전하고, 그들의 일상 속 <b>영웅</b>이 되고자 하는 마음을 담고 있습니다.<br/><br/>
        또한 우리의 서비스가 그분들의 <b>귀가 되어</b> 세상을 들을 수 있게 돕고,<br/>
        나아가 HearO를 통해 스스로 성장하며 <b>그분들 자신이 영웅이 되는</b> 여정을 함께합니다.<br/><br/>
        HearO의 파란색은 <b>신뢰와 평온</b>을,  
        부드럽게 이어진 곡선은 <b>서로를 잇는 소통</b>을 상징합니다.
      </p>
    </td>
  </tr>
</table>


<br>

## ✨ 주요 기능

### 🔹 1. 수어 사전
- 국립국어원 수어 API 연동으로 단어, 영상, 설명을 제공  
- 즐겨찾기·학습 이력 기능을 통해 개인 맞춤형 학습 지원  

### 🔹 2. AI 생활 소리 인식
- 초인종, 경적, 경보 등 주요 소리를 인식하여  
  시각적·진동 알림으로 사용자에게 즉시 안내  

### 🔹 3. 커뮤니티 게시판 서비스
- 청각장애인, 수어 학습자, 일반인이 함께 참여  
- 수어 학습 후기·팁 공유 및 소통 중심 커뮤니티 운영  

### 🔹 4. 실시간 구인정보 제공
- 실시간으로 구인 정보를 확인하여 취업 연계 서비스를 제공
- 청각장애인의 생활 자립을 응원

### 🔹 5. 접근성 중심 UX
- 시각 알림·진동 패턴·고대비 모드 지원  
- 사용자 맞춤형 접근성 설정 기능 제공  

<br>

## 📱 UI

| 로그인 | 소리감지 | 수어사전 | 상세보기 | 구인정보 | 커뮤니티 |
| :---: | :---: | :---: | :---: | :---: | :---: |
| <img src="https://github.com/user-attachments/assets/6f01277b-3b88-47d2-a283-9824418e829f" width="360" height="864"> | <img src="https://github.com/user-attachments/assets/48c1dda7-f703-4a7c-ba7a-c35ccc9c8106" width="360" height="864"> | <img src="https://github.com/user-attachments/assets/b4f9c59e-f4fa-4c1a-8ceb-5252470bd734" width="360" height="864"> | <img src="https://github.com/user-attachments/assets/99da099d-99ba-414c-ba03-163a36b74521" width="360" height="864"> | <img src="https://github.com/user-attachments/assets/9e55481b-c1dd-468e-9744-c89db1e279e2" alt="job" width="360" height="864"> | <img src="https://github.com/user-attachments/assets/954b52db-5803-419c-9b8e-f60212341a2d" alt="community" width="360" height="864"> |

<br>

## 🎯 개발 목적
- 모두가 차별 없이 소통할 수 있는 **포용적 커뮤니케이션 플랫폼** 구축  
- **AI와 공공데이터를 활용한 사회문제 해결형 서비스** 실현  
- 청각장애인의 일상 속 불편함을 줄이고 **자립적 소통 환경 조성**

<br>

## 🛠️ 기술 스택
- **Backend**: Spring Boot, JPA, MySQL  
- **Frontend**: Android (Kotlin)
- **Infra/DevOps**: AWS EC2, GitHub Actions, Docker  
- **AI**: PyTorch, 2DCNN, Mel-Spectrogram, UrbanSound8K(CC0/CCBY)
- **API 연동**: KCISA 수어 사전 API, 공공데이터 기반 생활 소리 정보  

<br>

## 🤖 학습 모델
청각장애인을 위한 실시간 소리 감지 프로젝트 UrbanSound8K 데이터셋 중 상업적 사용이 가능한(CC0, CC BY) 클립만 자동 필터링하여 자동차 경적(car_horn)과 사이렌(siren) 등 주요 도시 소리를 분류합니다.
<br>
<img width="400" height="400" alt="AI모델 다이어그램" src="https://github.com/user-attachments/assets/4d889449-0b24-457c-ac78-53a1b6c9d658" />
<br>



## 🧱 서버 아키텍쳐
프로젝트 개발 후 추가 예정

<br>

## 🧑‍💻 팀원 소개

### AI
<table>
  <tr>
    <td align="center">
      <a href="https://github.com/9aeunnn">
        <img src="https://github.com/9aeunnn.png?size=140" width="100" height="100" alt="김가은"/>
        <br/>
        <sub><b>김가은</b></sub>
      </a>
    </td>
  </tr>
</table>

---

### Backend
<table>
  <tr>
    <td align="center">
      <a href="https://github.com/kwonyuujin">
        <img src="https://github.com/kwonyuujin.png?size=140" width="100" height="100" alt="권유진"/>
        <br/>
        <sub><b>권유진</b></sub>
      </a>
    </td>
    <td align="center">
      <a href="https://github.com/leasenose">
        <img src="https://github.com/leasenose.png?size=140" width="100" height="100" alt="권유진"/>
        <br/>
        <sub><b>김재민</b></sub>
      </a>
    </td>
  </tr>
</table>

---

### Frontend
<table>
  <tr>
    <td align="center">
      <a href="https://github.com/Hyobee02">
        <img src="https://github.com/Hyobee02.png?size=140" width="100" height="100" alt="권유진"/>
        <br/>
        <sub><b>최효비</b></sub>
      </a>
    </td>
  </tr>
</table>

<br>

## 🌈 Contribution

HearO는 **AI 기술로 모두의 접근성을 높이는 사회적 가치 프로젝트**입니다.  
기여를 원하신다면 [컨벤션 가이드](#)를 참고해주세요.  
문의나 제안은 언제든 환영합니다! 💬
