# 미니 블랙박스 구현 (AWS, Arduino)

![arduino_run](https://user-images.githubusercontent.com/56067179/104873250-6e44cf80-5993-11eb-9951-de6ab21cbece.gif)


## Structure

<img src = "https://user-images.githubusercontent.com/56067179/104874295-ef04cb00-5995-11eb-94fa-f6fa496ca107.png" width = "600px">


## Tutorial

- 아두이노 보드, 초음파 거리 센서, LED 3개와 피에조 부저를 준비합니다.
- 아두이노 보드를 다음과 같은 핀 번호로 구성합니다.
  - #define ECHO 3
  - #define TRIG 2
  - #define LED_RED 6
  - #define LED_YELLOW 7
  - #define LED_GREEN 8
  - #define SPEAKER 5
  
- arduinio_secrets.h 파일을 알맞게 구성합니다.
  - SECRET_SSID : 와이파이 이름
  - SECRET_PASS : 와이파이 비밀 번호
  - SECRET_BROKER : 'AWS > 서비스 > IoT Core > 설정'의 엔드포인트
  - SECRET_CERTIFICATE : 'AWS > 서비스 > IAM > 사용자'의 certificate.pem 파일 참조
  
- 측정된 거리값에 따라 LED와 피에조 부저가 제어됩니다.
  - 거리 20cm 초과 : 초록색 LED
  - 거리 20cm 이하 : 노란색 LED + 낮고 느린 효과음
  - 거리 10cm 이하 : 빨간색 LED + 높고 빠른 효과음
