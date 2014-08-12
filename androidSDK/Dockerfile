#
# maiatoday/android-sdk
#

FROM maiatoday/java7
MAINTAINER maiatoday &lt;maiatoday@gmail.com&gt;

#with thanks to Paul Cambell &lt;pcampbell@kemitix.net&gt;

#
# Contains:
#  - wget
#  - unzip
#  - git
#  - git-flow
#  - git-gui
#  - gitk
#  - meld
#  - bash-completion
#

ENV DEBIAN_FRONTEND noninteractive

# Dependencies
RUN dpkg --add-architecture i386
RUN apt-get update
RUN apt-get install -y --no-install-recommends \
		wget \
		unzip \
		git \
		git-flow \
		git-gui \
		gitk \
		meld \
		bash-completion

WORKDIR /opt

# Main Android SDK
# - 23.0.2 is the latest version that can be downloaded directly
RUN wget -q http://dl.google.com/android/android-sdk_r23.0.2-linux.tgz
RUN tar xzf android-sdk_r23.0.2-linux.tgz
RUN chown -R root:root .
RUN rm -f android-sdk_r23.0.2-linux.tgz

# Other tools and resources of Android SDK
ENV ANDROID_HOME /opt/android-sdk-linux
ENV PATH $PATH:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools

# Android SDK Tools, revision 23.0.2
RUN wget -q http://dl-ssl.google.com/android/repository/tools_r23.0.2-linux.zip
RUN unzip -q tools_r23.0.2-linux.zip
RUN rm -f tools_r23.0.2-linux.zip

# Fix i386 loader
RUN apt-get install -y \
		libc6:i386 \
		libgcc1:i386 \
		gcc-4.6-base:i386 \
		libstdc++5:i386 \
		libstdc++6:i386

# FIX ia32-libs dependancies
RUN apt-get install -y \
		lib32z1 \
		lib32ncurses5 \
		lib32bz2-1.0

# Update path to include Build-tools
RUN echo &quot;\n\
export ANDROID_HOME=/opt/android-sdk-linux\n\
export PATH=\$PATH:\
\$ANDROID_HOME/tools:\
\$ANDROID_HOME/build-tools/19.1.0:\
\$ANDROID_HOME/platform-tools&quot; \
	&gt;&gt; /etc/profile

# now that we&#39;ve populated the directory, export it as a volume
VOLUME [&quot;/opt/android-sdk-linux&quot;]
