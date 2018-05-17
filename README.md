# cyrus3_centos7_minimal
# Installation cyrus3 sur centOS7 minimal

  
yum install -y cpan autoconf \ 
bison cyrus-sasl-devel flex gcc  gperf jansson-devel libbsd-devel libtool \ 
libicu-devel libuuid-devel openssl-devel pkgconfig sqlite-devel cyrus-sasl-plain \
cyrus-sasl-md5  libical-devel libxml2-devel mod_ssl net-snmp-devel \
openldap-devel zlib-devel

yum groupinstall "Development tools"

wget https://www.cyrusimap.org/releases/cyrus-imapd-3.0.6.tar.gz

tar xvzf cyrus-imapd-3.0.5.tar.gz

cd cyrus-imapd-3.0.5/
autoreconf -i
 
./configure CFLAGS="-W -Wno-unused-parameter -g -O0 -Wall -Wextra -Werror -fPIC" \
--enable-coverage --enable-calalarmd --enable-autocreate \
--enable-nntp --enable-http --enable-unit-tests \
--with-openssl=yes --with-perl --with-ldap \
--enable-idled --prefix=/usr/cyrus  --exec-prefix=/usr/cyrus
make

make install
  
  
