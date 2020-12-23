NLP Sentiment Analysis
자뎐어처리 한글/영어 감정분석 모델


한글 감정 분석 모델
<네이버(NSMC) 영화 리뷰 감정 분류>

실행환경 : Colab
데이터 정제 : 중복제거
토큰화 : 불용어 제거
형태소분석기 : konlpy Okt 사용
정수인코딩
빈 샘플 제거
패딩
LSTM을 활용한 감정분석
model = Sequential()
model.add(Embedding(vocab_size, 100))
model.add(LSTM(128))
model.add(Dense(1, activation='sigmoid'))

model.compile(optimizer='rmsprop', loss='binary_crossentropy', metrics=['acc'])
history = model.fit(X_train, y_train, epochs=15, callbacks=[es, mc], batch_size=60, validation_split=0.2)

참조 : https://wikidocs.net/44249
각종 모델 및 오픈소스 참고

영어 감정 분석 모델
<프렌즈 드라마 대사 감정 분류>

실행환경 : Colab
CNN.LSTM을 이용한 모델링 결과 30% 이하
ELECTRA 모델 사용 50% 
데이터 전처리, 모델 구현 및 학습, 결과 확인 진행

참조 : https://www.secmem.org/blog/2020/07/19/Sentiment-Analysis
https://github.com/jiwonny/nlp_emotion_classification
각종 인터넷 자료 및 오픈소스 
