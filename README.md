# 0. 핸즈온 준비

- 이벤트 엔진, Cloud Formation 이용: 
    - CloudFormation/Personalize-HOL-CF-template.yaml 파일을 다운 받습니다.
    - 이벤트엔진으로 AWS Console에 접속한 뒤 CloudFormation 으로 이동합니다.
    - Create stack > Specify template - Upload a template file 선택 > 다운받은 yaml파일 선택 > Next > Stack name 입력 (예: Personalize-HOL) > Next > Next > 맨 하단의 Capabilities 체크박스 체크 > Submit
    - CloudFormation 스택 배포는 약 5분 소요 됩니다.
<br><br>
- SageMaker notebook instance 를 이미 가지고 있는 경우 (자신의 계정에서 실습하는 경우)
    - SageMaker notebook instance를 실행하는 Role이 아래 4개의 권한을 꼭 가지고 있어야 합니다. 아래 권한을 추가 해주세요. 참고로 위의 수동 설정에는 아래 4가지 권한을 추가하는 과정이 있습니다. 참고 하세요. (AmazonSageMakerFullAccess, AmazonS3FullAccess, AmazonPersonalizeFullAccess, IAMFullAccess)
    
---

# 1. Personalize 워크샵 (SageMaker Notebook 환경)

- AWS Console > SageMaker 로 이동합니다.
- 왼쪽 패널에서 Notebook > Notebook Instances > "Personalize-Notebook"에서 "Open JupyterLab"을 클릭하면 새 탭으로 Jupyter Notebook이 뜹니다.
- Jupyter Notebook에서 File > New > Terminal 을 선택하여 새 터미널을 엽니다. 아래의 명령을 실행하여 github cloning을 진행 합니다.

```
$ cd SageMaker
$ git clone https://github.com/jesamkim/personalize-basic
```
