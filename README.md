# MAME4Mobile（本工程，来自github)
dev分支过时不要再用，目前android/ios的源码还是有很多不同的。
所以先分两个分支:android, ios。

1 编安卓so
ndk只能用17.2.4988734版本， 下好ndk后改makefile里面的ndk路径。
再运行make，生成mame64，手动改成libmame4droid.so（后面这个改到自动流程中)。

目前只在mac下编过，后面会调pc环境。
仅用makefile编安卓so，先不要用它编ios的.a，它里面的ios目前不通。

More information visit my cnblog: https://www.cnblogs.com/ciml/

Available roms: https://wowroms.com/en/roms/list/mame+0.139u1

2 缟iOS的.a
本工程的ios编不过的，所以用github另一工程(MAME4iOS)，把它整进来需要做以下修改:
    从MAME4iOS拷进:
    src/osd/droid-ios/libmame.h
    make-ios.sh
    xcode目录
    ios目录
    ios-res目录
    拷makefile过来重命名成makefile-ios
	
    同时多余的要去掉:
rm  src/lib/hqx/AUTHORS
rm  src/lib/hqx/COPYING
rm  src/lib/hqx/ChangeLog
rm  src/lib/hqx/Makefile.am.hqx
rm  src/lib/hqx/NEWS
rm  src/lib/hqx/README
rm  src/lib/hqx/common.h
rm  src/lib/hqx/configure.ac.hqx
rm  src/lib/hqx/hq2x-int.h
rm  src/lib/hqx/hq2x_16.c
rm  src/lib/hqx/hq2x_24.c
rm  src/lib/hqx/hq2x_32.c
rm  src/lib/hqx/hq3x-int.h
rm  src/lib/hqx/hq3x_16.c
rm  src/lib/hqx/hq3x_24.c
rm  src/lib/hqx/hq3x_32.c
rm  src/lib/hqx/hq4x-int.h
rm  src/lib/hqx/hq4x_16.c
rm  src/lib/hqx/hq4x_24.c
rm  src/lib/hqx/hq4x_32.c
rm  src/lib/hqx/hqx.c
rm  src/lib/hqx/hqx.h
rm  src/lib/hqx/init.c
rm  src/osd/droid-ios/bt_joy.c
rm  src/osd/droid-ios/bt_joy.h
rm  src/osd/droid-ios/netplay.c
rm  src/osd/droid-ios/netplay.h
rm  src/osd/droid-ios/opensl_snd.c
rm  src/osd/droid-ios/opensl_snd.h
rm  src/osd/droid-ios/osd-droid.c
rm  src/osd/droid-ios/sixaxis.c
rm  src/osd/droid-ios/sixaxis.h
rm  src/osd/droid-ios/skt_netplay.c
rm  src/osd/droid-ios/skt_netplay.h
rm  src/osd/droid-ios/wiimote.c
rm  src/osd/droid-ios/wiimote.h
这样，用make -f makefile-ios可生成.a, xcode工程有了这个.a就能运行了。

# License

The native code(iOS&Android) is under terms of GNU General Public License <http://www.gnu.org/licenses>, version 2 or later (GPL-2.0+)

The MAME core library is under MAME license, Visit http://mamedev.org for licensing and usage restrictions. 
