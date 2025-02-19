# FastAPI Beyond CRUD 

This is the source code for the [FastAPI Beyond CRUD](https://youtube.com/playlist?list=PLEt8Tae2spYnHy378vMlPH--87cfeh33P&si=rl-08ktaRjcm2aIQ) course. The course focuses on FastAPI development concepts that go beyond the basic CRUD operations.

For more details, visit the project's [website](https://jod35.github.io/fastapi-beyond-crud-docs/site/).

## Assignment 7
### For videos, pls check Actions work flow

First, create conventional_commits.yml to check if commits are valid
    a. check pr title 
    b. check pr commit

Second, create nightly_build.yml to check if the projects works
    a. docker build up
    b. doing data migration
    c. run test
    d. deploy on docker registry

Third, making project run in local
    update '.env.example' file:
        DATABASE_URL=postgresql+asyncpg://postgres:testpass@db:5432/bookly
        JWT_SECRET=hYW3L6I3gPpEUbtU+17FEHRYJuc8uLYHaLLsuzzyKn4=
        JWT_ALGORITHM=HS256
        REDIS_HOST=redis
        REDIS_PORT=6379
        REDIS_URL=redis://redis:6379/0
        MAIL_USERNAME=marcelle.vonrueden72@ethereal.email
        MAIL_PASSWORD=Z75RUTaWnGs2ytv7bX
        MAIL_SERVER=smtp.ethereal.email
        MAIL_PORT=587 
        MAIL_FROM=nore-reply@bookly.com
        MAIL_FROM_NAME=Tingxuan
        DOMAIN=localhost:8000   

1. Clone the project repository:
    ```bash
    git clone https://github.com/jod35/fastapi-beyond-CRUD.git
    ```
   
2. Navigate to the project directory:
    ```bash
    cd fastapi-beyond-CRUD/
    ```

3. Create and activate a virtual environment:
    ```bash
    python3 -m venv env
    source env/bin/activate
    ```

4. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

5. Set up environment variables by copying the example configuration:
    ```bash
    cp .env.example .env
    ```

6. Run Data Migration
   ```bash
    docker exec fastapi-beyond-crud-web-1 alembic upgrade head
    ```

7. Run test
   ```bash
   docker exec fastapi-beyond-crud-web-1 pip install pytest
   docker exec fastapi-beyond-crud-web-1 pytest
   ```
8. End
   ```bash
   docker compose down
   ```
    
