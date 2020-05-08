출처: https://devlimk1.tistory.com/7?category=890636 [소소한 개발공간, 임경원의 보조기억장치]

★ 에러 발생 상황**

Visual Studio Code 에서 HTML 파일 결과를 브라우저에서 쉽게 확인할 수 있는 확장프로그램인 **Live Server**를 사용하여 실행시키는데



![img](https://k.kakaocdn.net/dn/bsOh6N/btqDhwAtWKg/5Pw1jMoDFjOt5aiRCeK651/img.png)Live Server 확장프로그램 실행방법(창에서 오른쪽 클릭 화면)



 ***127.0.0.1 에서 전송한 데이터가 없습니다. ERR_EMPTY_RESPONSE\*** 

***에러\*** 가 발생했다.

 

 

**♥ 에러 해결**

 

1) 127.0.0.1에서 전송한 데이터가 없다는 에러가 발생

 



![img](https://k.kakaocdn.net/dn/ZhNo9/btqDdH4XKxv/MLKKAK4XEBMf0ohZwcT8F0/img.png)



2) 빨간색 표시한 확장프로그램 클릭



![img](https://k.kakaocdn.net/dn/pIfUY/btqDgxUaFGw/eXh3QeHnbAfDBipufX6hAK/img.png)



3) 설치한 Live Server 톱니바퀴 클릭 후 Extension Settings 클릭



![img](https://k.kakaocdn.net/dn/drE6qB/btqDecwOsLX/OD5KR3EbTdkpgSk1eAZN00/img.png)



4)

명령 프롬프트(CMD) 창에서 ipconfig 입력 후

**IPv4 주소에 있는 나의 IP주소를** 

**Live Server -> Settings: Host** 입력창에 입력한다.



![img](https://k.kakaocdn.net/dn/xDhn4/btqDiaYf7Ns/sm0Pr9xNR8ldbsv6rEU7kk/img.png)

![img](https://k.kakaocdn.net/dn/cFfI2K/btqDibpkLt6/ol8mowkKfmkpEPZ97Kaux1/img.png)



5)다시 index.html 창에서 오른쪽 클릭 후 **Open with Live Server** 실행시키면

정상적으로 브라우저에 실행 결과가 나오는 것을 볼 수 있다.



![img](https://k.kakaocdn.net/dn/EO25Y/btqDibJDuPQ/GMHWzh4YJtOg4Pd5n6N1SK/img.png)

![img](https://k.kakaocdn.net/dn/dkObCQ/btqDgx0UuZ4/fSLvsF5kMYkbUDklOxiD01/img.png)



 

 

♥수정이 필요한 부분 , 지적해주실 부분은 댓글로 부탁드려요~ 피드백은 언제나 환영입니다♥

♥긴 글 읽어주셔서 감사합니다♥



