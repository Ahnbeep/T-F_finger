# T-F_finger

**요구사항 정의서**

1. Dataset 확인

train set과 test set은 세 개의 다른 캡쳐 장치에서 뽑은 live와 fake 지문 이미지를 포함한 세 개의 하위set 으로 구성되어 있다. test set 내에 알고리즘의 generalizaion 능력을 평가하기 위해서 never-seen-before attack 이 있을 예정이다.
 
2. 2개 track: real vs. fake, 지문 표현법에대해 조사 = challenge 1, 2 

  1. [nameOfAlgorithm].exe 실행 가능한 이름이어야 한다.
  2. [ndataset] 분석하기 위한 dataset 의 식별 번호
  3. [templateimagesfile] 시스템 내 등록된 각 템플릿 이미지의 절대 경로 리스트를 포함한 텍스트 파일
  4. [probeimagesfile] 분석하기 위해 각 이미지의 절대 경로 리스트를 포함한 텍스트 파일
  5. [livenessoutputfile]
  6. [IMSoutputfile] 처리된 이미지와 해당(일치하는) 템플릿 간의 통합 일치 점수 결과를 포함한 텍스트 파일. 결과는 live class와 0부터 100까지 정규화된 이미지가 주어진  the belonging of the claimed identity given the image의 결합된  posterior 확률을 말한다.
 
점수 [50, 100]이 지문 이미지를 “live와 genuine”로 분류할때, 점수 [0, 50) 은 지문 이미지를 “fake와  attacker”로 분류한다

**화면 설계**
1. 기초학습
2. Data augmentation
3. Robustness(Regularization)
![image](https://user-images.githubusercontent.com/74764725/122212547-eed80f80-cee2-11eb-8456-cfb691fb64b3.png)


**아키텍쳐**

1. data 전처리 - 이미지 폴더명, 파일명 고려해 renaming
![image](https://user-images.githubusercontent.com/74764725/122212604-00211c00-cee3-11eb-9fa8-a2aaea375bfc.png)

2. csv파일 만들기
![image](https://user-images.githubusercontent.com/74764725/122212619-057e6680-cee3-11eb-8115-30a60c792f98.png)
4. deepfake 코드로 학습
5. adversarial input data 생성
6. adversarial input data 추가 방식 찾기
7. adversarial input data로 학습

![image](https://user-images.githubusercontent.com/74764725/122212717-20e97180-cee3-11eb-912a-4d47fe408767.png)
![image](https://user-images.githubusercontent.com/74764725/122212738-2777e900-cee3-11eb-8301-268c2b63b033.png)

![image](https://user-images.githubusercontent.com/74764725/122212733-25ae2580-cee3-11eb-9c6e-1f4d136c72e2.png)


