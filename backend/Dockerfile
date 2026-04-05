FROM python:3.11-slim

# создаём пользователя
RUN useradd -m appuser

WORKDIR /app

COPY app.py .

# ставим curl для healthcheck
RUN apt-get update && apt-get install -y curl && rm -rf /var/lib/apt/lists/*

USER appuser

EXPOSE 8080

ENTRYPOINT ["python"]

CMD ["app.py"]