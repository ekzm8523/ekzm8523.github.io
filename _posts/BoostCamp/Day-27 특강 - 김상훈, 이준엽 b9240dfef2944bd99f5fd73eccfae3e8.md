# Day-27 특강 - 김상훈, 이준엽

## 김상훈-캐글 그랜드마스터의 경진대회 노하우 대방출

- 업스테이지 데이터 사이언티스트
- 캐글 그랜드마스터 [ 통합 랭킹 최고 12등 ]
- 얼굴인식 전공
- 머신러닝 경력 15년 이상

인공지능 경쟁 플랫폼

캐글, 카카오 아레나, 데이콘

캐글을 해야 하는 이유

세계적으로 실력을 인정 받기 위해서

AI개발자로 배우고 성장 하기 위해서

우승하기 위해 필요한 것

- [ ]  파이프라인 (빠른/효율적) 반복
- [ ]  점수 개선 아이디어
- [ ]  탄탄한 검증 전략

### Notebooks 탭, Discussion 탭 참고

다양한 아이디어를 얻을 수 있음. Best Score, Most Votes 정렬 기능 사용 추천

비슷하거나 동일한 이전 대회, 참고할 논문, 현재 대회 Overview 등등

다른 사람들의 아이디어를 캐치해오는 것도 능력이다.

![_2021-03-03_10 21 48](https://user-images.githubusercontent.com/67869514/109791415-c854d800-7c55-11eb-8417-1a72479858da.png)


### 탄탄한 검증 전략 구축

Overfitting으로 인해 Public LB에서 1등이라도 Private LB 는 훨씬 하락될 가능성이 높음 → shake-up 현상

중요한건 Training set의 정확도와 Test set사이의 정확도의 갭을 줄여야 한다. → 낮을수록 좋은 모델

![_2021-03-03_10 26 03](https://user-images.githubusercontent.com/67869514/109791427-cbe85f00-7c55-11eb-9bc5-d75ba45f63a1.png)


캐글 데이터 구성

![_2021-03-03_10 26 45](https://user-images.githubusercontent.com/67869514/109791431-cd198c00-7c55-11eb-8ae1-1e0e1c89f393.png)

가장 유명한 전략은 k-fold 검증 전략 구축이다.

그중에서도 요즘은 Stratified k-fold를 자주 사용한다.

![_2021-03-03_10 28 14](https://user-images.githubusercontent.com/67869514/109791433-cdb22280-7c55-11eb-881f-683ce21b8a10.png)

### 아무리 검증 전략을 잘 세워도 오버 피팅의 위험은 존재

local CV와 public CV가 함께 올라가는 방법을 선택해야 한다.

### 정확도를 올리기위한 기타 꿀팁 [ 앙상블 ]

여러 방법이 있지만 요즘은 아래처럼 정리되는 추세이다.

![_2021-03-03_10 31 17](https://user-images.githubusercontent.com/67869514/109791438-ce4ab900-7c55-11eb-96c3-e8e7aebf99a0.png)

### 대회에서 좋은 성적을 내려면 높은 점수의 싱글 모델이 필요

앙상블 해도 싱글 모델의 점수에서 약간 개선이 있을 뿐임

### 언제까지 개선해야할까?

상위 랭커들이 discussion에서 언급한 자신의 싱글모델 점수 참고

대회 1~2주 정도 남았을때 싱글 모델 점수로만 50등 내에 들면 좋음

### 코드 관리

v1, v2, v3 버전별로 전처리 된 데이터, 모델 파일을 저장한다.

주피터에서 터미널을 열 수 있고 크롬 창을 닫아도 살아있으므로 원격 학습 가능하다.

---

# 이준엽 - Full Stack Machine Learning Engineer

- 엔씨소프트 AI센터 NLP Lab Machine learning research engineer (전문연구요원)
- 네이버 Clova AI OCR 팀 Tech leader / Machine learning research engineer
- 업스테이지 Machine learning research engineer (Co-founding member)

### Full stack + ML ?

Front + (Backend+ML) 와 (Front+ML) + Backend 정도로 나뉘는 것 같다.

![_2021-03-03_18 49 59](https://user-images.githubusercontent.com/67869514/109791442-cee34f80-7c55-11eb-9d33-3a92894cdf31.png)

![_2021-03-03_18 51 03](https://user-images.githubusercontent.com/67869514/109791444-cee34f80-7c55-11eb-844a-676e8aa7df90.png)

### ML Product의 과정이란?

보통 아래의 순서를 거친다.

요구사항 전달 → 데이터 수집 → ML 모델 개발 → 실 서버 배포 

조금 더 세밀하게 들어가자면

### 요구사항 전달

- 고객사 미팅(B2B) or 서비스 기획(B2C) - 제품에 대한 요구사항 전달, 추상적인 단계
- 요구사항 + 제약사항 정리 - 기능 상세 요구 사항 정리, 제약 사항 정리, 일정 정리
- ML Problem 으로 회귀 - 요구사항은 실 생활의 문제 , ML이 풀 수 있는 형태의 문제로 회귀하는 작업

### 데이터 수집

- Raw 데이터 수집 - 요구사항에 맞는 데이터 수집, Bias 없도록 분포 주의 , 저작권 주의
- Annotation Tool 기획 및 개발 - 데이터에 대한 정답 입력 툴, 모델 input / output 고려, 작업속도 / 정확도 극대화
- Annotation Guid 작성 및 운용 - 이럴 땐 어떻게 Annotation 하나요 ? 에 대한 대답이 되는 문서, 간단하고 명확한 Guide 문서를 작성하도록 노력

### ML 모델 개발

- 기존 연구 Research 및 내재화 - 논문을 찾아보고 이해하는 단계, 적절한 연구를 재현하여 내재화
- 실 데이터 적용 실험 + 평가 및 피드백 - 수집된 데이터 적용, 평가 및 모델 수정
- 모델 차원 경량화 작업 - 모델 단계의 경량화, Distillation, Network surgery

### 실 서버 배포

- 엔지니어링 경량화 작업 - Tenso RT 등의 프레임워크 적용 , Quantization
- 연구용 코드 수정 작업 - 연구용 코드 정리, 배포용 코드와 Interface 맞추는 작업
- 모델 버전 관리 및 배포 자동화 - 모델 버전 관리 시스템, 모델 배포 주기 결정 & 업데이트 배포 자동화 작업

![_2021-03-03_19 01 54](https://user-images.githubusercontent.com/67869514/109791445-cf7be600-7c55-11eb-8602-316986c8d448.png)

## 마무리 하자면

내가 되고싶은게 모든 분야를 두루두루 잘 할 수 있는 이준엽마스터님같은 풀스택 ML 개발자이다.

일단 많은 코드를 직접 짜보는게 중요할 듯하다.

## 피어세션

### U-net 논문 리뷰

The Contracting Path와 Expanding Path로 나뉨

The Contracting path

3*3 convolutions , not padding

Relu

2*2 max pooling(stride: 2)

Down sampling
