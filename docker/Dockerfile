FROM python:3

RUN apt-get update && apt-get install --no-install-recommends -y \
     libspatialindex-dev \
     unzip && \
     rm -rf /var/lib/apt/lists/*

COPY nbs/requirements.txt /tmp/requirements.txt
RUN pip install -r /tmp/requirements.txt

WORKDIR /opt/src

ENTRYPOINT [ "jupyter" ]
CMD [ "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root", "--notebook-dir=/opt/jupyter" ]
