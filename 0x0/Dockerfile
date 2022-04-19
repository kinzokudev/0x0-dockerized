FROM python:3.10

WORKDIR /app

COPY . /app

RUN pip install --no-cache-dir -r requirements.txt

CMD flask db upgrade; \
	uwsgi --socket 0.0.0.0:8080 --wsgi-file fhost.py --callable app --processes 4 --threads 2
