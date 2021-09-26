# 라즈베리파이 Mosquitto MQTT 실행 방법

 

## 1. MQTT Broker 설치

```
sudo apt install mosquitto mosquitto-clients
```
프로그램 서명키, 패키지 등록 절차 없이 위의 명령을 입력하면 설치된다.

한방에 브로커와 클라이언트 모두 설치됨.

## 2. MQTT Broker 활성화 및 동작상태 확인

1) 활성화하기

```
sudo systemctl enable mosquitto
```

2) 동작상태 확인하기

```
sudo systemctl status mosquitto
```
![11](https://user-images.githubusercontent.com/56014938/134810898-160b9fb6-90ab-44e3-894c-b055b5175a82.png)

## 3. Publish&Subscribe
 
MQTT에는 크게 두가지 기능이 있다. 바로 Publish(발행), Subscribe(구독) 이다. 간단히 말해서 메세지 송,수신으로 생각하면 된다.

우선 Publish를 알아보자

```
mosquitto_pub -h 'IP주소' -t 'topic' -m 'message'
```
IP주소 : 정확히는 호스트 주소를 의미한다. 기본 값을 127.0.0.1로 한다.

topic : 토픽 즉 주제를 의미한다. 이 주제를 선택한 대상들만 동일 메세지를 주고받을 수 있다. 게임 채널과 비교해 생각하면 이해가 쉽다. 

message : 메세지 말 그대로 주고받을 메세지 내용을 작성하면 된다.

위 세가지 모두 작성하여 발행하면 Publish는 끝난다.

다만 발송했는데로 아무런 결과가 나오지 않는다. 뭐가 잘못된 것일까?

잘못되지 않았다. 이건 단순히 보내는 것이지 받는 것이 아니다.

그럼 메세지를 받으려면 어떻게 해야할까? 바로 Subscribe이다

Subscribe는 아래 명령어를 작성하면 실행 할 수 있다.

```
mosquitto_sub -h 'IP주소' -t 'topic'
```

IP주소와 topic은 Publish와 동일하게 작성하면 된다.

아래 사진은 실행 결과이다

1. Publish

![111](https://user-images.githubusercontent.com/56014938/134811373-30342fc9-012c-4d8e-8f2b-fd7b8193dd13.png)

2. Subscribe

![222](https://user-images.githubusercontent.com/56014938/134811380-f70a7a95-19b0-4c8b-b2fa-45c8daacbad0.png)


