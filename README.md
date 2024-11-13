```markdown
# postgres_python

## 개요
Python으로 PostgreSQL 데이터베이스를 안전하고 효율적으로 다루는 예제 저장소입니다.

## 설치 요소
```bash
pip install -r requirements.txt

```

### requirements.txt

```
psycopg2-binary==2.9.9
python-dotenv==1.0.0

```

## 주요 기능

### SQL Injection 방지

- 파라미터화된 쿼리 사용
- 사용자 입력값 검증
- 안전한 데이터베이스 접근

### 모듈화된 데이터베이스 클래스

```python
class DB:
    def __init__(self, db_host, db_name, db_port, db_pwd, db_user):
        self.conn_params = {
            'dbname': db_name,
            'user': db_user,
            'port': db_port,
            'password': db_pwd,
            'host': db_host,
        }
        self.connect()

```

### 기본 CRUD 작업

```python
# Create (데이터 생성)
db.insert(name, age)

# Read (데이터 조회)
db.read_datas()  # 전체 조회
db.read_data_with_condition(name)  # 조건부 조회

# Update (데이터 수정)
db.update_data()  # 나이 정보 수정

# Delete (데이터 삭제)
db.delete_data()  # 이름으로 데이터 삭제

```

## 사용 예시

```python
# DB 연결
db = DB(db_host, db_name, db_port, db_pwd, db_user)

# 데이터 추가
name = input("이름을 입력하세요 : ")
age = input("나이를 입력하세요 : ")
db.insert(name, age)

# 전체 데이터 조회
db.read_datas()

# DB 연결 종료
db.close()

```

## 프로젝트 구조

```
postgres_python/
├── modules/
│   └── __init__.py
├── utils/
│   └── __init__.py
├── .env
├── requirements.txt
└── README.md

```

## 라이선스

MIT License

```

```