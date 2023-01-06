# GL-MT300N-V2-DTS-uart

- sudo apt-get install subversion build-essential libncurses5-dev zlib1g-dev gawk git ccache gettext libssl-dev xsltproc zip python

- git clone https://git.openwrt.org/openwrt/openwrt.git
- cd openwrt

sudo chown -R user .

- git checkout v19.07.10
- ./scripts/feeds update -a
- ./scripts/feeds install -a

- wget "https://raw.githubusercontent.com/painfull30/GL-MT300N-V2-DTS0-uart/main/300n_custom_DTS.patch" -O 300n_custom_DTS.patch
- git apply /tmp/300n_custom_DTS.patch

- wget "https://raw.githubusercontent.com/painfull30/GL-MT300N-V2-DTS0-uart/main/300nDTS.config" -O .config

- time make download
- time make -j$(nproc)

#if errors
- time make -j1 V=s

#unpack imagebuilder
- tar -xf bin/targets/ramips/mt76x8/openwrt-imagebuilder-* -C /tmp/

#run own script
- cd "/media/sf_D_DRIVE/Программинг/_Freelance/2020.04.20 - wikeys/"
- sudo bash make_archerc7_additvalue.sh

