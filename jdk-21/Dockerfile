# Use the official Ubuntu 24.04 as a base image
FROM ubuntu:24.04

# Set environment variables
ENV JAVA_VERSION=7u80
ENV JAVA_HOME=/usr/lib/jvm/java-1.7.0-openjdk-amd64
RUN apt-get update && apt-get install -y \
    software-properties-common \
    wget \
    curl \
    apt-utils 
RUN add-apt-repository ppa:openjdk-r/ppa \
    && apt-get update \
    && apt-get install -y openjdk-21-jdk
RUN wget https://archive.apache.org/dist/maven/maven-3/3.8.3/binaries/apache-maven-3.8.3-bin.tar.gz \
    && tar xzvf apache-maven-3.8.3-bin.tar.gz -C /opt \
    && ln -s /opt/apache-maven-3.8.3 /opt/maven \
    && rm apache-maven-3.8.3-bin.tar.gz
ENV JAVA_HOME=/usr/lib/jvm/java-1.21.0-openjdk-amd64
ENV M2_HOME=/opt/maven
ENV MAVEN_HOME=/opt/maven
ENV PATH=${M2_HOME}/bin:${PATH}
RUN java -version && mvn -version
# Default command
CMD ["bash"]