# Introduction
2차 프로젝트 이커머스기반 플랫폼 또는 앱개발

## 프로젝트 구조

AIRestaurant/
├── proj/ # Django 설정 모듈
├── restaurant/ # 앱
├── templates/ # 템플릿 HTML
├── .env # 환경변수 파일 (Git에 업로드 금지)
├── requirements.txt # 설치 패키지 목록
└── manage.py

## Preparation

가상 환경 설정 (WSL/macOS 공통)

```zsh
cd AIRestaurant
python3 -m venv venv
source venv/bin/activate
```

패키지 설치

```zsh
pip install -r requirements.txt
```

환경 변수 설정(.env)

```
DEBUG=False
SECRET_KEY=django-in
ALLOWED_HOSTS=*
```

AWS CLI 설치
https://aws.amazon.com/ko/cli/


## AWS 준비

- EC2 가 사용할 보안그룹을 하나 준비하고 해당 보안그룹아이디를 이용하여 EB 환경을 생성해야 합니다.
- RDS 인스턴스를 하나 생성하고 외부 접속을 허용한 다음 EC2가 사용할 보안그룹에도 MySQL 접속을 허용해줍니다.
- IAM에서 `aws-elasticbeanstalk-ec2-role` 에 S3 Full Access 등 해당 버킷의 쓰기 권한을 얼여줘야 합니다.


## Git

Git 설치
https://git-scm.com/book/ko/v2/시작하기-Git-설치

설치 후에

```zsh
git init
git add .
git commit -m "Initial Commit"
```

## Deployment

```zsh
eb init
```
