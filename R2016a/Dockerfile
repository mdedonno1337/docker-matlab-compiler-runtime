FROM debian

RUN apt update && \
    apt install -y curl wget unzip libncurses5-dev libncursesw5-dev

ADD inputs.txt /tmp/mcr/inputs.txt

RUN cd /tmp/mcr && \
    wget --progress=bar:force https://fr.mathworks.com/supportfiles/downloads/R2016a/deployment_files/R2016a/installers/glnxa64/MCR_R2016a_glnxa64_installer.zip && \
    unzip MCR_R2016a_glnxa64_installer.zip && \
    ./install -inputFile inputs.txt && \
    cd /tmp && \
    rm -rf mcr

ENV LD_LIBRARY_PATH=.:/usr/local/MATLAB_Runtime/v901/runtime/glnxa64:/usr/local/MATLAB_Runtime/v901/bin/glnxa64:/usr/local/MATLAB_Runtime/v901/sys/os/glnxa64:/usr/local/MATLAB_Runtime/v901/sys/opengl/lib/glnxa64
