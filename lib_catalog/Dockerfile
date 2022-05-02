FROM python:3.8-slim
RUN groupadd --gid 5001 touser \
    && useradd --home-dir /home/touser --create-home --uid 5001 \
        --gid 5001 --shell /bin/sh --skel /dev/null touser

USER touser
WORKDIR /app
COPY ./requirements.txt /app/requirements.txt
RUN pip install -r requirements.txt
COPY . ./
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
