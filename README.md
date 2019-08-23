# Mercator-python3
The python 3 distribution to use at Mercator is based on Anaconda.

To install, download Anaconda from https://www.anaconda.com/distribution/#download-section

Install Anaconda using the following commands:

> chmod +x Anaconda3-5.2.0-Linux-x86_64.sh
> ./Anaconda3-5.2.0-Linux-x86_64.sh

To install the needed python 3 packages for mercator, execute the following command:

> conda create --name mocs-37 --file mercator-linux-py37.0.txt

To be able to use the python 3 environment, execute:

> source activate mercator


There are a few extra packages that should be installed. This can be done using the following commands:

```bash
yum install postgresql-devel gcc-c++ gcc-gfortran
pip install guiqwt pySLALIB
pip install pygresql==5.0.6

# Install PyGuide
wget https://github.com/ApachePointObservatory/PyGuide/archive/2.3.0.tar.gz
tar zxvf 2.3.0.tar.gz
rm -rf 2.3.0.tar.gz
cd PyGuide-2.3.0/
python setup.py build
python setup.py install

# Install Spread
wget http://www.spread.org/download/spread-src-4.4.1.tar.gz
cd spread-src-4.4.1
./configure —prefix=/software/anaconda2/envs/mocs-37
make
make install
cd ../SpreadModule-1.5spread4
python setup.py build
python setup.py install

# Install Spread driver for python 3
wget https://www.savarese.com/downloads/libssrcspread/libssrcspread-1.0.15.tar.xz
tar Jxvf libssrcspread-1.0.15.tar.xz
cd libssrcspread-1.0.15/
configure --with-spread=
make install
```
