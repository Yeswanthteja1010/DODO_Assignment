FROM python:3.12-slim

WORKDIR /app

RUN groupadd -g 10001 appgroup && \
    useradd -u 10001 -g appgroup -s /sbin/nologin appuser

COPY app/requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY app/app.py .

RUN chown -R appuser:appgroup /app

USER 10001:10001

EXPOSE 8080

CMD ["python", "app.py"]
