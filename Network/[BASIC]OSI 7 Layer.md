## OSI 7 계층을 왜 만들었을까
---
일단 **OSI 7 계층**은 네트워크에서 **통신**이 일어나는 과정을 7단계로 나눈 것이라고 한다.
그렇다면 왜 굳이 계층을 나누었을까?
>그 이유는 흐름을 한눈에 알아보기 쉽고, 통신에 문제가 생겨도
다른 부분은 건들지 않고 7단계 중 문제가 생긴 부분만 손 보면 되기 때문이다.

이해하기 쉽도록 예를 들어보자.
```
PC방에서 카트라이더를 하다가 마지막 바퀴에 연결이 끊겼다.

이때 나를 포함한 주위 모든 사람들이 각자 하고있는 게임이 튕겼다면
PC방 네트워크가 문제이니 그 게층만 고치면 문제가 해결된다.

그런데 나 혼자만 연결이 끊겼다면
그건 본체에 랜선이 빠졌다거나, 소프트웨어끼리 충돌로 인해 그랬을 가능성이 높으니,
그 계층만 손보면 문제가 해결된다.
```
위와 같이 문제가 생겼을 때 7가지 계층 중 문제가 생긴 부분만 고칠 수 있도록 나눈 것이 **OSI 7 계층이다.**
(만약 계층을 나누지 않았다면 오류가 발생했을 때 대참사가 발생할 수도 있다..)
![](https://velog.velcdn.com/images/rkadl9999/post/a2b8b0a1-88df-44eb-b4af-ca6eb708866a/image.png)
위 사진에 보이듯 OSI 7 계층은 저렇게 나뉘어져 있다.
저렇게만 보면 뭐가 뭔지 모르니, 좀 더 자세히 알아보자.
### 물리 계층
---
- 7계층 중 가장 하위 계층 ( =  1계층 )
- 문자 그대로 전기적, 기계적인 계층
- 전송 단위 : 0과 1로 이루어진 비트

우리 주변에서 흔히 볼 수 있는 랜선 ( 인터넷 케이블 )이 물리 계층에 속한다.
( 케이블, 리피터, 허브 등의 장비가 물리 계층에 포함 )
<br>
### 데이터 링크 계층
---
- 7계층 중 2계층에 속함
- 두개의 직접 연결된 노드 간 데이터 전송 제공
- 물리 계층에서 일어난 오류 수정
- 전송 단위 : Frame

스위치라는 장비가 데이터 링크 계층에 속한다.
( 제대로 이해가 안된다, 싶으면 스위치가 어떤 역할을 하는지 찾아보면 좋을 거 같다.. )
<br>
### 네트워크 계층
---
- 7계층 중 3계층에 속한다.
- 전송 단위 : packet ( 패킷 )
- 패킷을 전달하는 역할을 한다.

네트워크 계층이 내가 생각했을 때는 가장 핵심같다.
라우터라는 네트워크 장비가 네트워크 계층에 속한다.
이것만으론 정리가 안될 수 있으니 아래 예시를 한번 보자 🙃
>광주광역시에서 미국 캘리포니아에 있는 서버에 접속한다고 가정했을 때,
연결 할 수 있는 경로는 매우 많다. ( Ex. 집에 갈때 지하철을 타고 버스로 환승을 한다. )
하지만 우리는 항상 가장 효율적인 경로를 원한다.
수 많은 경로 중에 효율적인 경로를 찾을 수 있도록 도와주는 장비가 라우터이다.

네트워크 계층은 위와 같은 역할을 한다.
<br>
### 전송 계층
---
- 7계층 중 4계층에 속함
- 전송할 데이터의 용량과 속도, 목적지 등을 처리
- TCP / UDP 사용

우리가 잘 알고 있는 IP 주소가 전송 계층에 해당한다.
TCP / UDP는 전송 프로토콜인데 꼭 한번 공부해보는 걸 추천합니다. 👍
<br>
### 세션 계층
---
- 7계층 중 5계층에 속함
- 통신하는 두 기기들 사이의 "대화"를 제어 및 동기화
- 세션를 생성 및 종료

말 그대로 세션을 담당하는 계층이다.
백엔드 쪽을 공부했다면 바로 어떤 일을 하는 계층인지 알 수 있을거다.
모르는 사람은 **쿠키와 세션**에 대해서 한번 알아보는 것도 좋을 거 같습니다. 🙃
<br>
### 표현 계층
---
- 7계층 중 6계층에 속함
- 데이터의 인코딩 / 디코딩, 압축 / 해제 담당
- 암호화, 복호화도 이 계층에서 담당한다.

데이터를 전송할 때 중간에 누가 훔쳐보거나 가로채도 안전하도록
데이터를 암호화, 복호화 시키는 과정을 표현 계층에서 담당한다.
**_( 여자친구랑 카톡할 때 누가 옆에서 보는걸 막기 위해 가리는 것과 비슷하다.)_**
<br>
### 응용 계층
---
- 7계층 중 가장 상위 게층 (= 7계층)
- 사용자에게 보이는 부분이다. ( 가장 가까운 계층 )
- 응용 프로그램들이 이 계층에 속한다.

>예를 들어보면,
구글 크롬, 카트라이더, 파이어 폭스, 파워포인트, 워드 등
모든 응용프로그램이 이 계층에 속하게 된다. 😀

<br></br>
OSI 7계층은 자격증, 네트워크 기초 등 많은 곳에서 나오는 부분이기 때문에
각 계층의 이름 정도라도 알아두는게 좋다. 😎

