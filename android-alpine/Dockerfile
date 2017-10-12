FROM openjdk:8-jre-alpine

ENV ANDROID_HOME /opt/android-sdk-linux

RUN apk update
RUN apk add unzip wget bash

RUN mkdir -p ${ANDROID_HOME} \
    && wget -q https://dl.google.com/android/repository/tools_r25.2.5-linux.zip -O android-sdk-tools.zip \
    && unzip -q android-sdk-tools.zip -d ${ANDROID_HOME} \
    && rm -f android-sdk-tools.zip

ENV PATH ${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/tools/bin:${ANDROID_HOME}/platform-tools
ENV LD_LIBRARY_PATH ${LD_LIBRARY_PATH}:${ANDROID_HOME}/tools/lib64

# accept licenses
RUN mkdir -p ${ANDROID_HOME}/licenses
RUN echo 8933bad161af4178b1185d1a37fbf41ea5269c55 > ${ANDROID_HOME}/licenses/android-sdk-license

RUN sdkmanager "platform-tools"
RUN sdkmanager "platforms;android-26"
RUN sdkmanager "build-tools;26.0.0"

#RUN sdkmanager "system-images;android-25;google_apis;armeabi-v7a"
#RUN sdkmanager "system-images;android-24;default;armeabi-v7a"

# Extras
RUN sdkmanager "extras;android;m2repository"
RUN sdkmanager "extras;google;m2repository"
RUN sdkmanager "extras;google;google_play_services"
RUN sdkmanager "extras;m2repository;com;android;support;constraint;constraint-layout;1.0.2"
RUN sdkmanager "add-ons;addon-google_apis-google-23"
