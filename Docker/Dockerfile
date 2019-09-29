FROM jenkins/jenkins:2.176.3

ENV ANDROID_HOME /Android/sdk
ENV PATH $PATH:$ANDROID_HOME/bin

USER root
RUN apt update -y && \
    apt upgrade -y && \
    apt install -y wget unzip

WORKDIR /Android/sdk
RUN wget "https://dl.google.com/android/repository/sdk-tools-linux-4333796.zip" && \
    unzip ./sdk-tools-linux-4333796.zip && \
    rm ./sdk-tools-linux-4333796.zip && \
    yes | ./tools/bin/sdkmanager "build-tools;28.0.3" "platform-tools" "platforms;android-28"
