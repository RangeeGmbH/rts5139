# RTS5129/RTS5139 [![Gitlab CI](https://gitlab.com/aurorafossorg/utils/rts5139/badges/master/pipeline.svg)](https://gitlab.com/aurorafossorg/utils/rts5139/pipelines) [![Codacy Badge](https://api.codacy.com/project/badge/Grade/95256f87488f4568815991fb8a379728)](https://www.codacy.com/app/aurorafossorg/rts5139)

## Overview

This is a temporary fix for RTS5129/RTS5139 USB MMC card reader on Linux 3.16+ kernels.

This ocurred during a transition from ```3.15``` to ```3.16``` kernel, as a result of the ```staging/rts5139``` driver (which worked with the RTS5129/RTS5139) being replaced by the newer ```rtsx``` driver (which does not work with the RTS5129/RTS5139). This project reverts back to the old drivers as a temporary measure to get things up and running again.


## Install Requirements

`sudo apt-get install build-essential git dkms linux-headers-$(uname -r)`


## Building

`https://github.com/kelebek333/rts5139-dkms`

`sudo dkms add ./rts5139-dkms`

`sudo dkms build rts5139-dkms/1.0`

`sudo dkms install rts5139-dkms/1.0`

`sudo cp ./rts5139-dkms/blacklist-rts5139.conf /etc/modprobe.d/`

## Remove

`sudo dkms build rts5139-dkms/1.0 --all`

`sudo rm -f /etc/modprobe.d/blacklist-rts5139.conf`


## License
GNU General Public License - Version 2, June 1991
