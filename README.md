### cc-tool version 0.26+
cc-tool provides support for Texas Instruments CC Debugger

### Building from source, dependencies:
- Ubuntu: `libusb-1.0-0-dev libboost-all-dev autoconf libtool`
- Fedora: `boost-devel libusb1-devel`
- Mac OS 14.3: `brew install autoconf automake libusb boost pkgconfig libtool`
  - built successfully on M3 pro max 2023

1. Regenerate Autotools files first by running `./bootstrap` script.
2. Configure with `./cfg` 
   1. If you get errors, they relate to libraries, linking or headers, all exported in this file. Check boost version and include path, this one in particular: `LDFLAGS="-L/opt/homebrew/Cellar/boost/1.84.0_1/lib/"`
3. Build with `make`
4. Test with cc-tool -v -e -w filename.hex

### User guide:
`man cc-tool`

### Additional:
File `udev/90-cc-debugger.rules` cotains udev rules changing permissions 
for TI CC Debugger device and TI evolution boards so they can be used 
from non-privileged accounts. Copy it to `/etc/udev/rules.d`

### Support:
If you found a bug try to reproduce it with command line option `--log`.
