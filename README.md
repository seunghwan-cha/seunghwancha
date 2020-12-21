네이버 영화 리뷰 감성 분류

다운로드링크 : https://github.com/e9t/nsmc/

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
