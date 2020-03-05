# Gnome Terminal Patch

Originally from [sasha-x](https://github.com/sasha-x/ubuntu-gnome-terminal-patch),
a patch to add PuTTY-like copy on select and right-click paste to Gnome Terminal in Ubuntu.  Use ctrl+right-click to bring up the original Gnome Terminal context menu.
I built the patched version on 64-bit Ubunty eoan 19.10, Gnome Terminal 3.34.2.

## Building Instructions using Patch

1. Install build dependencies

  ```shell
  sudo apt-get build-dep gnome-terminal
  ```

2. Download the sources and apply the patch

  ```shell
  mkdir gnome-terminal
  cd gnome-terminal
  apt source gnome-terminal
  cd gnome-terminal-3.34.2
  wget https://raw.githubusercontent.com/yar999/gnome-terminal-patch/master/gnome-terminal-3.34.2.patch
  patch -p0 < gnome-terminal-3.34.2.patch
  ```

3. Build

  ```shell
  dpkg-buildpackage -us -uc -b
  ```

4. Install

  ```shell
  cd ..
  sudo dpkg -i *.deb
  ```

## License

[MIT License](http://en.wikipedia.org/wiki/MIT_License)

