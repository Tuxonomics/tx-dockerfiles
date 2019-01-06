FROM ubuntu:18.04

RUN apt-get update && apt-get install -y cpio build-essential clang wget

# Install MKL 2019.1
RUN cd /tmp && \
  wget -q http://registrationcenter-download.intel.com/akdlm/irc_nas/tec/14895/l_mkl_2019.1.144.tgz && \
  tar -xzf l_mkl_2019.1.144.tgz && cd l_mkl_2019.1.144 && \
  sed -i 's/ACCEPT_EULA=decline/ACCEPT_EULA=accept/g' silent.cfg && \
  sed -i 's/ACTIVATION_TYPE=exist_lic/ACTIVATION_TYPE=trial_lic/g' silent.cfg && \
  ./install.sh -s silent.cfg && \
  cd .. && rm -rf *

RUN apt-get remove -y --purge wget && apt-get autoremove -y

