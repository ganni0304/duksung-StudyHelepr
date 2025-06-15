# 인터넷기초[04] 과제2 - 나만의 인공지능 서비스

## 개요
* 서비스명 : Study Helper
* 서비스 설명 : 사용자로부터 질문, 어려운점 , 이해도를 입력 받으면, Study Helper은 사용자가 입력한 질문에 대한 답과 설명ㅇ르 사용자에게 알려준다. 특히 설명 후에 유사한 문제나 변형 문제 2개를 생성해줌으로써 사용자의 학습에 도움을 되도록한다.
* 서비스 접속 주소 : https://ganni0304.github.io/duksung-studyhelper/

## 서비스 구성 요소(1) - Gemini API
* Study Helper가 답변하는 설명과 문제는 구글의 LMM 모델인 Gemini API를 활용해 생성한다.
* 활용 모델 : Gemini-2.0-flas
* 시스템 프롬프트 주안점
   - 문제에 대한 설명을 해주는 인공지능에게 모든 학문에 박식한 박사급 AI 교육 전문가라고 역할을 부여했다.
   - 말투는 따뜻하고 친절하게 해주라고 제시했다.
   - 긴 설명이나 튜토리얼을 작성 때 갇고성을 위하여 번호, 제목, 구분선, 코드 블록을 사용하여 시각적으로 구분하라 하였다.
   - 마지막에는 학생의 동기를 복돋을 수 있는 격언으로 마무리하도록 지정했다. 
 
## 서비스 구성 요소(2) - 프론트엔드
* Study Helper 서비스 페이지는 HTML, CSS, JavaScript를 사용하여 간단하게 구성하였다.
* CSS 스타일 시트는 style.css 파일로 분리하였다.
* 리락쿠마 병아리가 선생님이 된 것처럼 이미지를 OpenAI Sora를 이용하여 생성하였다.
  ![리락쿠마](https://github.com/user-attachments/assets/364719c6-2870-40bf-a96a-c5df5f4a7952)

## 서비스 구성 요소(3) - 백엔드
* 구글 Gemini API 호출을 위한 API 키가 노출되지 않도록, 프론트엔드의 요청을 받아서 Gemini API를 호출해주는 간단한 API 백엔드를 구성하였다.
* 해당 백엔드 로직은 서버리스 (Severless) 함수 기능을 제공하는 Vercel에 배포했다.
* 코드 및 구현 내용은 https://github.com/ganni0304/duksung-studyhelper-API를 참고한다. 
