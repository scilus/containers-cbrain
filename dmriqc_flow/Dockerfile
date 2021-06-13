FROM scilus/dmriqcpy:0.1.5-rc8

RUN apt install -y python3-apt -f
RUN cp /usr/lib/python3/dist-packages/apt_pkg.cpython-36m-x86_64-linux-gnu.so /usr/lib/python3/dist-packages/apt_pkg.cpython-37m-x86_64-linux-gnu.so

RUN apt update
RUN apt -y install software-properties-common
RUN add-apt-repository ppa:openjdk-r/ppa
RUN apt update
RUN apt -y install openjdk-11-jdk curl

RUN apt -y install wget unzip

WORKDIR /
RUN wget https://github.com/nextflow-io/nextflow/releases/download/v19.04.0/nextflow-19.04.0-all && mv nextflow-19.04.0-all nextflow && chmod +x nextflow
ENV PATH="/:${PATH}"

WORKDIR /
ENV DMRIQCFLOW_VERSION="master"
RUN wget https://github.com/scilus/dmriqc_flow/archive/${DMRIQCFLOW_VERSION}.zip
RUN unzip ${DMRIQCFLOW_VERSION}.zip
RUN mv dmriqc_flow-${DMRIQCFLOW_VERSION} dmriqc_flow
