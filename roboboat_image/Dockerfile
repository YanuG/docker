# docker image of ros kinetic
FROM osrf/ros:kinetic-desktop-full

# install ros packages, git and openssh-sever
RUN apt-get update && apt-get install -y \
    ros-kinetic-robot=1.3.2-0* \
    && rm -rf /var/lib/apt/lists/* && \
    apt-get update && \
    apt-get install -y git && \
    apt install -y openssh-server
    
# add directory for ssh keys
RUN mkdir /root/.ssh/

# copy private key docker container
ADD id_rsa /root/.ssh/id_rsa

# change permissions of the file to read, write and execute
RUN chmod 700 /root/.ssh/id_rsa

# disable strict host key checking for ssh
RUN echo "Host gitlab.com\n\tStrictHostKeyChecking no\n" >> /root/.ssh/config

# clone roboboat_workspace
RUN git clone git@gitlab.com:ottabotics-team/Roboboat/Software/roboboat_workspace.git

# run first time setup 
RUN  /roboboat_workspace/scripts/docker_first_time_setup.sh
