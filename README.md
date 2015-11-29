##About
It is not a fork of https://github.com/rmyorston/busybox-w32, but a help project.

busybox-w32 have 127 commands, 

```
       [, [[, ar, ash, awk, base64, basename, bash, bbconfig, bunzip2, bzcat,
       bzip2, cal, cat, catv, chmod, cksum, clear, cmp, comm, cp, cpio, cut,
       date, dc, dd, df, diff, dirname, dos2unix, dpkg-deb, du, echo, ed,
       egrep, env, expand, expr, false, fgrep, find, fold, ftpget, ftpput,
       getopt, grep, groups, gunzip, gzip, hd, head, hexdump, id, ipcalc,
       kill, killall, less, ln, logname, ls, lzcat, lzma, lzop, lzopcat, man,
       md5sum, mkdir, mktemp, mv, nc, od, patch, pgrep, pidof, printenv,
       printf, ps, pwd, rev, rm, rmdir, rpm2cpio, sed, seq, sh, sha1sum,
       sha256sum, sha3sum, sha512sum, shuf, sleep, sort, split, stat, strings,
       sum, tac, tail, tar, tee, test, touch, tr, true, truncate, uname,
       uncompress, unexpand, uniq, unix2dos, unlink, unlzma, unlzop, unxz,
       unzip, usleep, uudecode, uuencode, vi, wc, wget, which, whoami, xargs,
       xz, xzcat, yes, zcat
```

if you do not want run the command in this way

```
cmd.exe /c C:\path\to\busybox.exe sh -l
```
but

```
sh -l
```
this project is for you

##Update busybox.exe
Here is the last version [busybox.exe](http://frippery.org/files/busybox/busybox.exe)

##script to create 127 batch files

*Under Linux

```
sed -r  's/\ *(\w*\[*\-*\w*),*/echo @%~dp0\\\\busybox.exe \1 %*>\1.bat\n/g' bb.txt>bb
chmod u+x bb
./bb
zip busybox.zip *.bat
```

*Under Windows,

```
busybox bash
$ for cmd in `busybox --list`; do echo @%~dp0\\busybox.exe $cmd %*>$cmd.bat ;done
```

##Change log
*	replace busybox wget with [wget.exe](https://eternallybored.org/misc/wget/current/wget.exe) to support HTTPS

##P.S.
*	[scoop](https://github.com/lukesampson/scoop) is a good project, but it depends PowerShell3
*	[gow](https://github.com/bmatzelle/gow) (Gnu On Windows) is the lightweight alternative to Cygwin