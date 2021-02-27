FROM scilus/docker-tractoflow:latest

WORKDIR /
RUN wget https://github.com/nextflow-io/nextflow/releases/download/v19.04.0/nextflow-19.04.0-all && mv nextflow-19.04.0-all nextflow && chmod +x nextflow
ENV PATH="/:${PATH}"

WORKDIR /
ENV TRACTOFLOW_VERSION="2.1.2"
RUN wget https://github.com/scilus/tractoflow/archive/${TRACTOFLOW_VERSION}.zip
RUN unzip ${TRACTOFLOW_VERSION}.zip
RUN mv tractoflow-${TRACTOFLOW_VERSION} tractoflow

WORKDIR /
