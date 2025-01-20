### System Inform
- Ubuntu 24.04 LTS
- sudo apt-get upgrade
- sudo apt-get update
- sudo apt-get install build-essential

### Install VSCode
- Download VSCode for Linux link
- Install
  - sudo dpkg -i code*.deb

### Tools
- sudo apt-get install gedit
- sudo apt-get install git-all
- sudo apt-get install openssh-server
- sudo apt-get install terminator

### Develop Library
- sudo apt-get install libboost-all-dev
  - Check version of installed LibBoost:
    - dpkg -s libboost-dev | grep 'Version'
    - Ubuntu 24.04LTS: Version: 1.83.0.1ubuntu2
- sudo apt-get install libglu1-mesa-dev freeglut3-dev mesa-common-dev
- sudo apt-get install cmake
  - Check version of cmake:
    - cmake --version
- sudo apt install libgoogle-glog-dev

### Download Qt-Offline installer [here](https://www.qt.io/offline-installers)
  - Qt-6.7.2 [Download Link](https://download.qt.io/official_releases/qt/6.7/6.7.2/single/qt-everywhere-src-6.7.2.tar.xz?__hstc=45788219.e9dba1c46f2e1969a08372456147125d.1689755853338.1689755853338.1689755853338.1&__hssc=45788219.1.1689755853338&__hsfp=783877104)
  - Extract Qt:
    - tar xf ~/Downloads/qt-everywhere-src-6.7.2.tar.xz
  - Install dependencies: [Qt Linux Requirements](https://doc.qt.io/qt-6/linux-requirements.html)
  - Install clang-dev:
    - sudo apt-get install libclang-dev
  - Build Qt Library and Tools:
    - mkdir -p ~/dev/qt-build
    - cd ~/dev/qt-build
    - /tmp/qt-everywhere-src-6.7.2/configure
    - cmake –build . –parallel
    - cmake –install .
- sudo apt-get install qtcreator
- sudo apt-get install qt6-base-dev
  - Check which qmake6 is registered in system:
    - which qmake6
    - qmake6 –version
    - Go to /usr/bin/
    - ls -la | grep qmake6: qmake6 -> /usr/lib/qt6/bin
    - Change symbol link:
      - sudo ln -sfn qmake6 -> /usr/local/Qt-6.7.2/bin/qmake6

### Download Qt-Online
- Install Qt online
- Install clang-dev:
    - sudo apt-get install libclang-dev
- Install dependencies:
    - sudo apt install libfontconfig1 libxcb-glx0 libx11-xcb1 libxcb-icccm4 libxcb-image0  libxcb-keysyms1 libxcb-randr0 libxcb-render-util0  libxcb-sync1 libxcb-xfixes0  libxcb-xinerama0 libxcb-xkb1 libxkbcommon-x11-0 libgl1 libegl1 libxcb-shape0 libxcb-cursor0 libglx-dev libgl1-mesa-dev
- Add path to system:
    - cd ~
    - nano ~/.bashrc
    - export PATH=$PATH:/home/'username'/Qt/'version'/gcc_64/bin
    - source ~/.bashrc
      

- sudo apt-get install freeglut3-dev
- sudo apt-get install libglfw3-dev libgl1-mesa-dev libglu1-mesa-dev
- sudo apt-get install libglew-dev
- sudo apt-get install libftgl-dev
- sudo apt-get install libgdal-dev
- sudo apt install fonts-roboto

### Install Qwt
- Download
- Unzip
- Edit qwt.pro by adding `QT += svg`
- Edit qwtconfig.pri by commenting out `QWT_CONFIG += QwtSvg`
- qmake6
- make -j32
- sudo make install
- Install to /usr/local/qwt-6.3.0/
- Add library to system:
    - cd ~
    - nano ~/.bashrc
    - export LD_LIBRARY_PATH=/usr/local/qwt-6.3.0/lib:$LD_LIBRARY_PATH
    - source ~/.bashrc

### QT Design Studio (optional)
- sudo apt-get install -y libxcb-cursor-dev
- Download qt-online-installer-linux-x64-4.8.0.run
- Install QT Design Studio
- Find QT Design Studio in [install_dir]/Tools/

### Github Desktop
- Add repositories:
  - wget -qO - https://apt.packages.shiftkey.dev/gpg.key | gpg –dearmor | sudo tee /usr/share/keyrings/shiftkey-packages.gpg > /dev/null
  - sudo sh -c ‘echo “deb [arch=amd64 signed-by=/usr/share/keyrings/shiftkey-packages.gpg] https://apt.packages.shiftkey.dev/ubuntu/ any main” > /etc/apt/sources.list.d/shiftkey-packages.list’
- Update and install Github Desktop:
  - sudo apt update && sudo apt install github-desktop

### Fix VSCode not responding
- Disable Wayland:
  - Edit /etc/gdm3/custom.conf
  - Disable Wayland:
    - WaylandEnable=false

### Create Qt-Project
- Create a QWidget Application `QWidgetApp`
- Select `QMake`
- Class `Class`
- Kit `Kits`
- Build Project `Build`
- Run Application `Run App`
  - cd /home/vnes/workspace/HelloQt/build/Desktop-Debug
  - ./HelloQT
