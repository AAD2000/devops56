FROM ubuntu:latest

WORKDIR /wkr

RUN apt-get update -y 
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y cmake g++ python3 python3-pip 
RUN apt-get clean 
RUN apt-get autoremove

RUN pip install flask


COPY . /wkr

RUN cmake . 
RUN make

RUN useradd techproguser
USER techproguser

EXPOSE 5000
ENTRYPOINT python3 -m flask run --host=0.0.0.0 
