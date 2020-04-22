# [Error_Eclipse] Server Tomcat v9.0 Server at localhost failed to start 에러 해결방법 2가지!



> 나의 소소한 기록이 누군가에게는 도움이 되고, 그토록 원하던 답변일 수 있다.

####  

![img](https://k.kakaocdn.net/dn/8rvnn/btqDCartwQX/CD55j2Ek8eIkAKFjRNPz5k/img.png)

###  **에러(Error) 상황**



이클립스에서 서블릿 코드를 작성 후 톰캣을 실행하다보면

**Server Tomcat v9.0 Server at localhost failed to start.** 에러가 발생하는 경우가 종종 있다... 

어제는 분명 서버가 잘 실행되었고, 이후에 나는 잘못한게 없는데... 

아침에 다시 실행시켜보면 에러가 발생하는 당황스러운 이 상황...!

![img](https://k.kakaocdn.net/dn/bDeG5p/btqDA5YpukN/GQAaRBDO9RyfRrW1ZYaFE1/img.png)

![img](https://k.kakaocdn.net/dn/odAzZ/btqDFqzzUyJ/ieMjp0kT9e8eLZjhO2rZ20/img.png)



![img](https://k.kakaocdn.net/dn/sqA9k/btqDA6iNCcl/0VDLOcp380KRkQFNqDG73k/img.png)

### **시도해본 내용**

**1. 이클립스 종료 후 재실행**

**2. 아래 사진과 같이 해당 프로젝트 서버 Remove 후 코드 재실행**

![img](https://k.kakaocdn.net/dn/dkZtVu/btqDDZbGQJg/2t5TPfEDBuXGDwjNLReyKK/img.png)

![img](https://k.kakaocdn.net/dn/pCauS/btqDCbRnBPe/z1XS5psfYKMiuF08pRcpG0/img.png)

### **알아낸 오류 원인**

구글링하였더니**, 2가지의 오류 해결방법**을 알게되었다.

**첫번째 원인은** xml 파일 설정과 어노테이션(@WebServlet) url 맵핑이 겹치면서 에러가 발생

**두번째 원인은** 원인이라기보다는 톰캣 실행 경로에서 발생하는 충돌에러로 판단되어 해당 프로젝트 톰캣 서버 삭제 후 실행환경을 재구축 



![img](https://k.kakaocdn.net/dn/ursl1/btqDCakNSJC/MjB6R8JWAcPAheRSSKYAKK/img.png)

###  **해결방법**

***☞*** **첫번째 원인(xml 파일 설정과 어노테이션(@WebServlet) url 맵핑이 겹치면서 에러가 발생)**

![img](https://k.kakaocdn.net/dn/chKz9H/btqDEGJIh7f/2ick2Mg6oLDCZaTgKrC330/img.png)

>  ***\**\*metadata-complete="false" 설정 후 코드 실행하면 web.xml 파일과 index.java에 있는 url 맵핑을 둘 다 참조하게되어 index.java 파일의 @WebServlet("/hello") 와 web.xml파일에서 servlet-mapping의 url-pattern 과 충돌이 발생하게 되어 에러를 발생시킨다.\*\**\***

![img](https://k.kakaocdn.net/dn/brxRYi/btqDCbcQkMu/WQkU0Z1jBCgL9ixx3N28sK/img.png)

> ***\**\*\*\*index.java 의 @WebServlet("/hello") 를 주석처리하고 web.xml의 metadata-complet="true" 로 변경하면 web.xml의 servlet-mapping만 참조하게 되어 충돌없이 정상적으로 실행되어진다.\*\*\*\*\****



****\**\*\*\*\*\*\*☞\*\*\*\*\*\*\**\*******\*두번째 원인(톰캣 실행 경로에서 발생하는 충돌에러로 판단)\****

**★이런 저런 다 시도해보고도 에러가 해결이 안된다면 아래의 방법으로 에러를 해결할 수 있을 것이다.**



![img](https://k.kakaocdn.net/dn/bquAq9/btqDBARsgbL/3njmAeZKhdKN7wDDIAEWkk/img.png)

**Window->Preferences 클릭**



![img](https://k.kakaocdn.net/dn/chYk7j/btqDFpHsTCG/koyMNmwWIcQx42AMssxVDk/img.png)

**Server탭 -> Runtime Environments -> 기존에 있는 톰캣 서버 Remove**



![img](https://k.kakaocdn.net/dn/dm9R9K/btqDDw8AqBH/tVDEmtSdylpDbFDDGKkJo1/img.png)

**OK 클릭!**



![img](https://k.kakaocdn.net/dn/bu7piz/btqDACoJOuK/rSPO3nN1ELwkXRQYMA8cyk/img.png)

**삭제 확인 후, 다시 Add -> 톰캣 버전 설정 후 Next**



![img](https://k.kakaocdn.net/dn/qybKQ/btqDAB4pVHm/jqy0i1LrwlgKmrwAUXGGs1/img.png)

**톰캣 설치한 디렉토리 설정 후 Finish**



![img](https://k.kakaocdn.net/dn/bfVQGc/btqDEGv8C10/TNy3gqTNz70QlQxGezYglk/img.png)

**기존에 실행했던 톰캣서버를 삭제했었으므로, 다시 재설정**



![img](https://k.kakaocdn.net/dn/baXYvb/btqDDv2W9SF/qPLHh1re8HHBhkdNX7xKD1/img.png)

**톰캣서버를 실행하고자 하는 프로젝트 Add**



![img](https://k.kakaocdn.net/dn/bo05kF/btqDA5YrwyZ/QaKTvoAERNrbeSLsMiB4kK/img.png)

**톰캣 서버 설정은 잘했으나, 위와같이 서블릿 관련 라이브러리를 import하지 못하는 에러 발생!**



![img](https://k.kakaocdn.net/dn/dLVoNq/btqDDYjwZBb/8XQ0uERrdgWJmKZPeX3mG0/img.png)

**확인해보니, 해당 프로젝트에 톰캣 라이브러리가 없음**



![img](https://k.kakaocdn.net/dn/bz7Prd/btqDEZhYlsZ/vUk0tAQh5SoXo2LbIEXFok/img.png)

**해당 프로젝트 오른쪽 마우스 클릭 -> Build Path-> Configure Build Path 클릭**



![img](https://k.kakaocdn.net/dn/K63jf/btqDDvBRRVV/nqa6Bi9QcAD5f4F6M5ArI1/img.png)

**위의 실행번호에 맞게 클릭**



![img](https://k.kakaocdn.net/dn/bEEXhF/btqDCZiUqhR/BVCennbIpn4BgTbdnTsfL1/img.png)

**Server Runtime 클릭 후 Next**



![img](https://k.kakaocdn.net/dn/cX54Su/btqDEFRAhSe/NPQAve0VbUFLRtqOknXEpk/img.png)

**톰캣 클릭 후 Finish**



![img](https://k.kakaocdn.net/dn/AqIzE/btqDCZQKgiq/yCOqbFfWvO0M1kpWOH1Tzk/img.png)

**라이브러리에 추가된 톰캣 확인 후 Apply and close**



![img](https://k.kakaocdn.net/dn/bBL2Y0/btqDDXx45qW/JnFhEPQVvnPPMwxpqChFI1/img.png)

**위에서 없었던 Libraries에 톰캣라이브러리가 설정되었고, 에러도 없어짐을 확인!**



![img](https://k.kakaocdn.net/dn/bFa53m/btqDEZI3qfG/7iIMnt9jRRwbJhpJCkjfkk/img.png)

**코드 실행하면 결과가 브라우저에서 잘 출력됨을 확인할 수 있다!**



> ♥ 수정이 필요한 부분 , 지적해주실 부분은 댓글로 부탁드려요~ 피드백은 언제나 환영입니다 ♥
> ♥ 긴 글 읽어주셔서 감사합니다 ♥