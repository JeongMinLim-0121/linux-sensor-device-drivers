# 🔐 **linux-sensor-device-drivers**
>  사용자 애플리케이션과 커널 디바이스 드라이버를 연동해 센서 수집·디스플레이 출력·시간 제어를 수행하는 Linux 임베디드 제어 시스템

---
## 📌 1. 프로젝트 목표

- Linux 커널 모듈 기반으로 센서·디스플레이·RTC 장치 제어 드라이버 구현
- GPIO / I2C 기반 하드웨어 제어 흐름 이해 및 커널–유저 공간 연동
- 드라이버 로딩·해제, 장치 제어 인터페이스 설계 경험 확보

---
## 🎬 2. 시연 영상

https://github.com/user-attachments/assets/cf1690ff-f7f9-4f45-9d17-bac4cddd5973

---
## 🧠 3. 전자 회로도
> STM32 MCU를 중심으로 센서(DHT11), OLED, RTC 모듈이 연결된 하드웨어 구성
<img width="1362" height="733" alt="전기 회로도" src="https://github.com/user-attachments/assets/ba7d6524-b904-46c0-93a3-5b1c211bc0f9" />

 ---
## 🔧 4. 핵심 기능
 
### ⚙️ RTC Control Driver
- 커널 모듈을 통한 RTC 레지스터 제어
- 시간 설정 / 조회 기능 구현

### 🚦DHT11 Driver
- GPIO 기반 온·습도 데이터 수집
- 커널 타이밍 제어 및 데이터 파싱 로직 구현
  
### 🖥 OLED Driver
- I2C 통신 기반 텍스트 출력
- 사용자 입력에 따른 화면 제어 인터페이스 제공
  
---
 ## 🧩 기술 요약
 
- Language: C
- OS: Linux
- Kernel Module / Device Driver
- Interface: GPIO, I2C
 


