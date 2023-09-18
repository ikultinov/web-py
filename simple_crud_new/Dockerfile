FROM python:3.8

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFERED 1

WORKDIR /home/myuser/src/simple_crud
COPY ./requirements.txt /home/myuser/src/requirements.txt
RUN apt-get upgrade
RUN apt-get update
RUN pip install -r /home/myuser/src/requirements.txt

COPY . /home/myuser/src/simple_crud

ENV DEBUG=0
ENV SECRET_KEY=DSFGSDf89785rllfjdas--fuew8fyh!hkpfk6%p18-5$yljvrl^

EXPOSE 8000

RUN python manage.py migrate

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]