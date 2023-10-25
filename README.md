## Django로 개발한 나만의 Twitter 배포

MVT패턴을 적용한 간단한 SNS 서비스를 DRF APIView로 구현하고<br>
백앤드 인스턴스와 DB 인스턴스를 연결한 프로젝트입니다.<br>
CI/CD 자동화로 배포시 자동으로 서비스의 버전업이 가능합니다.<br><br>
<img src="https://github.com/bainaryho/catalogueApp/assets/90160898/20181f67-b4e1-4b07-a6c5-b2c476a0d23b" width="800" height="350">
<img src="https://github.com/bainaryho/DjangoSNS/assets/90160898/0f0b9da7-1541-4a0c-85db-a9dc7b06083c" width="200" height="200">


### 라이브러리 버전
Django 4.2.3  
postgresql 13  
gunicorn 21.2.0  
psycopg2-binary 2.9.7  
djangorestframework 3.14.0  
drf-spectacular 0.26.4  
python-dotenv 0.19.1  

### **1. 백엔드 DB 설계**  
  
- Django 모델을 사용하여 게시글과 유저를 생성
- Django의 ORM을 사용하여 모델 간의 관계를 정의하고 데이터베이스를 마이그레이션
  
### **2. 백엔드 API 개발**  
  
- Django REST framework를 사용하여 필요한 API 엔드포인트를 개발
- 사용자, 게시글과 관련된 API를 구현
- API에 대한 권한과 인증을 설정하여 사용자만이 해당 기능을 사용할 수 있도록 합니다.  
   
### **3. 배포**  
  
- Django 프로젝트를 NCP 클라우드 서비스에 배포
- 웹 서버 Gunicorn, 리버스 프록시 Nginx를 설정하여 프로덕션 환경에 배포
- 서버에서 환경 변수를 설정하여 중요한 정보를 안전하게 관리
  
### **4. CICD Pipeline 작성**  

#### **CICD 확인 : https://github.com/bainaryho/DjangoSNS/commits/master**
  
- GitHub Actions CI/CD 도구를 사용하여 CI/CD 파이프라인을 설정
- 코드가 GitHub 리포지토리에 푸시될 때 테스트를 자동으로 실행하도록 설정
