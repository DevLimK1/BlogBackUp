# [Eclipse] Ctrl+Space는 그만! 글자 입력하기만하면 Content Assist(자동완성기능)가 실행되는 방법!

**eclipse가 아닌 intellij를 사용해본 사람이라면 글자를 입력하기만해도 메소드나 어노테이션 등의 자동완성기능이 실행되어 일일이 Ctrl+Space를 눌러서 자동완성 기능을 실행시키지 않아도 되는 것이 참 매력적이라 느꼈을 것이다.**



**그 편함을 잊지 못하기에, 찾던 중 eclipse에서도 똑같은 기능을 구현할 수 있는 방법을 찾게되어 포스팅한다.**





### **[설정 방법]**

**① eclipse -> window -> Preferences**





![img](https://k.kakaocdn.net/dn/d9XVrm/btqDCZ99A9S/rBzHNHkAevOyfL366k840K/img.png)





**② Java -> editor -> content Assist**



(위 과정으로 들어가는게 귀찮다면, type filter text 검색란에 content assist를 바로 검색하자)

그리고 큰 사각형 영역의 Auto Activation을 주목!











![img](https://k.kakaocdn.net/dn/pFxTt/btqDADUvCkn/3w5ynFR8X0mZq4L8FcchK0/img.png)











**③ Auto activation delay 입력란은 0 값으로 설정,**

  ***\*Auto activation triggers for java 입력란 에는 아래 문자열 코드를 전체 복사해서 붙여놓기!\****

***\*->\**** ***\*Apply and close!\****



[ 복사 붙여넣기 할 문자열 코드 ↓ ]

> .qwertyuioplkjhgfdsazxcvbnm_QWERTYUIOPLKJHGFDSAZXCVBNM@
>
> 위 코드의 작동원리를 간단하게 설명하면, 복붙한 코드에 있는 문자를 하나 입력하더라도 자동완성기능 실행됨. 



![img](https://k.kakaocdn.net/dn/bzKPtk/btqDyFyYHZA/ehd2rXbSC0z6QLKxSyCEMk/img.png)





### **[설정 후]**

**ctrl+space가 아닌 글자만 입력해도 자동완성 기능이 아래 사진과 같이 나오는 건을 알 수 있다.**



![img](https://k.kakaocdn.net/dn/DV4MZ/btqDzDULlUB/50LPQ2DhxYe03BHWd4EhA0/img.png)

![img](https://k.kakaocdn.net/dn/ImbFX/btqDCaqyoNb/YlygUv55NPwKuDbdfCLDgk/img.png)

 
위 기능에 맛들린 개발자는..... 
이클립스 설치하는 즉시 셋팅설정하게 될 것입니다🤭
1분 1초라도 아껴서 즐코하세요🙂





♥수정이 필요한 부분 , 지적해주실 부분은 댓글로 부탁드려요~ 피드백은 언제나 환영입니다♥

♥긴 글 읽어주셔서 감사합니다♥





참조

[ https://stackoverflow.com/questions/5685257/any-way-to-get-intellij-like-autocompletion-in-eclipse/12349932#12349932](https://stackoverflow.com/questions/5685257/any-way-to-get-intellij-like-autocompletion-in-eclipse/12349932#12349932)