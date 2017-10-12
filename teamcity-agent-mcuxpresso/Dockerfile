FROM jetbrains/teamcity-agent

COPY mcuxpressoide-10.0.2_411.x86_64.deb /mcuxpressoide-10.0.2_411.x86_64.deb

RUN DEBIAN_FRONTEND=noninteractive dpkg --add-architecture i386
RUN DEBIAN_FRONTEND=noninteractive apt-get update -qq
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y libncurses5:i386 libusb-1.0-0-dev dfu-util libwebkitgtk-1.0-0

RUN DEBIAN_FRONTEND=noninteractive dpkg --unpack /mcuxpressoide-10.0.2_411.x86_64.deb
COPY mcuxpressoide.postinst /var/lib/dpkg/info/mcuxpressoide.postinst
RUN DEBIAN_FRONTEND=noninteractive dpkg --configure mcuxpressoide
RUN DEBIAN_FRONTEND=noninteractive apt-get -fy install

RUN rm -f /mcuxpressoide-10.0.2_411.x86_64.deb
