FROM python:3.12-slim

RUN apt-get update && apt-get install -y \
    git \
    curl

RUN mkdir /app/

COPY . /app/

WORKDIR /app

RUN pip3 install -r requirements.txt

# Make port 5000 available to the world outside this container
EXPOSE 5000

# Define environment variable
ENV FLASK_APP=app.py
ENV FLASK_RUN_HOST=0.0.0.0

RUN echo 'starting up'

# Run app.py when the container launches
CMD ["flask", "run"]
