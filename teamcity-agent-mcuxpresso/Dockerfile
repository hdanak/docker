FROM jetbrains/teamcity-agent

ARG deb_pkg=mcuxpressoide-10.1.0_589.x86_64.deb
COPY $deb_pkg /$deb_pkg

RUN DEBIAN_FRONTEND=noninteractive dpkg --add-architecture i386
RUN DEBIAN_FRONTEND=noninteractive apt-get update -qq
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y libncurses5:i386 libusb-1.0-0-dev dfu-util libwebkitgtk-1.0-0

RUN DEBIAN_FRONTEND=noninteractive dpkg --unpack /$deb_pkg
COPY mcuxpressoide.postinst /var/lib/dpkg/info/mcuxpressoide.postinst
RUN DEBIAN_FRONTEND=noninteractive dpkg --configure mcuxpressoide
RUN DEBIAN_FRONTEND=noninteractive apt-get -fy install

RUN rm -f /$deb_pkg
