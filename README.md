# Instruction on installation

**1. Dependencies**

1.1. Check Python installation

python --version

If it's not installed, please install Python from official site.

1.2. Check 'pip' installation

python -m pip --version

If it's not installed write the following

python -m ensurepip --default-pip
python -m pip install --upgrade pip

1.3. Install all dependencies

pip install fastapi[all] sqlalchemy passlib bcrypt jwt

This command will install:
-FastAPI – API framework
-Uvicorn – server for API loading
-SQLAlchemy – for work with DB
-Passlib (bcrypt) – password hashing
-JWT (pyjwt) – authentification with tokens

2. API starting

Start API from main.py

cd /d D:/Example/Test (main.py folder path)
uvicorn main:app --reload

Now server is open at http://127.0.0.1:8000

3. Test with Postman application

3.1. POST /register

-Follow URL http://127.0.0.1:8000/register

-In the Body -> raw -> JSON write:

{
    "email": "example@gmail.com",
    "password": "qwerty"
}

![image](https://github.com/user-attachments/assets/35324db1-62df-4700-8866-63ca7695a426)

-Click 'Send'

-Server answer should be:
![image](https://github.com/user-attachments/assets/052215c1-9796-4fd5-b4ae-d69362c17365)

3.2. POST /login

-Follow URL http://127.0.0.1:8000/login

-In the Body -> x-www-form-urlencoded:
![image](https://github.com/user-attachments/assets/78dbeeb2-1653-47e1-812a-8a2308ba67c6)

-Click 'Send'

-Server answer should be:
![image](https://github.com/user-attachments/assets/1272ddf0-b113-4272-af3a-ca593605cf6b)

3.3. GET /private-data

-Follow URL http://127.0.0.1:8000/private-data

-In the Headers:
-In Authorization field write: Bearer YOUR_TOKEN
![image](https://github.com/user-attachments/assets/3cd8ad4f-2954-41f6-bc50-1f760d9545fc)

-Click 'Send'

-Server answer should be:
![image](https://github.com/user-attachments/assets/22755956-d456-4e67-83b6-03cacc8c382d)

3.4. GET /public-data

-Follow URL http://127.0.0.1:8000/public-data

-Click 'Send'

-Server answer should be:
![image](https://github.com/user-attachments/assets/791eb0e8-2f18-4fa4-bccf-66a96983f640)

