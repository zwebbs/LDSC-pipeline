FROM python:2

WORKDIR /usr/src/app

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt
RUN git clone https://github.com/bulik/ldsc.git
workdir /usr/src/app/ldsc/

CMD [ "python"]
