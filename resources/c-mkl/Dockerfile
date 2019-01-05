FROM ubuntu:18.04

RUN apt-get update && apt-get install -y wget cpio build-essential 

# Install MKL
RUN cd /tmp && \
# Download MKL install package
  wget -q http://registrationcenter-download.intel.com/akdlm/irc_nas/tec/14895/l_mkl_2019.1.144.tgz && \
  tar -xzf l_mkl_2019.1.144.tgz && cd l_mkl_2019.1.144 && \
  sed -i 's/ACCEPT_EULA=decline/ACCEPT_EULA=accept/g' silent.cfg && \
  sed -i 's/ACTIVATION_TYPE=exist_lic/ACTIVATION_TYPE=trial_lic/g' silent.cfg && \
  ./install.sh -s silent.cfg && \
  cd .. && rm -rf *

