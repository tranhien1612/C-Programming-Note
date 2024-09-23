# Install GST from source code

## Prerequistes: Install below pacakges
```
	apt install meson
	apt-get install libmount-dev
	apt-get install flex
	apt-get install flex bison
	apt-get install libglib2.0-dev
```
	
## Compilation and installation steps
### Remove older version
```
	apt-get remove *gstreamer*
```

### Clone the repository


Clone the repository from link: https://gitlab.freedesktop.org/gstreamer/gstreamer/-/tree/1.22.9?ref_type=tags

```
  mkdir /tmp/gst-<gst-version> && cd /tmp/gst-<gst-version>
	git clone https://gitlab.freedesktop.org/gstreamer/gstreamer.git
	cd gstreamer

  git checkout <gst-version-branch> #e.g. git checkout 1.22.9
```

### Build
```
	meson build --prefix=/usr
	ninja -C build/
	cd build && ninja install
```

## Check and confirm the newly installed gstreamer version
	gst-inspect-1.0 --version
