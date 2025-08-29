## 텍스트 수집
1. **google-play-scraper 라이브러리 활용**  
   - Google Play Store에서 ChatGPT, Google Gemini 앱 리뷰 자동 수집  
   - 리뷰 텍스트, 별점, 작성일, 공감 수 등 메타데이터 포함  

2. **앱 고유 식별자(App ID) 기반 수집**  
   - Play Store URL 내 `id=` 뒤의 문자열을 이용  
   - 예: `com.openai.chatgpt`  

3. **리뷰 필터링**  
   - 별점 **1점 리뷰(부정)**, **4점 리뷰(긍정)**만 추출  
   - 5점 리뷰는 과도한 칭찬·단순 긍정으로 인한 분석 왜곡 가능성 때문에 제외  

4. **데이터 전처리**  
   - 소문자 변환, 특수문자/기호 제거  
   - 불용어 제거, 토큰화  
   - 표제어 추출(Lemmatization), 어간 추출(Stemming)  

---

## 텍스트 분석 기법
1. **이그램(Bigram) 빈도 분석**  
   - 리뷰 내 연속된 단어 쌍을 추출하여 주요 불만/호감 패턴 확인  

2. **동시 출현어 네트워크 분석**  
   - 단어 간 동시 등장 관계를 네트워크 구조로 분석하여 핵심 연결 구조 파악  

3. **TF-IDF (Term Frequency–Inverse Document Frequency)**  
   - 각 리뷰에서 상대적으로 중요한 단어를 추출하여 핵심 키워드 비교  

4. **LDA 토픽 모델링 (Latent Dirichlet Allocation)**  
   - 리뷰 텍스트를 주제별로 분류하여 공통 주제 및 차별적 주제 도출  
   - LDAvis 시각화 포함  

5. **감성 분석 (Sentiment Analysis)**  
   - 긍정/부정/중립 감정 분포 비교  
   - 감성별 빈도 단어 및 시각화 (Wordcloud, 빈도 그래프)
