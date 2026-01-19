# start by pulling the python image
FROM python:3.8-alpine

# switch working directory
WORKDIR /app


# copy the requirements file into the image
COPY ./requirements.txt requirements.txt
COPY ./view.py view.py
COPY ./templates/ templates/

RUN python -m venv venv
ENV PATH=/app/venv:$PATH

# install the dependencies and packages in the requirements file
RUN pip install -r requirements.txt

# configure the container to run in an executed manner

ENTRYPOINT ["python" ]

CMD ["view.py" ]
