# 스치다!
  ![스치다 로고 1](https://practice2082.s3.ap-northeast-2.amazonaws.com/Slide+16_9+-+1+(4).png)




<p align='center'>
  <img src='https://img.shields.io/badge/Javascript-ES6-yellow?logo=javascript'/>
  <img src='https://img.shields.io/badge/Node.js-v16.14.2-green?logo=Node.js'/>
  <img src='https://img.shields.io/badge/Express-v4.18.0-black?logo=Express'/>
  <img src='https://img.shields.io/badge/MongoDB-v4.2.19-green?logo=mongodb'/>
  <img src='https://img.shields.io/badge/prettier-v2.6.2-pink?logo=prettier'/>
  <img src='https://img.shields.io/badge/Passport-v0.5.2-green?logo=passport'/>
  <img src='https://img.shields.io/badge/socket.io-v4.5.0-white?logo=Socket.io'/>
  <img src="https://img.shields.io/badge/Json Web Token-v8.5.1-8a8a8a?logo=JSON Web Tokens&logoColor=white" />
  </br></br>
  Deploy
  </br></br>
  <img src="https://img.shields.io/badge/Git hub-000000?logo=Github&logoColor=white" />
  <img src="https://img.shields.io/badge/GitHub Actions-blue?logo=GitHubActions&logoColor=black">
</p>

## 바로가기
- 사이트 바로가기 : https://seuchida.shop
- 발표 영상 : 

## 🎉 스치다 서비스 소개

### 시연 영상
- 영상 링크 : https://youtu.be/KUxPjKCmbxM

### 1. 우리 동네 스포츠 친구찾기 서비스
<details> <summary>실시간 위치기반 서비스로 현재 내 위치를 기준으로 주변 운동친구들을 찾아주는 서비스입니다!</summary> <div markdown="1"> <img width='25%' src='https://practice2082.s3.ap-northeast-2.amazonaws.com/%EB%A6%AC%EB%93%9C%EB%AF%B8+%EC%9D%B4%EB%AF%B8%EC%A7%801.png'> </div> </details>


### 2. 혼자하기 힘든 운동들도 스치다를 통해 같이 운동할 수 있습니다!
<details> <summary>운동 종목과 운동할 장소, 시간을 정해서 같이 운동할 사람을 모집할 수 있습니다.</summary> <img width='25%' src='https://practice2082.s3.ap-northeast-2.amazonaws.com/%EB%A6%AC%EB%93%9C%EB%AF%B8+%EC%9D%B4%EB%AF%B8%EC%A7%802.png'> </details>

## ERD
![서비스 ERD](https://practice2082.s3.ap-northeast-2.amazonaws.com/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7+2022-05-30+%EC%98%A4%ED%9B%84+4.37.48.png)

## 서비스 아키텍처   

![image](https://user-images.githubusercontent.com/100466594/171614695-39a052f0-a300-4f38-a605-e7b1450be99c.png)


## &#128187;기술스택/라이브러리
### 기술스택
<table width = "200" style="text-align:center;" >
  <tr>
    <th height = "40"> 종류</th>
    <th height = "40">이름</th>

  </tr>
  <tr>
    <td>서버 프레임워크</td>
    <td>Express</td>
  </tr>
  <tr>
    <td >Database</td>
    <td>MongoDB, AtlasDB</td>
  </tr>
  <tr>
    <td >CI</td>
    <td>GithubAction</td>
  </tr>
  <tr>
    <td >CD</td>
    <td>GithubAction</td>
  </tr>
  <tr>
    <td >이미지파일 저장소</td>
    <td>S3</td>
  </tr>
  <tr>
    <td >로드밸런스</td>
    <td>AWS ELB</td>
  </tr>
  <tr>
    <td >실시간데이터통신</td>
    <td>socket.io</td>
  </tr>

<table width = "200" style="text-align:center;" >
  <tr>
    <th height = "40">라이브러리</th>
    <th height = "40">Appliance</th>

  </tr>
  <tr>
    <td >dotenv</td>
    <td>포트값외 중요한값 보안처리</td>
  </tr>
  <tr>
    <td >Mongoose</td>
    <td>MongoDB 데이터 모델링</td>
  </tr>
  <tr>
    <td >Cors</td>
    <td>Request Resource 제한</td>
  </tr>
   <tr>
    <td>passport,passport-google-oauth20,passport-kakao</td>
    <td> 소셜 로그인 </td>
  </tr>
   <tr>
    <td>socket.io</td>
    <td> 실시간 통신 </td>
  </tr>
  <tr>
    <td >jsonwebtoken</td>
    <td> 암호화 </td>
  </tr>
   <tr>
    <td>prettier</td>
    <td> 클린코드 </td>
  </tr>
  <tr>
    <td>multer-s3</td>
    <td> s3이미지 업로드 </td>
  </tr>
  <tr>
    <td>Joi
</td>
    <td> 유효성 검사 </td>
  </tr>
  <tr>
    <td>artillery</td>
    <td> 부하테스트 </td>
  </tr>
  
</table>

## 트러블 슈팅 
### 1. 게시글 삭제 API 보안이슈
<details> <summary>(1) 게시글 삭제 관련 보안문제</summary> 다른 사람 게시글 주소창의 url을 이용해서 postman 혹은 ARC를 통해 작성자 본인이 아닌 다른사람의 토큰으로도 삭제할 수 는 문제가 있었습니다. 그래서 백앤드 코드에서도 게시글 삭제api에  게시글 작성자와 삭제하려는 사람의 아이디가 같은지 검증절차를 추가해서 문제를 해결했습니다.
  </details>

### 2. 데이터베이스 해킹 이슈
<details> <summary>EC2 데이터베이스 해킹</summary> 서버 ec2에 데이터베이스를 설치해서 사용하는 중 데이터베이스를 해킹당하는 일이 있었습니다. 원인을 데이터베이스 계정 비밀번호가 간단해서 발생한 문제로 파악하여 비밀번호를 어렵게 변경해봤지만 같은일이 발생하였고 이 부분을 해결하기 위해 몽고db에서 관리해주는 아틀라스를 사용하고 아틀라스 자체의 화이트리스트를 작성했습니다. 화이트리스트에 지정된 ip만 접근할수있게 함으로써 보안을 강화했습니다.
 </details>
  
### 3. socket.io&로드밸런서 이슈
<details> <summary>socket.io&로드밸런서</summary> 로드밸런서를 적용하기전에는 소켓 기능이 잘 작동했지만 로드밸런서로 서버를 여러개 연결하는 순간부터 socket polling error가 발생했습니다. 원인은 http long polling 통신이 socket.io 세션의 수명동안 여러번http 요청을 보내서 생긴 문제였습니다. 구글링 해본결과 여러 서버를 운영 하려면 sticky session을 활성화 하거나 http long polling을 비활성화 하기위해 websocket 통신을 사용하면 에러가 해결된다는 걸 알아냈습니다. 저희는 두번째 방법인 websocket 통신을 이용해서 에러를 해결했습니다.
 </details>
  

## 📌 팀원소개
### 백엔드
<table width = "200" style="text-align:center;" >
  <tr>
    <th height = "40"> Name</th>
    <th height = "40"> Github</th>
  </tr>
  <tr>
    <td> 신상렬 </td>
    <td> https://github.com/gofl26 </td>
  </tr>
  <tr>
    <td> 윤영수 </td>
    <td> https://github.com/tayyoon </td>
  </tr>
  <tr>
    <td> 김연유 </td>
    <td> https://github.com/gitmackenzie </td>
  </tr>
</table>
  
### 프론트엔드
<table width = "200" style="text-align:center;" >
  <tr>
    <th height = "40"> Name</th>
    <th height = "40">Github</th>
  </tr>
  <tr>
    <td> 이태훈 </td>
    <td> https://github.com/hoontail </td>
  </tr>
  <tr>
    <td> 최정원 </td>
    <td> https://github.com/carrot31 </td>
  </tr>
  <tr>
    <td> 강형원 </td>
    <td> https://github.com/hyoungwonkang </td>
  </tr>
</table>

### 디자이너
<table width = "200" style="text-align:center;" >
  <tr>
    <th height = "40"> Name</th>
    <th height = "40">Blog</th>
  </tr>
  <tr>
    <td> 이수림 </td>
    <td>  </td>
  </tr>
  <tr>
    <td>장유진</td>
    <td> https://www.notion.so/Eugene-e1d9ac3124fe426ab29ce979daa88907 </td>
  </tr>
</table>
