## 프론트엔드 배포 파이프라인
GitHub Actions에 워크플로우를 작성해 다음과 같이 배포가 진행되도록 합니다.

1. 저장소를 체크아웃합니다.
2. Node.js 18.x 버전을 설정합니다.
3. 프로젝트 의존성을 설치합니다.
4. Next.js 프로젝트를 빌드합니다.
5. AWS 자격 증명을 구성합니다.
6. 빌드된 파일을 S3 버킷에 동기화합니다.
7. CloudFront 캐시를 무효화합니다.

## 주요 링크

- S3 버킷 웹사이트 엔드포인트: http://hanghaehjw.s3-website.eu-north-1.amazonaws.com
- CloudFrount 배포 도메인 이름: https://d2bgszo93ozg92.cloudfront.net

## 주요 개념
- GitHub Actions : GitHub Actions는 GitHub에서 제공하는 자동화 플랫폼으로, CI/CD 작업을 쉽게 설정할 수 있도록 도와줍니다.
- CI/CD : CI/CD는 **Continuous Integration(지속적 통합)**과 **Continuous Delivery/Deployment(지속적 전달/배포)**의 약자입니다.
    - Jenkins
    오픈소스 CI/CD 서버로 매우 유연한 설정 가능.
    수많은 플러그인 지원으로 확장 가능.
    단점: 설치 및 유지 관리가 필요.
    - CircleCI
    클라우드 기반 및 온프레미스 모두 지원.
    빠른 빌드 속도와 간단한 설정으로 인기.
    GitHub와 GitLab 통합 지원.
   - Travis CI
    GitHub 프로젝트에 CI/CD를 빠르게 추가할 수 있는 도구.
    설정 파일 .travis.yml을 통해 정의.
    오픈소스 프로젝트에 무료.
    - GitLab CI/CD
    GitLab에서 제공하는 내장 CI/CD 도구.
    GitLab 리포지토리와 완벽히 통합.
   - Azure DevOps
    Microsoft에서 제공하는 클라우드 DevOps 플랫폼.
    GitHub과도 통합 가능.
    - Bitbucket Pipelines
    Atlassian의 Bitbucket에 내장된 CI/CD 도구.
    GitHub Actions와 유사한 파이프라인 설정 가능.
   - TeamCity
    JetBrains에서 제공하는 CI/CD 도구.
    코드 품질 관리 도구와 쉽게 통합 가능.
- S3 : Amazon Simple Storage Service (S3)**는 오브젝트 스토리지 서비스입니다. AWS(Amazon Web Services)에서 제공하며, 인터넷을 통해 데이터를 안전하게 저장, 관리, 액세스할 수 있도록 설계되었습니다.
- 스토리지: 스토리지는 데이터를 저장하는 기술이나 시스템을 의미합니다. 컴퓨터에서 파일, 데이터베이스, 미디어 등 모든 종류의 데이터를 저장하고 필요할 때 접근할 수 있도록 지원합니다.
- CloudFront : Amazon CloudFront는 AWS에서 제공하는 **글로벌 콘텐츠 전송 서비스(CDN)**입니다. CloudFront는 사용자가 웹사이트, 애플리케이션, 스트리밍 비디오, 또는 API에 빠르게 접근할 수 있도록 콘텐츠를 캐싱하고, 보안을 강화하며, 네트워크 지연을 줄이는 데 도움을 줍니다.
- CDN: CDN(Content Delivery Network)**는 전 세계적으로 분산된 서버 네트워크를 이용해 콘텐츠를 사용자에게 빠르고 효율적으로 제공하는 기술입니다. CDN은 웹 페이지, 이미지, 비디오, CSS, JavaScript 등 정적 및 동적 콘텐츠를 캐싱하여 사용자와 가까운 서버에서 제공함으로써 성능을 최적화합니다.
## BASIC
## 배포 파이프라인을 설명하는 다이어그램과 설명
![제목 없는 다이어그램](https://github.com/user-attachments/assets/ac8efcf9-be5d-4f99-8f81-27ba0ac2902d)

GitHub Actions에 워크플로우를 작성해 다음과 같이 배포가 진행되도록 합니다.
1. 저장소를 체크아웃합니다.
2. Node.js 18.x 버전을 설정합니다.
3. 프로젝트 의존성을 설치합니다.
4. Next.js 프로젝트를 빌드합니다.
5. AWS 자격 증명을 구성합니다.
6. 빌드된 파일을 S3 버킷에 동기화합니다.
7. CloudFront 캐시를 무효화합니다.
## ADVANCED
## CDN 도입 전과 도입 후의 성능 개선 보고서 작성
AS-IS : S3
![성능 개선 전](https://github.com/user-attachments/assets/04408559-af19-4766-8a2a-d893e9846fc0)
TO-BD : Cloudfront
![성능개선 후](https://github.com/user-attachments/assets/917f471a-1dc4-4fe4-9a48-3427d8b03f0d)

|제목|내용|설명|
|------|---|---|
|테스트1|테스트2|테스트3|
|테스트1|테스트2|테스트3|
|테스트1|테스트2|테스트3|

