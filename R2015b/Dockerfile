FROM debian

RUN apt update && \
    apt install -y curl wget unzip libncurses5-dev libncursesw5-dev

RUN mkdir /install && \
	cd /install && \
    wget --progress=bar:force https://fr.mathworks.com/supportfiles/downloads/R2015b/deployment_files/R2015b/installers/glnxa64/MCR_R2015b_glnxa64_installer.zip && \
    unzip MCR_R2015b_glnxa64_installer.zip && \
    ./install -mode silent -agreeToLicense yes -destinationFolder /usr/local/MATLAB_Runtime/ && \
    cd / && \
    rm -rf install

ENV LD_LIBRARY_PATH=.:/usr/local/MATLAB_Runtime/v90/runtime/glnxa64:/usr/local/MATLAB_Runtime/v90/bin/glnxa64:/usr/local/MATLAB_Runtime/v90/sys/os/glnxa64:/usr/local/MATLAB_Runtime/v90/sys/opengl/lib/glnxa64
