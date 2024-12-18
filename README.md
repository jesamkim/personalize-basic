# Amazon Personalize 기초 실습

이 프로젝트는 Amazon Personalize를 사용하여 추천 시스템을 구현하는 단계별 실습 가이드입니다.

## 프로젝트 개요

Amazon Personalize를 활용하여 개인화된 추천 시스템을 구축하는 방법을 학습할 수 있습니다. 실제 소매(Retail) 데이터셋을 사용하여 데이터 준비부터 추천 모델 생성, 평가, 그리고 실제 추천을 받아보는 과정까지 전체 과정을 체험해볼 수 있습니다.

## 실습 구성

실습은 다음과 같은 순서로 진행됩니다:

1. 데이터셋 준비 (`1.prepare_dataset.ipynb`)
2. 데이터 변환 (`2.transform_dataset.ipynb`)
3. S3에 데이터셋 업로드 (`3.upload_dataset_to_s3.ipynb`)
4. Dataset Group 생성 (`4.create_dataset_group.ipynb`)
5. 솔루션(추천 모델) 생성 (`5.create_solution.ipynb`)
6. 솔루션 메트릭 평가 (`6.evaluate_solutions_metrics.ipynb`)
7. 캠페인 생성 (`7.create_campaign.ipynb`)
8. 추천 결과 확인 (`8.get_recommendations.ipynb`)
9. 리소스 정리 (`9.cleanup.ipynb`)

## 사전 준비사항

### 옵션 1: CloudFormation 이용

1. CloudFormation 템플릿 준비
    - `CloudFormation/Personalize-HOL-CF-template.yaml` 파일을 다운로드합니다.

2. CloudFormation 스택 생성
    - AWS Console에 접속한 뒤 CloudFormation으로 이동합니다.
    - Create stack > Specify template에서 "Upload a template file" 선택
    - 다운로드한 yaml 파일 선택 > Next
    - Stack name 입력 (예: Personalize-HOL) > Next > Next
    - 맨 하단의 Capabilities 체크박스 체크 > Submit
    - 스택 배포에는 약 5분이 소요됩니다.

### 옵션 2: 기존 SageMaker Notebook Instance 사용

기존 SageMaker notebook instance를 사용하는 경우, 실행 Role에 다음 권한들이 필요합니다:
- AmazonSageMakerFullAccess
- AmazonS3FullAccess
- AmazonPersonalizeFullAccess
- IAMFullAccess

## 실습 시작하기

1. AWS Console에서 SageMaker AI로 이동합니다.
2. Notebook > Notebook Instances에서 "Personalize-Notebook"의 "Open JupyterLab" 클릭
3. JupyterLab에서 새 터미널을 열고 (File > New > Terminal) 다음 명령어를 실행:
```bash
cd SageMaker
git clone https://github.com/jesamkim/personalize-basic
```

## 프로젝트 구조

```
personalize-basic/
├── CloudFormation/              # AWS 리소스 설정을 위한 CloudFormation 템플릿
├── code/                       # 실습 노트북 및 관련 파일
│   ├── src/                   # 유틸리티 함수
│   ├── img/                   # 실습 가이드 이미지
│   └── *.ipynb               # 단계별 실습 노트북
└── data/                      # 실습에 사용할 데이터셋
```

## 주의사항

- 각 노트북은 순서대로 실행해야 합니다.
- AWS 리소스 사용에 따른 비용이 발생할 수 있으므로, 실습 완료 후 반드시 cleanup 노트북을 실행하여 리소스를 정리해주세요.
