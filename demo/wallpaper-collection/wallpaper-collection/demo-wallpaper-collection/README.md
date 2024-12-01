

# demo-wallpaper-collection


## Usage


> deb-build-essential

``` sh
sudo apt-get --yes install git devscripts equivs
```


> deb-build-dep

``` sh
sudo mk-build-deps -i -t "apt-get -y" -r
```


> deb-build

``` sh
dpkg-buildpackage -b -uc -us -tc -j$(nproc)
```




## Sample Command


###  sample 1

> run to change log

``` sh
debchange --newversion "0.1.1-1" --controlmaint --distribution "unstable" --urgency "low" "Latest Release" --changelog debian/changelog
```

> cat debian/changelog




###  sample 2

run

``` sh
date -R
```

show

```
Mon, 02 Dec 2024 05:12:10 +0800
```


## sample 3

run to install [imagemagick](https://packages.debian.org/stable/imagemagick)

``` sh
sudo apt-get install imagemagick
```


run to create image

``` sh
convert \
	-size 640x480 'canvas:rgba(0,0,0,0)' \
	-fill 'rgba(180,142,173,0.7)' -draw "rectangle 0,0,640,480"  \
	640x480.jpg

convert \
	-size 800x600 'canvas:rgba(0,0,0,0)' \
	-fill 'rgba(163,190,149,0.7)' -draw "rectangle 0,0,800,600"  \
	800x600.jpg

convert \
	-size 1024x768 'canvas:rgba(0,0,0,0)' \
	-fill 'rgba(143,188,187,0.7)' -draw "rectangle 0,0,1024,768"  \
	1024x768.jpg

```

``` sh
ln -sf 1024x768.jpg default.jpg
```


* [nord palette](https://www.nordtheme.com/docs/colors-and-palettes)


## sample 4

run to show content

``` sh
dpkg -c ../demo-wallpaper-collection_0.1.1_amd64.deb
```

show

```
drwxr-xr-x root/root         0 2024-12-01 13:37 ./
drwxr-xr-x root/root         0 2024-12-01 13:37 ./usr/
drwxr-xr-x root/root         0 2024-12-01 13:37 ./usr/share/
drwxr-xr-x root/root         0 2024-12-01 13:37 ./usr/share/backgrounds/
drwxr-xr-x root/root         0 2024-12-01 13:37 ./usr/share/backgrounds/demo-wallpaper-collection/
-rw-r--r-- root/root      9503 2024-12-01 13:37 ./usr/share/backgrounds/demo-wallpaper-collection/1024x768.jpg
-rw-r--r-- root/root      3887 2024-12-01 13:37 ./usr/share/backgrounds/demo-wallpaper-collection/640x480.jpg
-rw-r--r-- root/root      5912 2024-12-01 13:37 ./usr/share/backgrounds/demo-wallpaper-collection/800x600.jpg
drwxr-xr-x root/root         0 2024-12-01 13:37 ./usr/share/doc/
drwxr-xr-x root/root         0 2024-12-01 13:37 ./usr/share/doc/demo-wallpaper-collection/
-rw-r--r-- root/root       180 2024-12-01 13:37 ./usr/share/doc/demo-wallpaper-collection/changelog.gz
-rw-r--r-- root/root      1065 2024-12-01 13:37 ./usr/share/doc/demo-wallpaper-collection/copyright
lrwxrwxrwx root/root         0 2024-12-01 13:37 ./usr/share/backgrounds/demo-wallpaper-collection/default.jpg -> 1024x768.jpg
```

run to show info

``` sh
dpkg -I ../demo-wallpaper-collection_0.1.1_amd64.deb
```

show

```
 new Debian package, version 2.0.
 size 2328 bytes: control archive=652 bytes.
     333 bytes,    10 lines      control
     454 bytes,     5 lines      md5sums
 Package: demo-wallpaper-collection
 Version: 0.1.1
 Architecture: amd64
 Maintainer: Develop Team <develop@home.heaven>
 Installed-Size: 32
 Section: devel
 Priority: optional
 Homepage: https://samwhelp.github.io/demo-create-debian-package/
 Description: Demo Skel Build Debian Package
  Skel create debian package for wallpaper collection.

```

run to install demo-wallpaper-collection_0.1.1_amd64.deb

``` sh
sudo dpkg -i ../demo-wallpaper-collection_0.1.1_amd64.deb
```


run to show file installed by demo-wallpaper-collection_0.1.1_amd64.deb

``` sh
dpkg -L demo-wallpaper-collection
```

show

```
/.
/usr
/usr/share
/usr/share/backgrounds
/usr/share/backgrounds/demo-wallpaper-collection
/usr/share/backgrounds/demo-wallpaper-collection/1024x768.jpg
/usr/share/backgrounds/demo-wallpaper-collection/640x480.jpg
/usr/share/backgrounds/demo-wallpaper-collection/800x600.jpg
/usr/share/doc
/usr/share/doc/demo-wallpaper-collection
/usr/share/doc/demo-wallpaper-collection/changelog.gz
/usr/share/doc/demo-wallpaper-collection/copyright
/usr/share/backgrounds/demo-wallpaper-collection/default.jpg
```

run to remove

``` sh
sudo dpkg -r demo-wallpaper-collection
```

or run to remove

``` sh
sudo apt-get remove demo-wallpaper-collection
```

or run to remove

``` sh
sudo apt-get purge demo-wallpaper-collection
```
