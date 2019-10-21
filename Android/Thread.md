# Thread
> Process 내에 _순차적으로 실행되는 실행 흐름_ 의 최소 단위
> ##### Refs
> * [안드로이드 앱 프로세스 분리하기](https://brunch.co.kr/@huewu/4)
> * [안드로이드 백그라운드 잘 다루기 Thread, Looper, Handler](https://academy.realm.io/kr/posts/android-thread-looper-handler/)
> * [안드로이드 스레드(Android Thread)](https://recipes4dev.tistory.com/143)

##### Program
명령과 데이터로 구성되어 저장 장치(Storage Device)에 저장된 형태의 실행코드

##### Process
현재 메모리에 로딩되고 실행 중인 프로그램, 운영체제에 의해 메모리에 적재되어 실행 중인 프로그램

![Process](../‎⁨img/img_process.png)

###### Thread Create
1. extends Thread
  다중 상속 불가, run()를 구현을 강제화 할 수 없음
2. implements Runnable


* 멀티
* 통신
* 스케쥴링
* 동기화
* 성능 튜닝
* 메모리 관리
