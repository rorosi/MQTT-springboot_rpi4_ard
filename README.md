# 라즈베리파이 Mosquitto MQTT 실행 방법

 

## 1. MQTT Broker 설치

...
  sudo apt install mosquitto mosquitto-clients
...
프로그램 서명키, 패키지 등록 절차 없이 위의 명령을 입력하면 설치된다.

한방에 브로커와 클라이언트 모두 설치됨.

## 2. MQTT Broker 활성화 및 동작상태 확인

1) 활성화하기

...
  sudo systemctl enable mosquitto
...

2) 동작상태 확인하기

...
  sudo systemctl status mosquitto
...
