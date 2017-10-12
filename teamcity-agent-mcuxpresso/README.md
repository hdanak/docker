## teamcity-agent-mcuxpresso

#### Note: You'll need to download the `mcuxpressoide-10.0.2_411.x86_64.deb.bin` package from NXP.

    mkdir mcuxpresso
    chmod +x mcuxpressoide-10.0.2_411.x86_64.deb.bin
    ./mcuxpressoide-10.0.2_411.x86_64.deb.bin --noexec --keep --target mcuxpresso
    mv mcuxpresso/mcuxpressoide-10.0.2_411.x86_64.deb .
    docker build .
