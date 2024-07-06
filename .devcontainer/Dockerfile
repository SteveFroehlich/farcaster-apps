FROM python:3.11-slim

WORKDIR /python-docker

# Install ps and curl
RUN apt-get update && \
    apt-get install -y procps curl git && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
EXPOSE 80
EXPOSE 443

COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt

COPY ../ .

CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0"]
