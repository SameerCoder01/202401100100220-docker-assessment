FROM python:3.13-slim-trixie
ENV PYTHONDONTWRITEBYTECODE=1 PYTHONUNBUFFERED=1
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt     && groupadd --gid 10001 app     && useradd --uid 10001 --gid app --no-create-home app
COPY --chown=app:app app.py .
ARG APP_VERSION=0.2
ENV APP_VERSION=${APP_VERSION}
USER 10001:10001
EXPOSE 5000
CMD ["python", "app.py"]
