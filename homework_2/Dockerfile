```Dockerfile
FROM jupyter/base-notebook:latest

USER root

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
      git \
      openssh-client \
      curl && \
    rm -rf /var/lib/apt/lists/*

RUN pip install --no-cache-dir cassandra-sigv4 boto3

RUN mkdir -p /home/jovyan/.certs && \
    curl -sSL https://certs.secureserver.net/repository/sf-class2-root.crt \
         -o /home/jovyan/.certs/sf-class2-root.crt && \
    chown -R jovyan:users /home/jovyan/.certs

USER jovyan

WORKDIR /home/jovyan/work

EXPOSE 8888

CMD ["start-notebook.sh", "--NotebookApp.token=''", "--NotebookApp.notebook_dir=/home/jovyan/work"]
```


