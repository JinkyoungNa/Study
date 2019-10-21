# Thread
> Process 내에 _순차적으로 실행되는 실행 흐름_ 의 최소 단위
> ##### Refs
> * [안드로이드 스레드(Android Thread)](https://recipes4dev.tistory.com/143)
> * [안드로이드 백그라운드 잘 다루기 Thread, Looper, Handler](https://academy.realm.io/kr/posts/android-thread-looper-handler/)
> * [Thread 와 Android Main Thread](http://cafe.daum.net/_c21_/bbs_search_read?grpid=1MWA2&fldid=aAfL&datanum=98&docid=1MWA2%7CaAfL%7C98%7C20110704111711)
> * [안드로이드 앱 프로세스 분리하기](https://brunch.co.kr/@huewu/4)

![Process](../‎⁨img/img_process.png)

#### Program
명령과 데이터로 구성되어 저장 장치(Storage Device)에 저장된 형태의 실행코드

#### Process
현재 메모리에 로딩되고 실행 중인 프로그램, 운영체제에 의해 메모리에 적재되어 실행 중인 프로그램

안드로이드의 애플리케이션을 실행하면 시스템은 메인 액티비티를 메모리로 올려 프로세스로 만들며, 이 때 메인 스레드(==UI Thread)가 자동으로 생성됩니다.

#### Thread Create
  1. **extends Thread**
    * Thread Class 확장
    * Task 세부 기능 수정 가능
    * 오버 헤드 발생 가능
  2. **implements Runnable**
    * runnable 인터페이스만 구현할 경우 간결하게 구현 가능
    * 논리적으로 분리된 Task 설계 가능

#### ActivityThread (MainThread)
사용자가 입력할 이벤트 처리, 화면 GUI 그리기 /
_순차처리가 중요하므로 꼭 동일한 쓰레드에서 처리_

  ![MainThread](../img/img_andoid_mainthread.png)

  **처리 순서**
  * System Event Message 전달
  * Handler가 MessageQueue에 전달
  * Looper가 MessageQueue에 Message가 있는지 확인
  * 순차적으로 (FIFO) 처리한 Message를 Handler에 전달
  * Handler가 Message 처리

Main(UI) Thread에서 시간이 걸리는 작업을 실행한다면, Application의 반응성은 낮아지고, ANR(Android Not Responding) 상태로 전환 될 수도 있다. 따라서 작업을 여러 Thread로 분리하고 Thread간에 통신 하는 방법이 필요하게 되었다.



* 멀티
* 통신
* 스케쥴링
* 동기화
* 성능 튜닝
* 메모리 관리
