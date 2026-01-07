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
 ## 🛠 5. 구현 상세

- 일부 장치에서는 커널 영역에서의 신호 타이밍이 동작 성공 여부에 직접적인 영향을 미쳐,
  GPIO Bit-Banging 방식으로 통신 프로토콜을 직접 구현함
- 마이크로초 단위 지연(`udelay`)과 인터럽트 제어를 활용해
  타이밍 민감 구간을 안정적으로 처리
- Character Device 기반 인터페이스를 통해
  사용자 애플리케이션이 `read/write` 시스템 콜로 커널 드라이버에 접근하도록 구성
- 인터럽트 기반 입력 처리 과정에서 `jiffies`를 활용한 시간 비교 로직을 적용해
  기계식 스위치 입력으로 인한 채터링 현상을 드라이버 레벨에서 필터링
  
---
 ## 🧩 6. 기술 요약
 
- Language: C
- OS: Linux
- Kernel Module / Device Driver
- Interface: GPIO, I2C
 


