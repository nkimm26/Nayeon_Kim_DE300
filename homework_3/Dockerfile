FROM jupyter/datascience-notebook

WORKDIR /home/jovyan

EXPOSE 8888

ENV DEBIAN_FRONTEND=noninteractive

COPY . .

USER root

RUN apt-get update && apt-get install -y \
    wget \
    curl \
    unzip \
    bzip2 \
    git \
    && rm -rf /var/lib/apt/lists/*

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && \
    unzip awscliv2.zip && \
    ./aws/install && \
    rm -rf awscliv2.zip ./aws
USER jovyan

CMD ["start-notebook.sh", "--NotebookApp.token=''", "--NotebookApp.password=''", "--allow-root"]

