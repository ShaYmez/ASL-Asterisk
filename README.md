# Asterisk Source for AllStarLink

This is the Asterisk source package for AllStarLink and the files to build the ASL 2.0.0+ distribution.

---------------------------------------------------------------------------------------------------------------------------------

AllStarLink Wiki: https://wiki.allstarlink.org

AllStarLink Community Forum: https://community.allstarlink.org/

AllStarLink Portal:  https://www.allstarlink.org

AllStarLink Node Stats:  https://stats.allstarlink.org

---------------------------------------------------------------------------------------------------------------------------------

## Prerequisites

#### Debian 10 Buster

* Install the ASL Repo

<pre>
echo "deb http://apt.allstarlink.org/repos/asl_builds buster main" > /etc/apt/sources.list.d/allstar.list
curl -s http://apt.allstarlink.org/repos/repo_signing.key | sudo apt-key add -
apt update</pre>
</pre>

* Alternative Repo install for both Debian 10 or Debian 11
<pre>
apt update
apt install curl gpg

# If 10 Repo installed, remove from lists.
rm /etc/apt/sources.list.d/allstar.list   

cd /tmp
wget http://apt.allstarlink.org/repos/asl_builds/install-allstarlink-repository
chmod +x install-allstarlink-repository
./install-allstarlink-repository
apt update
</pre>

* Install apt dependencies
```
apt -y install \
  asl-dahdi-source \
  build-essential \
  cmake \
  devscripts \
  doxygen \
  freetds-dev \
  g++ \
  git \
  graphviz \
  gsfonts \
  libasound2-dev \
  libboost-all-dev \
  libcap-dev \
  libcurl4-openssl-dev \
  libgmp-dev \
  libgsm1-dev \
  libi2c-dev \
  libiksemel-dev \
  libjansson-dev \
  libnewt-dev \
  libpopt-dev \
  libpq-dev \
  libpri-dev \
  libreadline-dev \
  libsnmp-dev \
  libspeex-dev \
  libspeexdsp-dev \
  libsqlite3-dev \
  libssl-dev \
  libtonezone-dev \
  libusb-dev \
  libvorbis-dev \
  libvpb-dev \
  python3-numpy \
  quilt \
  swig \
  unixodbc-dev

```

## Compiling
Packaging (.deb)

This will compile and package AllStar into .deb files. You do not need to run configure or make before doing this.

```
git clone https://github.com/AllStarLink/ASL-Asterisk.git
cd ASL-Asterisk/asterisk
debuild -b -us -uc
```

.debs will appear in the repository root folder after compiling and packaging

Manually
```
git clone https://github.com/AllStarLink/ASL-Asterisk.git
cd ASL-Asterisk/asterisk
./configure
make
make install
```

If all goes well, you will have cloned, configured, compiled and installed the Astersisk 1.4.23pre and app_rpt suite of programs that comprise the ASL 2.0.0+ release onto your system.

---------------------------------------------------------------------------------------------------------------------------------

## Help

Community Forum: https://community.allstarlink.org/

AllStarLink Wiki: http://wiki.allstarlink.org

E-Mail: developers@allstarlink.org

---------------------------------------------------------------------------------------------------------------------------------

## Contributing

Please refer to the [Contributing](https://wiki.allstarlink.org/wiki/Contributing) page on the AllStarLink Wiki.

## Copyright

Asterisk 1.4.23pre is copyright Digium (https://www.digium.com)

app_rpt and associated programs (app_rpt suite) are copyright Jim Dixon, WB6NIL; 2018-2021 AllStarLink, Inc., and contributors

_(Refer to each individual's file source code for full copyright information)_

## License

Asterisk, app_rpt, and all associated code/files are licensed, released, and distributed under the GNU General Public License v2 and cannot be relicensed without written permission of Digium and the copyright holders of the app_rpt suite of programs.
