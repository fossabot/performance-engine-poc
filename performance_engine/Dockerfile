FROM python:3.7.0

WORKDIR /usr/src/

RUN apt-get update && apt-get -y install jq

COPY requirements.txt requirements.dev.txt /usr/src/

RUN pip install --no-cache-dir -r requirements.dev.txt

RUN pip --no-cache-dir install --upgrade awscli

ENV FBN_LUSID_API_URL ${FBN_LUSID_API_URL}

ENTRYPOINT PYTHONPATH=/usr/src/:/usr/src/tests python -m pytest