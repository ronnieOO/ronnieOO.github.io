---
title : STS 톰캣 서버 연동 - macOS M1
date : 2024-07-16 +0900
categories : [개발이야기]
tags : sts, macos, m1
---
# STS 톰캣 서버 연동
---
## 1. 설치 준비 
- JDK 11 이상 설치하기
- 톰캣 9.0.x 설치하기
- STS4 다운로드 (Spring Tools 4 for Eclipse) <br>
https://spring.io/tools ➡️ MACOS ARM_64 다운로드 한 후, 설치하기

## 2. ch2 프로젝트 import 하기
아래 github 링크에서 ch2.zip 다운로드 <br>
https://github.com/castello/spring_basic/blob/main/download/ch2.zip <br>
다운 받은 ch2.zip 파일의 압축 풀어주기<br>
<br>
STS4에서 `import projects...` 클릭 <br>
<img width="243" alt="Screenshot 2024-07-16 at 7 54 17 PM" src="https://github.com/user-attachments/assets/92b8678e-0ebe-46b6-b5f4-c19003c05723">{: .align-left}
<br><br>
아래 화면에서 `Existing Projects into Workspace` 선택 후, `Next>` 클릭<br>
<img width="592" alt="Screenshot 2024-07-16 at 7 58 15 PM" src="https://github.com/user-attachments/assets/1d157fc7-6d04-43c3-a25f-9a1fe1e2ebce">
<br><br>
`Browse` 클릭해서 ch2 폴더 지정 후, `Finish` 클릭 <br>
<img width="588" alt="Screenshot 2024-07-16 at 8 04 08 PM" src="https://github.com/user-attachments/assets/f7d8b9bd-de14-41da-bdce-d85a47cd95bf">
<br><br>

## 3. Tomcat 서버 등록하기
STS4 메뉴 > `Window` > `Show View` > `Other...` 클릭 <br>
`Servers` 선택한 후, `Open` 클릭 <br>
<img width="314" alt="Screenshot 2024-07-16 at 8 08 22 PM" src="https://github.com/user-attachments/assets/d69dc23b-539b-4ab5-8ed6-9fe595dd8466">
<br><br>
하단의 `Servers`뷰에서 `No servers are .... ` 클릭<br>
<img width="512" alt="Screenshot 2024-07-16 at 8 08 37 PM" src="https://github.com/user-attachments/assets/b19b350e-6496-4db8-afa9-f52e6f2c9917">
<br><br>
Apache > Tomcat v9.0 Server 선택한 후, `Next >`클릭<br>
<img width="586" alt="Screenshot 2024-07-16 at 8 09 06 PM" src="https://github.com/user-attachments/assets/1fcc024c-26ca-4349-ab90-d7886ef0f0f5">
<br><br>
ch2 선택 후, `Add >` 클릭<br>
<img width="591" alt="Screenshot 2024-07-16 at 8 11 09 PM" src="https://github.com/user-attachments/assets/e354fba2-cc0b-43d6-ad2b-cbb7bd702e5c">
<br><br>
아래처럼 add 되었으면 `Finish` 클릭<br>
<img width="586" alt="Screenshot 2024-07-16 at 8 11 15 PM" src="https://github.com/user-attachments/assets/741f5668-48f9-47e7-88cb-76f15d45c5db">
<br><br>
하단에 `Servers` 뷰에서 추가된 Tomcat 서버에서 우클릭 > `Start` 클릭<br>
<img width="612" alt="Screenshot 2024-07-16 at 8 11 43 PM" src="https://github.com/user-attachments/assets/061672a3-c9d9-4912-a303-be360b7fc6b8">
<br><br>
started 로 상태가 변한 것을 확인 <br>
<img width="485" alt="Screenshot 2024-07-16 at 8 12 07 PM" src="https://github.com/user-attachments/assets/9399f4b8-a942-4589-a3c4-5eca09bf3429">
<br><br>
크롬 브라우저를 열고, localhost:8080 을 방문해서 아래와 같이 나오면 성공! <br>
<img width="547" alt="Screenshot 2024-07-16 at 8 38 09 PM" src="https://github.com/user-attachments/assets/48caab0b-67c9-447d-ad7e-da689eca7dc7">
<br><br>

## 4. 오류 상황
📌 브라우저를 열었는데, 아래와 같이 나왔을 경우 해결방법은 무엇일까?<br>
<img width="1432" alt="Screenshot 2024-07-16 at 8 12 29 PM" src="https://github.com/user-attachments/assets/7e66e745-c66b-4704-b79d-3bcd58af7e5f">
<br><br>
💡 해결 방법 1. <br>
메뉴 > `Setting` > web 검색 > Web Browser 선택 <br>
1. `Use external web browser` 선택
2. `Chrome` 선택 후, `Apply and Close` 클릭
<br>
<img width="618" alt="Screenshot 2024-07-16 at 8 13 29 PM" src="https://github.com/user-attachments/assets/5b9fa75f-b370-44de-807d-166733b79bd1">
<br><br>

💡 해결 방법 2. <br>
하단의 `Modules` 탭을 클릭 > 아래 그림의 경로를 선택 > 오른쪽에 `Edit` 클릭<br>
<img width="1439" alt="Screenshot 2024-07-16 at 8 16 23 PM" src="https://github.com/user-attachments/assets/6fa0b83d-7b8b-4ff7-a65b-6617608d10ed">
<br><br>
아래 그림에서 Path의 경로를 '/ch2' ➡️ '/' 으로 변경 하고, `OK` 클릭 <br>
<img width="293" alt="Screenshot 2024-07-16 at 8 16 37 PM" src="https://github.com/user-attachments/assets/5af489fd-86d4-45b2-90c9-84e16b5276ec">
<br>
<img width="292" alt="Screenshot 2024-07-16 at 8 16 44 PM" src="https://github.com/user-attachments/assets/c7780010-8e6b-44b5-95b5-7e1d13022e9f">
<br><br>

이렇게 하면, 크롬 브라우저에서 톰캣 연동 성공한 화면을 볼 수 있을 것이다. 문제 해결 완료!! 
