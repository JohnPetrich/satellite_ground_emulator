# this file from /opt/local/share/gnuradio/examples/dtv
#
# You will need to get the Test Transport stream yourself
# as it it too large to fit in the repository. See further down
# in this file for instructions.
#
# Copyright 2014 Ron Economos
#
# This file is part of gr-dvbs2
#
# gr-dvbs2 is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 3, or (at your option)
# any later version.
#
# gr-dvbs2 is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with gr-dvbs2; see the file COPYING.  If not, write to
# the Free Software Foundation, Inc., 51 Franklin Street,
# Boston, MA 02110-1301, USA.

gr-dvbs2
======

Author: Ron Economos
Email: <w6rz@comcast.net>

The goal of this project is to build a software-defined DVB-S2
transmitter, based on the EN 302 307 V1.3.1 Second Generation
framing structure, channel coding and modulation systems for
Broadcasting, Interactive Services, New Gathering and other
broadband satellite applications standard:

http://www.etsi.org/deliver/etsi_en/302300_302399/302307/01.03.01_60/en_302307v010301p.pdf

The baseband framing, baseband scrambling, LDPC (low density
parity check), BCH (Bose, Chaudhuri, Hocquenghem), bit interleaver
and physical layer framing and scrambling blocks are from G4GUO's
DATV-Express Digital Amateur Television project datvexpress_gui
(https://github.com/G4GUO/datvexpress_gui/tree/master/DVB-S2)
and converted to GnuRadio 3.7.x.

A gnuradio-companion flowgraph (dvbs2_tx.grc) for the bladeRF
transmit capable SDR is included along with a stand-alone
Python script for bladeRF (dvbs2-blade.py).

A test Transport Stream that matches the example applications
symbol rate, constellation and code rate can be downloaded here:

http://www.w6rz.net/adv16apsk910.ts

A DVB-S2 and DVB-S2X Transport Stream bit-rate calculator:

https://github.com/drmpeg/dtv-utils/blob/master/dvbs2rate.c

Note: This implementation supports the following DVB-S2
System configurations:

1) QPSK 1/4, 1/3, 2/5
2) QPSK 1/2, 3/5, 2/3, 3/4, 4/5, 5/6, 8/9, 9/10
3) 8PSK 3/5, 2/3, 3/4, 5/6, 8/9, 9/10
4) 16APSK 2/3, 3/4, 4/5, 5/6, 8/9, 9/10
5) 32APSK 3/4, 4/5, 5/6, 8/9, 9/10
6) CCM (Constant Coding and Modulation)
7) FECFRAME normal 64,800 bits
8) FECFRAME short 16,200 bits
9) Single Transport Stream
10) Roll-off 0.35, 0.25 and 0.20

System configurations not supported are:

1) VCM (Variable Coding and Modulation)
2) ACM (Adaptive Coding and Modulation)
3) Multiple Transport Streams
4) Single Generic Stream
5) Multiple Generic Streams
6) Input Stream Synchronizer
7) Null Packet Detection
8) Dummy Frame Insertion
9) Wide-band mode

Note: DVB-S2X extensions are not fully tested due to lack of
available consumer or prosumer receivers. For DVB-S2X, optional
Broadcast services configurations supported are 64APSK and
64APSK-L. 128APSK, 256APSK and 256APSK-L constellations are
included for experimentation.

https://www.dvb.org/resources/public/standards/a83-2_dvb-s2x_den302307-2.pdf


Contributions are welcome!

