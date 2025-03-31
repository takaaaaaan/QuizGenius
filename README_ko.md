# 문제 생성 애플리케이션

이 애플리케이션은 텍스트나 이미지로부터 문제를 자동으로 생성하는 웹 애플리케이션입니다. Streamlit을 사용하여 구축되었으며, 다국어 지원과 AI를 활용한 문제 생성 기능을 제공합니다.

## 주요 기능

- 📝 문제 생성
  - 텍스트 기반 문제 생성
  - 이미지에서 텍스트 추출 및 문제 생성
  - 카메라를 사용한 실시간 이미지 캡처
- 🌐 다국어 지원
  - 한국어
  - 영어
  - 일본어
  - 중국어
  - 미얀마어
- 🎯 맞춤형 문제 설정
  - 문제 수
  - 문제 유형 (객관식, 빈칸 채우기, 서술형)
  - 난이도
  - 주제
  - 답변 형식
- 💾 데이터베이스 연동
  - 생성된 문제와 답변 저장
  - 기록 관리

## 필수 요구사항

- Python 3.10 이상
- MySQL 데이터베이스
- OpenAI API 키
- Google Cloud Vision API 키

## 설치 방법

1. 저장소 복제
```bash
git clone [repository-url]
cd [repository-name]
```

2. 가상환경 생성 및 활성화
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows
```

3. 필요한 패키지 설치
```bash
pip install -r requirements.txt
```

4. 데이터베이스 설정
- MySQL 데이터베이스 생성
- 다음 테이블 생성:
```sql
CREATE TABLE moning (
    id INT AUTO_INCREMENT PRIMARY KEY,
    Quiz_text TEXT,
    Quiz_trans TEXT,
    Quiz_qust TEXT,
    Quiz_ans TEXT
);
```

5. 환경 변수 설정
- OpenAI API 키 설정
- Google Cloud Vision API 키 설정

## 사용 방법

1. 애플리케이션 실행
```bash
streamlit run Generator.py
```

2. 브라우저에서 http://localhost:8501 접속

3. 사이드바에서 기능 선택:
   - 📝문제 만들기: 문제 생성
   - 📄📱🎨Demo Page: 데모 페이지
   - Code Page: 코드 표시

## 프로젝트 구조

```
.
├── Generator.py      # 메인 애플리케이션 파일
├── page1.py         # 문제 생성 페이지
├── page2.py         # 데모 페이지
├── page3.py         # 코드 표시 페이지
├── requirements.txt # 의존성 패키지 목록
└── README.md        # 이 파일
```

## 주의사항

- API 키는 적절히 관리하고 공개하지 마세요
- 데이터베이스 연결 정보는 환경에 맞게 설정하세요
- 이미지 처리 기능을 사용할 경우 카메라 접근 권한이 필요합니다

## 라이선스

이 프로젝트는 MIT 라이선스로 공개되어 있습니다. 