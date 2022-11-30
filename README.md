# rc700-cpm-jbox
RC702 CP/M jbox building on GitHub Actions, with new stuff.

See <http://www.jbox.dk/rc702/rcbios.shtm> for starting point.  

My goal is to end up with what I had 30 years ago, namely a 
CP/M running on real hardware with serial port and keyboard 
buffering so it is usable as a terminal against a Unix
system.   No modem though.  Starting with 19200 baud but
hopefully go up to 115200 if the CPU can keep up.


Instead of continuing with my old disassembled and heavily hacked
BIOS (see <https://github.com/ravn/rc702-bios>) I am going with 
the impressive work that Michael Ringgård did with his RC702 emulator.

The sources are in <B/0> to target RunCPM.

/ravn 2022-11-30