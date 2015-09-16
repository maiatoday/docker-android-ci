#
# maiatoday/jenkins_android
#

FROM jenkins:latest
MAINTAINER maiatoday <maiatoday@gmail.com>

RUN apt-get update && apt-get -y install libstdc++6 lib32z1 lib32stdc++6 expect

# Android config
RUN curl -3L https://raw.github.com/embarkmobile/android-sdk-installer/version-2/android-sdk-installer | bash /dev/stdin --install=tools,platform-tools,build-tools-23.0.1,android-23,android-20,android-19,extra-android-support,extra-android-m2repository --dir=/opt --accept="android-sdk-license-5be876d5|android-sdk-preview-license-52d11cd2"
RUN rm /opt/android-sdk*linux.tgz
ENV ["ANDROID_HOME", "/opt/android-sdk-linux"]
