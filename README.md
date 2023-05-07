# 네이버 뉴스 악성 댓글 분류기 생성
### 7th BOAZ Bigdata Conference
- 팀원 : 김유경, 최하은, 김현중, 박정우, 김수연
---
### 분석 주제
- 네이버 뉴스의 악성 지수 구축 및 악성 댓글 분류 모델링

### 분석 과정
- 데이터 수집
  ![데이터 수집](https://user-images.githubusercontent.com/90254892/236655584-244f6615-97c2-4ad0-8d38-1b9476ff711d.png)
  - 대략 10주간 일주일에 6개 카테고리(사회, 경제, 생활/문화, IT/과학, 정치, 연예인)당 30개 기사의 댓글 크롤링    
  
  ![카테고리별 댓글 개수](https://user-images.githubusercontent.com/90254892/236655590-b0dc3e5f-1da3-473a-9121-c33d2cc70a65.png)
  - 카테고리별 댓글 개수
  
- 악성 지수 구축
  1. 악성 라벨링을 위한 샘플링
    - 한 개의 뉴스당 4개의 댓글 층화 추출
    - 총 7,180개 댓글 샘플 사용
  2. 팀원 다섯명의 라벨의 최빈값을 최종 라벨로 사용
  
  - 악성 댓글 기준
    ![악성아님](https://user-images.githubusercontent.com/90254892/236655860-8036b58b-8e41-4476-ae01-0f8fe0775e4b.png)
    - 표현의 자유라고 인정하여 악성 댓글이 아닌 것으로 분류
    
    ![악성임](https://user-images.githubusercontent.com/90254892/236655861-89c4543a-6705-4448-8a07-cb539f1038eb.png)
    - 표현의 자유를 넘어 공격적인 악성 댓글인 것으로 분류
   
 - twitter-Korea을 이용한 한국어 형태소 분석
    - 트위터 게시글과 같은 짧은 글에 특화되어 있어 댓글 데이터에 적합함
      ![데이터 전처리 예시](https://user-images.githubusercontent.com/90254892/236655976-8a3d1080-1a74-4aaf-88e8-6e4fbee7f539.png)
      - 데이터 전처리 
  
 - 모델링
   - 악성 댓글이 훨씬 적음 -> up sampling으로 클래스 불균형 해소
   - 10-fold Cross Validation

    ![모델선정](https://user-images.githubusercontent.com/90254892/236656081-47c45f3e-b79b-4ba0-b0d1-e16d4d4f759b.png)
      - 최종 모형으로 SVM 선택 
    
    !
  
### 결과
- 전체 네이버 기사 댓글 EDA
- 네이버 기사에서 벗어난 범용성이 있는 새로운 테스트 셋에 적용시켜봄
- [발표영상](https://www.youtube.com/watch?v=TkLrDL0XnkM)
