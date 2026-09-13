# fran .curl -H 'Cache-Control: no-cache' -o installantigravity.sh https://raw.githubusercontent.com/AnBui2004/termux/refs/heads/main/ide/antigravity/install1.sh && chmod +rwx installantigravity.sh && ./installantigravity.sh && rm installantigravity.sh && clear
export DATA_DIR=/data/user/0/com.xodos/files
export LANG=C.UTF-8
export LD_LIBRARY_PATH=$DATA_DIR/lib:$DATA_DIR/usr/lib
export PATH=$DATA_DIR/bin:$DATA_DIR/usr/bin:$PATH
export CONTAINER_DIR=$DATA_DIR/containers/0
export PROOT_TMP_DIR=$DATA_DIR/proot_tmp
export PROOT_LOADER=$DATA_DIR/applib/libproot-loader.so
export PROOT_LOADER_32=$DATA_DIR/applib/libproot-loader32.so
#export PROOT_L2S_DIR=$CONTAINER_DIR/.l2s
cd $DATA_DIR

#export PATH=/system/bin:$DATA_DIR/bin:$DATA_DIR/usr/bin
#export LD_LIBRARY_PATH=$DATA_DIR/usr/lib
ln -sf $DATA_DIR/applib/libexec_busybox.so $DATA_DIR/usr/bin/busybox
if [ ! -f "/system/bin/sh" ]; then
ln -sf /system/bin/sh $DATA_DIR/usr/bin/sh
fi
if [ ! -f "$DATA_DIR/usr/bin/sh" ]; then
ln -sf $DATA_DIR/applib/libexec_busybox.so $DATA_DIR/usr/bin/sh
fi
ln -sf $DATA_DIR/applib/libexec_busybox.so $DATA_DIR/usr/bin/cat
ln -sf $DATA_DIR/applib/libpv.so $DATA_DIR/usr/bin/pv
ln -sf $DATA_DIR/applib/libxz.so $DATA_DIR/usr/bin/xz
ln -sf $DATA_DIR/applib/libgzip.so $DATA_DIR/usr/bin/gzip
ln -sf $DATA_DIR/applib/liblzma.so $DATA_DIR/usr/lib/liblzma.so.5
ln -sf $DATA_DIR/applib/libexec_proot.so $DATA_DIR/usr/bin/proot
ln -sf $DATA_DIR/applib/libexec_tar.so $DATA_DIR/usr/bin/tar
ln -sf $DATA_DIR/applib/libexec_pulseaudio.so $DATA_DIR/usr/bin/pulseaudio
ln -sf $DATA_DIR/applib/libbusybox.so $DATA_DIR/usr/lib/libbusybox.so.1.37.0
ln -sf $DATA_DIR/applib/libtalloc.so $DATA_DIR/usr/lib/libtalloc.so.2
ln -sf $DATA_DIR/applib/libproot-loader32.so $DATA_DIR/usr/lib/loader32
ln -sf $DATA_DIR/applib/libproot-loader.so $DATA_DIR/usr/lib/loader
for f in /system/bin/*; do [ -f "$f" ] && ln -sf "$f" "$DATA_DIR/usr/bin/"; done

$DATA_DIR/usr/bin/busybox unzip -o assets.zip
chmod -R +x libexec/proot/*
chmod -R +x usr/bin/*
chmod -R +x bin/*
chmod -R +x usr/libexec/*
chmod 1777 usr/tmp
sleep 1
export PREFIX=$DATA_DIR/usr
export HOME=$DATA_DIR/home
export TMPDIR=$DATA_DIR/usr/tmp
#ln -sf $DATA_DIR/usr/bin $DATA_DIR/bin

export DATA_DIR=/data/user/0/com.xodos/files
export PATH=$DATA_DIR/usr/bin:$PATH
export LD_LIBRARY_PATH=$DATA_DIR/usr/lib
export CONTAINER_DIR=$DATA_DIR/containers/0
export EXTRA_OPT=""
cd $DATA_DIR
#export PATH=$DATA_DIR/bin:$PATH
export PROOT_TMP_DIR=$DATA_DIR/proot_tmp
export PROOT_LOADER=$DATA_DIR/applib/libproot-loader.so
export PROOT_LOADER_32=$DATA_DIR/applib/libproot-loader32.so
#export PROOT_L2S_DIR=$CONTAINER_DIR/.l2s

if [ -f "$DATA_DIR/proot.tar.xz" ]; then
$DATA_DIR/usr/bin/proot --link2symlink sh -c "cat proot.tar* | $DATA_DIR/usr/bin/tar x -J --delay-directory-restore --preserve-permissions  -C  /data/data/com.xodos/files/containers/0" || true
#Script from proot-distro
chmod u+rw "$CONTAINER_DIR/etc/passwd" "$CONTAINER_DIR/etc/shadow" "$CONTAINER_DIR/etc/group" "$CONTAINER_DIR/etc/gshadow"
echo "aid_$(id -un):x:$(id -u):$(id -g):Termux:/:/sbin/nologin" >> "$CONTAINER_DIR/etc/passwd"
echo "aid_$(id -un):*:18446:0:99999:7:::" >> "$CONTAINER_DIR/etc/shadow"
id -Gn | tr ' ' '\n' > tmp1
id -G | tr ' ' '\n' > tmp2
$DATA_DIR/usr/bin/busybox paste tmp1 tmp2 > tmp3
local group_name group_id
cat tmp3 | while read -r group_name group_id; do
	echo "aid_${group_name}:x:${group_id}:root,aid_$(id -un)" >> "$CONTAINER_DIR/etc/group"
	if [ -f "$CONTAINER_DIR/etc/gshadow" ]; then
		echo "aid_${group_name}:*::root,aid_$(id -un)" >> "$CONTAINER_DIR/etc/gshadow"
	fi
done
fi
$DATA_DIR/usr/bin/busybox rm -rf proot.tar* tmp1 tmp2 tmp3 assets.zip || true

sleep 1


exit $?
:/ $ export DATA_DIR=/data/user/0/com.xodos/files

:/ $ export LANG=C.UTF-8

:/ $ export LD_LIBRARY_PATH=$DATA_DIR/lib:$DATA_DIR/usr/lib

:/ $ export PATH=$DATA_DIR/bin:$DATA_DIR/usr/bin:$PATH

:/ $ export CONTAINER_DIR=$DATA_DIR/containers/0

:/ $ export PROOT_TMP_DIR=$DATA_DIR/proot_tmp

:/ $ export PROOT_LOADER=$DATA_DIR/applib/libproot-loader.so

:/ $ export PROOT_LOADER_32=$DATA_DIR/applib/libproot-loader32.so

:/ $ #export PROOT_L2S_DIR=$CONTAINER_DIR/.l2s

:/ $ cd $DATA_DIR

:/data/user/0/com.xodos/files $ 

:/data/user/0/com.xodos/files $ #export PATH=/system/bin:$DATA_DIR/bin:$DATA_D
export PATH=/system/bin:$DATA_DIR/bin:$DATA_D                                 <IR/usr/bin

:/data/user/0/com.xodos/files $ #export LD_LIBRARY_PATH=$DATA_DIR/usr/lib

:/data/user/0/com.xodos/files $ ln -sf $DATA_DIR/applib/libexec_busybox.so $DA
n -sf $DATA_DIR/applib/libexec_busybox.so $DA                                 <TA_DIR/usr/bin/busybox

:/data/user/0/com.xodos/files $ if [ ! -f "/system/bin/sh" ]; then

> ln -sf /system/bin/sh $DATA_DIR/usr/bin/sh

> fi

:/data/user/0/com.xodos/files $ if [ ! -f "$DATA_DIR/usr/bin/sh" ]; then

> ln -sf $DATA_DIR/applib/libexec_busybox.so $DATA_DIR/usr/bin/sh

> fi

:/data/user/0/com.xodos/files $ ln -sf $DATA_DIR/applib/libexec_busybox.so $DA
n -sf $DATA_DIR/applib/libexec_busybox.so $DA                                 <TA_DIR/usr/bin/cat

:/data/user/0/com.xodos/files $ ln -sf $DATA_DIR/applib/libpv.so $DATA_DIR/usr
n -sf $DATA_DIR/applib/libpv.so $DATA_DIR/usr                                 </bin/pv

:/data/user/0/com.xodos/files $ ln -sf $DATA_DIR/applib/libxz.so $DATA_DIR/usr
n -sf $DATA_DIR/applib/libxz.so $DATA_DIR/usr                                 </bin/xz

:/data/user/0/com.xodos/files $ ln -sf $DATA_DIR/applib/libgzip.so $DATA_DIR/u
n -sf $DATA_DIR/applib/libgzip.so $DATA_DIR/u                                 <sr/bin/gzip

:/data/user/0/com.xodos/files $ ln -sf $DATA_DIR/applib/liblzma.so $DATA_DIR/u
n -sf $DATA_DIR/applib/liblzma.so $DATA_DIR/u                                 <sr/lib/liblzma.so.5

:/data/user/0/com.xodos/files $ ln -sf $DATA_DIR/applib/libexec_proot.so $DATA
n -sf $DATA_DIR/applib/libexec_proot.so $DATA                                 <_DIR/usr/bin/proot

:/data/user/0/com.xodos/files $ ln -sf $DATA_DIR/applib/libexec_tar.so $DATA_D
n -sf $DATA_DIR/applib/libexec_tar.so $DATA_D                                 <IR/usr/bin/tar

:/data/user/0/com.xodos/files $ ln -sf $DATA_DIR/applib/libexec_pulseaudio.so 
n -sf $DATA_DIR/applib/libexec_pulseaudio.so                                  <$DATA_DIR/usr/bin/pulseaudio

:/data/user/0/com.xodos/files $ ln -sf $DATA_DIR/applib/libbusybox.so $DATA_DI
n -sf $DATA_DIR/applib/libbusybox.so $DATA_DI                                 <R/usr/lib/libbusybox.so.1.37.0

:/data/user/0/com.xodos/files $ ln -sf $DATA_DIR/applib/libtalloc.so $DATA_DIR
n -sf $DATA_DIR/applib/libtalloc.so $DATA_DIR                                 </usr/lib/libtalloc.so.2

:/data/user/0/com.xodos/files $ ln -sf $DATA_DIR/applib/libproot-loader32.so $
n -sf $DATA_DIR/applib/libproot-loader32.so $                                 <DATA_DIR/usr/lib/loader32

:/data/user/0/com.xodos/files $ ln -sf $DATA_DIR/applib/libproot-loader.so $DA
n -sf $DATA_DIR/applib/libproot-loader.so $DA                                 <TA_DIR/usr/lib/loader

:/data/user/0/com.xodos/files $ for f in /system/bin/*; do [ -f "$f" ] && ln -
or f in /system/bin/*; do [ -f "$f" ] && ln -                                 <sf "$f" "$DATA_DIR/usr/bin/"; don
 [ -f "$f" ] && ln -sf "$f" "$DATA_DIR/usr/bin/"; don                         <e

1|:/data/user/0/com.xodos/files $ 

1|:/data/user/0/com.xodos/files $ $DATA_DIR/usr/bin/busybox unzip -o assets.zi
DATA_DIR/usr/bin/busybox unzip -o assets.zi                                   <p

Archive:  assets.zip
   creating: bin/
  inflating: bin/libjson-c.so
  inflating: bin/libltdl.so
  inflating: bin/libprotocol-cli.so
  inflating: bin/libprotocol-http.so
  inflating: bin/libprotocol-native.so
  inflating: bin/libprotocol-simple.so
  inflating: bin/libpulse-simple.so
  inflating: bin/libpulse.so
  inflating: bin/libpulsecommon-13.0.so
  inflating: bin/libpulsecore-13.0.so
  inflating: bin/librtp.so
  inflating: bin/libsndfile.so
  inflating: bin/module-allow-passthrough.so
  inflating: bin/module-always-sink.so
  inflating: bin/module-always-source.so
  inflating: bin/module-augment-properties.so
  inflating: bin/module-card-restore.so
  inflating: bin/module-cli-protocol-tcp.so
  inflating: bin/module-cli-protocol-unix.so
  inflating: bin/module-cli.so
  inflating: bin/module-combine-sink.so
  inflating: bin/module-combine.so
  inflating: bin/module-default-device-restore.so
  inflating: bin/module-detect.so
  inflating: bin/module-device-manager.so
  inflating: bin/module-device-restore.so
  inflating: bin/module-echo-cancel.so
  inflating: bin/module-filter-apply.so
  inflating: bin/module-filter-heuristics.so
  inflating: bin/module-http-protocol-tcp.so
  inflating: bin/module-http-protocol-unix.so
  inflating: bin/module-intended-roles.so
  inflating: bin/module-ladspa-sink.so
  inflating: bin/module-loopback.so
  inflating: bin/module-match.so
  inflating: bin/module-mmkbd-evdev.so
  inflating: bin/module-native-protocol-fd.so
  inflating: bin/module-native-protocol-tcp.so
  inflating: bin/module-native-protocol-unix.so
  inflating: bin/module-null-sink.so
  inflating: bin/module-null-source.so
  inflating: bin/module-opensles.so
  inflating: bin/module-position-event-sounds.so
  inflating: bin/module-remap-sink.so
  inflating: bin/module-remap-source.so
  inflating: bin/module-rescue-streams.so
  inflating: bin/module-role-cork.so
  inflating: bin/module-role-ducking.so
  inflating: bin/module-rtp-recv.so
  inflating: bin/module-rtp-send.so
  inflating: bin/module-simple-protocol-tcp.so
  inflating: bin/module-simple-protocol-unix.so
  inflating: bin/module-sine-source.so
  inflating: bin/module-sine.so
  inflating: bin/module-stream-restore.so
  inflating: bin/module-suspend-on-idle.so
  inflating: bin/module-switch-on-connect.so
  inflating: bin/module-switch-on-port-available.so
  inflating: bin/module-tunnel-sink-new.so
  inflating: bin/module-tunnel-sink.so
  inflating: bin/module-tunnel-source-new.so
  inflating: bin/module-tunnel-source.so
  inflating: bin/module-virtual-sink.so
  inflating: bin/module-virtual-source.so
  inflating: bin/module-virtual-surround-sink.so
  inflating: bin/module-volume-restore.so
  inflating: bin/pulseaudio.conf
:/data/user/0/com.xodos/files $ chmod -R +x libexec/proot/*

chmod: libexec/proot/*: No such file or directory
1|:/data/user/0/com.xodos/files $ chmod -R +x usr/bin/*

chmod: chmod 'usr/bin/busybox' to 0777: Permission denied
chmod: chmod 'usr/bin/cat' to 0777: Permission denied
chmod: chmod 'usr/bin/gzip' to 0777: Permission denied
chmod: chmod 'usr/bin/proot' to 0777: Permission denied
chmod: chmod 'usr/bin/pulseaudio' to 0777: Permission denied
chmod: chmod 'usr/bin/pv' to 0777: Permission denied
chmod: chmod 'usr/bin/sh' to 0777: Permission denied
chmod: chmod 'usr/bin/tar' to 0777: Permission denied
chmod: chmod 'usr/bin/xz' to 0777: Permission denied
1|:/data/user/0/com.xodos/files $ chmod -R +x bin/*

:/data/user/0/com.xodos/files $ chmod -R +x usr/libexec/*

chmod: usr/libexec/*: No such file or directory
1|:/data/user/0/com.xodos/files $ chmod 1777 usr/tmp

:/data/user/0/com.xodos/files $ sleep 1

:/data/user/0/com.xodos/files $ export PREFIX=$DATA_DIR/usr

:/data/user/0/com.xodos/files $ export HOME=$DATA_DIR/home

:/data/user/0/com.xodos/files $ export TMPDIR=$DATA_DIR/usr/tmp

:/data/user/0/com.xodos/files $ #ln -sf $DATA_DIR/usr/bin $DATA_DIR/bin

:/data/user/0/com.xodos/files $ 

:/data/user/0/com.xodos/files $ export DATA_DIR=/data/user/0/com.xodos/files

:/data/user/0/com.xodos/files $ export PATH=$DATA_DIR/usr/bin:$PATH

:/data/user/0/com.xodos/files $ export LD_LIBRARY_PATH=$DATA_DIR/usr/lib

:/data/user/0/com.xodos/files $ export CONTAINER_DIR=$DATA_DIR/containers/0

:/data/user/0/com.xodos/files $ export EXTRA_OPT=""

:/data/user/0/com.xodos/files $ cd $DATA_DIR

:/data/user/0/com.xodos/files $ #export PATH=$DATA_DIR/bin:$PATH

:/data/user/0/com.xodos/files $ export PROOT_TMP_DIR=$DATA_DIR/proot_tmp

:/data/user/0/com.xodos/files $ export PROOT_LOADER=$DATA_DIR/applib/libproot-
xport PROOT_LOADER=$DATA_DIR/applib/libproot-                                 <loader.so

:/data/user/0/com.xodos/files $ export PROOT_LOADER_32=$DATA_DIR/applib/libpro
xport PROOT_LOADER_32=$DATA_DIR/applib/libpro                                 <ot-loader32.so

:/data/user/0/com.xodos/files $ #export PROOT_L2S_DIR=$CONTAINER_DIR/.l2s

:/data/user/0/com.xodos/files $ 

:/data/user/0/com.xodos/files $ if [ -f "$DATA_DIR/proot.tar.xz" ]; then

> $DATA_DIR/usr/bin/proot --link2symlink sh -c "cat proot.tar* | $DATA_DIR/usr
 --link2symlink sh -c "cat proot.tar* | $DATA_DIR/usr                         </bin/tar x -J --delay-dir
t proot.tar* | $DATA_DIR/usr/bin/tar x -J --delay-dir                         <ectory-restore --preserve
usr/bin/tar x -J --delay-directory-restore --preserve                         <-permissions  -C  /data/d
directory-restore --preserve-permissions  -C  /data/d                         <ata/com.xodos/files/conta
rve-permissions  -C  /data/data/com.xodos/files/conta                         <iners/0" || true

> #Script from proot-distro

> chmod u+rw "$CONTAINER_DIR/etc/passwd" "$CONTAINER_DIR/etc/shadow" "$CONTAIN
DIR/etc/passwd" "$CONTAINER_DIR/etc/shadow" "$CONTAIN                         <ER_DIR/etc/group" "$CONTA
ER_DIR/etc/shadow" "$CONTAINER_DIR/etc/group" "$CONTA                         <INER_DIR/etc/gshadow"

> echo "aid_$(id -un):x:$(id -u):$(id -g):Termux:/:/sbin/nologin" >> "$CONTAIN
(id -u):$(id -g):Termux:/:/sbin/nologin" >> "$CONTAIN                         <ER_DIR/etc/passwd"

> echo "aid_$(id -un):*:18446:0:99999:7:::" >> "$CONTAINER_DIR/etc/shadow"

> id -Gn | tr ' ' '\n' > tmp1

> id -G | tr ' ' '\n' > tmp2

> $DATA_DIR/usr/bin/busybox paste tmp1 tmp2 > tmp3

> local group_name group_id

> cat tmp3 | while read -r group_name group_id; do

> echo "aid_${group_name}:x:${group_id}:root,aid_$(id -un)" >> "$CONTAINER_DIR
:x:${group_id}:root,aid_$(id -un)" >> "$CONTAINER_DIR                         </etc/group"

> if [ -f "$CONTAINER_DIR/etc/gshadow" ]; then

> echo "aid_${group_name}:*::root,aid_$(id -un)" >> "$CONTAINER_DIR/etc/gshado
:*::root,aid_$(id -un)" >> "$CONTAINER_DIR/etc/gshado                         <w"

> fi

> done

> fi

:/data/user/0/com.xodos/files $ $DATA_DIR/usr/bin/busybox rm -rf proot.tar* tm
DATA_DIR/usr/bin/busybox rm -rf proot.tar* tm                                 <p1 tmp2 tmp3 assets.zip || true

:/data/user/0/com.xodos/files $ 

:/data/user/0/com.xodos/files $ sleep 1

:/data/user/0/com.xodos/files $ 

:/data/user/0/com.xodos/files $ 

:/data/user/0/com.xodos/files $ exit $?

export LANG=C.UTF-8
export DATA_DIR=/data/user/0/com.xodos/files
export PREFIX=$DATA_DIR/usr
export HOME=$DATA_DIR/home
export TMPDIR=$DATA_DIR/usr/tmp
export PATH=$DATA_DIR/usr/bin:$PATH
export LD_LIBRARY_PATH=$DATA_DIR/usr/lib
export CONTAINER_DIR=$DATA_DIR/containers/0
export EXTRA_OPT=""
cd $DATA_DIR
export PROOT_TMP_DIR=$DATA_DIR/proot_tmp
export PROOT_LOADER=$DATA_DIR/applib/libproot-loader.so
export PROOT_LOADER_32=$DATA_DIR/applib/libproot-loader32.so
#export PROOT_L2S_DIR=$CONTAINER_DIR/.l2s
$DATA_DIR/usr/bin/proot --link2symlink sh -c "

if [  -f "$DATA_DIR/xaa" ]; then
  echo ' Extracting split archive...'
  cat xa* | $DATA_DIR/usr/bin/tar x -J 
    --delay-directory-restore 
    --preserve-permissions 
     -C /data/data/com.xodos/files/
else
  echo ' No xa archive parts found, skipping...'
fi
"
if [ -f "$DATA_DIR/xodos.tar.xz" ]; then

$DATA_DIR/usr/bin/tar -xf $DATA_DIR/xodos.tar.xz  --delay-directory-restore  --preserve-permissions  -C /data/data/com.xodos/files 
  else
echo " xodos.tar.xz not found, skipping..."
fi
#Script to fix
sleep 1

$DATA_DIR/usr/bin/busybox rm -rf xa* xodos.tar.xz || true
echo "" > /data/data/com.xodos/files/usr/opt/drv
sed -i 's/xproot//g' /data/data/com.xodos/files/usr/bin/xodos

fixx(){
sed -i '/export PULSE_SERVER=tcp:127.0.0.1:4718/a \
chmod +x $PREFIX/var/lib/proot-distro/installed-rootfs/0/lang \
source $PREFIX/var/lib/proot-distro/installed-rootfs/0/lang \
unset GALLIUM_DRIVER' "$PREFIX/bin/xxx"
sed -i '/export PULSE_SERVER=tcp:127.0.0.1:4718/a \
chmod +x $PREFIX/var/lib/proot-distro/installed-rootfs/0/lang \
source $PREFIX/var/lib/proot-distro/installed-rootfs/0/lang \
unset GALLIUM_DRIVER' "$PREFIX/bin/xodos"
cp -f $PREFIX/var/lib/proot-distro/installed-rootfs/0/lang $PREFIX/bin/lang
}
sed -i.bak 's/^Hset -e^H/set +e/g' "$PREFIX/bin/proot-distro"
ln -sf $DATA_DIR/tiny/extra/ $DATA_DIR/containers/0/extra
ln -sf /sdcard $DATA_DIR/containers/0/sdcard

for f in "$DATA_DIR/usr/opt/winece/arm64-v8a/bin/"*; do ln -sf "$f" "$DATA_DIR/usr/bin/"; done

exit $?
:/ $ export LANG=C.UTF-8

:/ $ export DATA_DIR=/data/user/0/com.xodos/files

:/ $ export PREFIX=$DATA_DIR/usr

:/ $ export HOME=$DATA_DIR/home

:/ $ export TMPDIR=$DATA_DIR/usr/tmp

:/ $ export PATH=$DATA_DIR/usr/bin:$PATH

:/ $ export LD_LIBRARY_PATH=$DATA_DIR/usr/lib

:/ $ export CONTAINER_DIR=$DATA_DIR/containers/0

:/ $ export EXTRA_OPT=""

:/ $ cd $DATA_DIR

:/data/user/0/com.xodos/files $ export PROOT_TMP_DIR=$DATA_DIR/proot_tmp

:/data/user/0/com.xodos/files $ export PROOT_LOADER=$DATA_DIR/applib/libproot-
xport PROOT_LOADER=$DATA_DIR/applib/libproot-                                 <loader.so

:/data/user/0/com.xodos/files $ export PROOT_LOADER_32=$DATA_DIR/applib/libpro
xport PROOT_LOADER_32=$DATA_DIR/applib/libpro                                 <ot-loader32.so

:/data/user/0/com.xodos/files $ #export PROOT_L2S_DIR=$CONTAINER_DIR/.l2s

:/data/user/0/com.xodos/files $ $DATA_DIR/usr/bin/proot --link2symlink sh -c "
DATA_DIR/usr/bin/proot --link2symlink sh -c "                                 <

> 

> if [  -f "$DATA_DIR/xaa" ]; then

>   echo ' Extracting split archive...'

>   cat xa* | $DATA_DIR/usr/bin/tar x -J 

>     --delay-directory-restore 

>     --preserve-permissions 

>      -C /data/data/com.xodos/files/

> else

>   echo ' No xa archive parts found, skipping...'

> fi

> "

 Extracting split archive...
./antigravity.sh
