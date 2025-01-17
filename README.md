## 1-1) 사전과제 진행 가이드

- 아래 총 5 문제에 대한 해설을 작성한 뒤 Pull Request를 날려주세요.
- 문제 해설에 대한 정해진 양식은 없으며, 최대한 자세히 해설해주시면 좋습니다.
- 문제 유형은 해당 코스에서 다룰 주제들을 포함하고 있으니 완벽히 이해하시면 코스를 수강하는데 큰 도움이 될 것입니다.

**문의 사항은 사전 과제 Repository의 Issue로 등록해 주세요.*
  


## 1-2) 사전 과제

- (1) 동기와 비동기 프로그래밍에 대한 차이점을 설명해주세요.
- (2) 블로킹과 논블로킹의 차이점을 설명해주세요.
- (3) 본인이 주로 사용하는 언어에서 비동기 프로그래밍을 사용하는 방법을 설명해주세요.
- (4) 메세지 큐를 쓰는 이유에 대하여 2가지 예시를 서술해주세요.
- (5) 본인이 작성한 서버 코드가 있는 github repo 주소를 제출해주세요. (CRUD 기능을 모두 포함하여야 하며, 서버에 대한 설명을 README에 작성해주시면 더욱 좋습니다.) 
- (6 - Optional) 해당 수업을 통해 꼭 배우고 싶은 주제 또는 지식이 있다면 자유롭게 서술해주세요.



1) 동기와 비동기를 언급할때는 무엇과 무엇이(2개이상의 process)? 또한 시간에 관한언급이 있어야합니다. 
A,B스레드가 시작시간 또는 종료시간이 일치하면 동기라 할 수 있습니다. 
A가 실행한 메소드의 return 시각이랑 그 return 된 결과를 전달받고 B가 자신의 메소드를 실행한다면 이 또한 동기라 할 수 있습니다. 
비동기의 경우에는 return 시각이랑 B가 그 결과를 받고 실행하는 시각이 일치 하지 않는 경우입니다. 

2) 블로킹과 관련된이야기를 할때는 내가 직접 제어할 수 없는 대상과 연관이 있을때 나오게됩니다. 
어떤 IO작업을 하는 메소드를 호출했을때 해당 IO가 끝나서 return 할때까지 기다리면 블록킹 기다리지 않으면 논블록킹입니다.


3) String res = Executors.newCachedThreadPool().submit(() -> "hi").get();
해당 메소드에서 submit(()->"hi") 부분은 별도의 스레드에게 작업을 위임하고 submit메소드 리턴시간과 인자로 넘겨준 Callable의 실행결과를 받는 시간이 일치하지 않습니다.
이는 비동기적으로 진행된다는것을 알 수 있습니다.
.get() 부분은 메소드 리턴시간과 결과를 가져오는 시간이 일치합니다. (동기) 또한 저 get을 호출한 스레드가 대기하게됩니다. (블록킹)


4) kafka 가 대표적인데 msa에서 서로다른 ms에서 안정적으로 통신하고싶을 떄 사용하게 됩니다. 
여러 ms가 topic안에 들은 메시지를 지속적으로 소비하게 해줍니다.
distribute transaction을 구성할때 일종의 transaction log역할을 하기에 recovery 나 에러분석을 하기 용이합니다.

5) 

6) AWS에 관한 지식이 전무한데 이번 세미나를 통해서 열심히 배우고 싶습니다.
