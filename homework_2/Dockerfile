FROM jupyter/base-notebook

COPY ./home/jovyan/work/

WORKDIR /home/jovyan/work

RUN apt-get update && apt-get install -y git

EXPOSE 8888

CMD ["start-notebook.sh", "--NotebookApp.token=''", "--NotebookApp.password=''", "--ip=0.0.0.0", "--port=8888", "--no-browser"]


