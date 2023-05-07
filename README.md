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
  
   
 - twitter-Korea을 이용한 한국어 형태소 분석
    - 트위터 게시글과 같은 짧은 글에 특화되어 있어 댓글 데이터에 적합함
  
 - 모델링 : 최종적으로 SVM 선정
   1. 악성 댓글이 훨씬 적음 -> up sampling으로 클래스 불균형 해소
   2. AdaBoost
   3. Neural Network
   4. Random Forest
   5. SVM
  
### 결과
- 전체 네이버 기사 댓글 EDA
- 네이버 기사에서 벗어난 범용성이 있는 새로운 테스트 셋에 적용시켜봄
- [발표영상](https://www.youtube.com/watch?v=TkLrDL0XnkM)
