FROM python:3.8-slim

RUN apt-get update && apt-get install -y \
    git \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY app.py .

RUN mkdir templates
RUN mkdir static

COPY templates/ templates/
COPY static/ static/

ENV OPNSENSE_API_KEY=""
ENV OPNSENSE_API_SECRET=""
ENV OPNSENSE_IP=""

EXPOSE 5000

CMD ["flask", "run", "--host=0.0.0.0"]
