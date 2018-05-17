# cyrus3_centos7_minimal
# Installation cyrus3 sur centOS7 minimal
yum group install "Development Tools"
  
yum install -y nano vim mlocate net-tools wget open-vm-tools openssl-devel.x86_64 jansson-devel.x86_64 cyrus-sasl-devel.x86_64 libicu-devel.x86_64 cpan

wget https://www.cyrusimap.org/releases/cyrus-imapd-3.0.6.tar.gz

tar xvzf cyrus-imapd-3.0.5.tar.gz

cd cyrus-imapd-3.0.5/

./configure

make

make install
  
  
