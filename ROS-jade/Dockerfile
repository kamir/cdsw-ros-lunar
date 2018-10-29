# Dockerfile
FROM cloudera-cdsw-docker-repo.jfrog.io/cdsw/engine:1

MAINTAINER Mirko Kämpf "mirko@cloudera.com"

# update packages and install maven
RUN apt-get update && \
    apt-get install -y -q gnuplot vim wget curl maven mc&& \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
    
RUN sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

RUN apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 421C365BD9FF1F717815A3895523BAEEB01FA116

RUN apt-get update && \
    apt-get install -y -q ros-jade-ros-base && \
    rosdep init && \
    rosdep update
    
RUN echo "source /opt/ros/jade/setup.bash" >> /home/cdsw/.bashrc
  
RUN apt-get -y -q install python-rosinstall ros-jade-ros-tutorials





#
#To be addeded:
#==============
#
#sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
#apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 421C365BD9FF1F717815A3895523BAEEB01FA116
#apt-get update
#apt-get install ros-lunar-ros-base
#rosdep init
#rosdep update
#echo "source /opt/ros/lunar/setup.bash" >> /home/cdsw/.bashrc
#apt-get install python-rosinstall
#apt-get install ros-lunar-ros-tutorials
