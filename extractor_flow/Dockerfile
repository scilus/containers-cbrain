FROM scilus/extractor_flow:1.1.0

RUN apt install -y python-apt -f
RUN cp /usr/lib/python3/dist-packages/apt_pkg.cpython-35m-x86_64-linux-gnu.so /usr/lib/python3/dist-packages/apt_pkg.cpython-37m-x86_64-linux-gnu.so

RUN add-apt-repository ppa:openjdk-r/ppa
RUN apt update
RUN apt -y install openjdk-11-jdk curl

WORKDIR /
RUN wget https://github.com/nextflow-io/nextflow/releases/download/v19.04.0/nextflow-19.04.0-all && mv nextflow-19.04.0-all nextflow && chmod +x nextflow
ENV PATH="/:${PATH}"

WORKDIR /
ENV EXTRACTORFLOW_VERSION="master"
RUN wget https://github.com/scilus/extractor_flow/archive/${EXTRACTORFLOW_VERSION}.zip
RUN unzip ${EXTRACTORFLOW_VERSION}.zip
RUN mv extractor_flow-${EXTRACTORFLOW_VERSION} extractorflow_flow
