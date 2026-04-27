FROM python:3.12-slim

# tránh tạo file .pyc + log buffer
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

WORKDIR /app

# copy dependency trước để cache
COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

# copy source code
COPY app/ app/

EXPOSE 5000

CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "5000"]