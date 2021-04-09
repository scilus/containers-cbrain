FROM scilus/dmriqc_flow:latest

# RUN apt install -y python-apt -f
RUN apt-get install -y software-properties-common
RUN apt-get install -y wget
RUN apt-get install -y unzip

RUN add-apt-repository ppa:openjdk-r/ppa
RUN apt update
RUN apt -y install openjdk-11-jdk curl

WORKDIR /
RUN wget https://github.com/nextflow-io/nextflow/releases/download/v19.04.0/nextflow-19.04.0-all && mv nextflow-19.04.0-all nextflow && chmod +x nextflow
ENV PATH="/:${PATH}"

WORKDIR /
ENV DMRIQC_FLOW_VERSION="0.1.0"
RUN wget https://github.com/GuillaumeTh/dmriqc-flow/archive/${DMRIQC_FLOW_VERSION}.zip
RUN unzip ${DMRIQC_FLOW_VERSION}.zip
RUN mv dmriqc-flow-${DMRIQC_FLOW_VERSION} dmriqc_flow

WORKDIR /
