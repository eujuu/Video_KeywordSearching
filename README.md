# Video_KeywordSearching
__영상의 핵심 문장 추출 및 핵심 키워드의 timestamp 찾기__<br/>

stt를 실행하여 script와 timestamp를 저장한 뒤, 원하는 파일 실행(빈도수 이용, textrank, lda, 단순 키워드 매칭 사용)

### 1. STT
* 구글 stt 이용, script와 timestamp정보 저장
* [Google STT Link](https://cloud.google.com/speech-to-text?hl=ko)

### 2. 빈도수
* 명사의 빈도수가 가장 높은 부분이 핵심 문장일 것이라고 간주
* 빈도수가 높은 단어를 찾아 그 단어가 출현한 timestamp알아내기

### 3. TextRank
* 핵심 문장을 찾는 전통적인 기법인 TextRank
* [lovit textrank] (https://lovit.github.io/nlp/2019/04/30/textrank/) <br/>
+) wordRank는 별로여서 따로 저장하지 않음

### 4. LDA
* Topic Modeling에 많이 쓰는 LDA(Latent Dirichlet Allocation)기법

### 5. 단순 키워드 매칭
* 키워드를 미리 저장하여서 해당 키워드 출현 위치 저장
* stt성능에 크게 의존

### 6. timestamp위치 알아내기
* nlp를 하기 위해 문장 분리를 수행하는 과정에서 단어의 구성이 기존 script와 달라지면서 단순하게 단어의 수로 timestamp를 알아내는게 힘들어짐
* cosine similarity를 이용하여 찾은 핵심 문장과 script내에서의 문장 중, 가장 유사한 문장의 timestamp를 저장
