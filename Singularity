BootStrap: docker
From:dbgannon/ubuntuplus

%files

%labels
MAINTAINER gannon

%environment
LD_LIBRARY_PATH=/usr/local/lib
export LD_LIBRARY_PATH=/usr/local/lib

%runscript
    echo "This is what happens when you run the container..."


%post
    echo "Hello from inside the container"
    echo "Installing Development Tools YUM group"
    apt-get -y update
    apt-get -y upgrade
    apt-get -y install vim
    apt-get -y install build-essential
    apt-get -y install wget
    wget https://www.open-mpi.org/software/ompi/v2.1/downloads/openmpi-2.1.0.tar.bz2
    tar -xf openmpi-2.1.0.tar.bz2
    echo "installing openmpi"
    ls
    cd openmpi-2.1.0
    ./configure --prefix=/usr/local
    make
    make install
    echo "done"
    export LD_LIBRARY_PATH=/usr/local/lib
    ls /mpicodes
    mpicc /mpicodes/ring-simple.c -o /usr/bin/ring-simple
