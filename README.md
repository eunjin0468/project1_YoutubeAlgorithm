# 개선된 YouTube 동영상 추천 알고리즘 개발

사용자가 기존 유튜브 추천 알고리즘에서 벗어나 더욱 새롭고 다양한 영상을 접할 수 있도록 **개선된 추천 알고리즘**을 구현한 프로젝트입니다.  
추천 영상의 키워드를 추출하고 관련 댓글을 분석하여 보다 다채로운 콘텐츠를 제공함으로써, 사용자 경험 향상과 서비스 이용 시간 증가 및 수익 극대화를 목표로 합니다.

---

## 📌 기술 스택 및 라이브러리

- **언어:** Python  
- **개발 환경:** Jupyter Notebook  
- **기술 스택:** 웹 크롤링  

### 라이브러리
- **BeautifulSoup, Selenium** → 웹 크롤링  
- **WordCloud** → 텍스트 시각화  
- **pandas** → 데이터 처리 및 분석  
- **KRWordRank** → 한글 키워드 추출 및 텍스트 마이닝  

---

## 💭 회고

- **pandas (데이터 처리 및 분석)**  
  - 대용량 데이터 정제와 키워드 중복 제거  
- **KRWordRank (한글 키워드 추출)**  
  - 댓글 데이터를 기반으로 효과적인 키워드 추출 가능  
- **데이터 처리 및 성능 최적화**  
  - 크롤링 데이터가 많아질수록 메모리 관리와 데이터 정제 중요  
- **사용자 경험 개선 여부**  
  - 추천된 영상이 사용자의 관심사와 얼마나 부합하는지 검증 필요  

---

## 🔨 프로젝트 내용

### 1️⃣ 실행결과를 저장할 CSV 파일 생성

[CSV 파일 생성]<img width="607" height="297" alt="1" src="https://github.com/user-attachments/assets/80a76f99-b3d4-4484-88cd-381427777d88" />

### 2️⃣ 시크릿 모드 활용

- 구독/시청 기록이 유튜브 환경에 영향을 미치지 않도록 시크릿 모드 사용  
- 중복되지 않는 다양한 콘텐츠 제공 가능  

![시크릿 모드](https://prod-files-secure.s3.us-west-2.amazonaws.com/e147a65b-e273-4ef6-8434-be616017032f/9e712b54-d4f0-417d-a402-7f0ea3c740fa/Untitled.png)

### 3️⃣ 크롤링으로 유튜브 동영상 제목 수집

- 초기 화면 20회 새로고침하며 영상 제목 수집  
- `find`와 `get_text`를 이용해 원하는 제목만 텍스트로 추출  

![동영상 제목 수집](https://prod-files-secure.s3.us-west-2.amazonaws.com/e147a65b-e273-4ef6-8434-be616017032f/5002b90e-e9da-4c93-b25e-5f9cbede4e1e/Untitled.png)

### 4️⃣ 상위 10개 키워드 추출

- KRWordRank를 사용하여 의미 없는 키워드 제외  
- 조건에 맞는 빈도수 높은 상위 10개 키워드 추출  

![키워드 추출](https://prod-files-secure.s3.us-west-2.amazonaws.com/e147a65b-e273-4ef6-8434-be616017032f/db210e02-71e5-47bf-8e66-6c3515f304e2/Untitled.png)

### 5️⃣ 댓글 크롤링

- 상위 10개 키워드 검색 후 댓글 수집  
- 실시간 스트리밍 영상 제외 (도배성 댓글 방지)  
- 댓글 텍스트 형태로 저장  

### 6️⃣ 댓글 기반 추가 키워드 추출

- 저장된 댓글을 사용하여 다시 상위 10개 키워드 추출  
- KRWordRank 활용  

![댓글 기반 키워드](https://prod-files-secure.s3.us-west-2.amazonaws.com/e147a65b-e273-4ef6-8434-be616017032f/5527d00f-7f6a-4a2c-816a-a3190763cd2b/Untitled.png)

### 7️⃣ 추천 동영상 URL 제공

- 중복 제거 후 키워드 기반 추천 영상 추출  
- 키워드별 5개의 추천 영상 제목과 URL 제공 (href 형식)  

![추천 영상 URL](https://prod-files-secure.s3.us-west-2.amazonaws.com/e147a65b-e273-4ef6-8434-be616017032f/0113c6c8-7085-4afb-a0fb-712c2da889bb/Untitled.png)

---

## 🍀 기대효과

- 사용자가 관심 있는 새로운 콘텐츠를 쉽게 탐색 가능  
- 추천 영상 다양화로 서비스 체류 시간 증가 및 수익 증대  

![기대효과](https://prod-files-secure.s3.us-west-2.amazonaws.com/e147a65b-e273-4ef6-8434-be616017032f/bc933dc9-3c48-4465-9a14-bc0e97f70201/Untitled.png)

---

## 🎯 결과 및 성과

- 대한전기학회 [대학생 작품경진대회] 장려상 수상
