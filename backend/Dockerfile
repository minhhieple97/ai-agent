FROM python:3.13.6-alpine3.22

RUN apk update && apk add curl


ENV PATH=/opt/venv/bin:$PATH
WORKDIR /app


RUN python -m venv /opt/venv/


COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt


COPY ./src .


CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]