EXTRA_DIST = Info.plist PkgInfo English.lproj/InfoPlist.strings linuxtrack_wii.icns \
English.lproj/MainMenu.nib/keyedobjects.nib English.lproj/MainMenu.nib/designable.nib

AM_CFLAGS = -arch x86_64
SLEOPARD_CFLAG = 
SLEOPARD_LDFLAG = -L..
DARWINFLAGS = -undefined dynamic_lookup 

if DARWIN
  bin_PROGRAMS = qt_cam WiiServer
endif

qt_cam_SOURCES = qt_camera.m args.c args.h buffer.c buffer.h mac_camera.h \
  ../com_proc.h ../ipc_utils.h processing.c processing.h macwebcam.c ../facetrack.h
EXTRA_qt_cam_SOURCES = dummy.cpp
qt_cam_LDADD = ../libfacetrack_int.la ../libltr.la -lobjc -lpthread
qt_cam_LDFLAGS = ${AM_CFLAGS} ${SLEOPARD_LDFLAG} -framework Cocoa -framework QTKit \
  -framework QuartzCore $(OPENCV_LIBS) -headerpad_max_install_names -L${srcdir}
qt_cam_CXXFLAGS = ${AM_CFLAGS} ${SLEOPARD_CFLAG} -I${srcdir} -I${srcdir}/.. -I..  -DOPENCV $(OPENCV_CFLAGS)
qt_cam_CFLAGS = ${AM_CFLAGS} ${SLEOPARD_CFLAG} -I${srcdir} -I${srcdir}/.. -I..  -DOPENCV $(OPENCV_CFLAGS)
qt_cam_OBJCFLAGS = ${AM_CFLAGS} ${SLEOPARD_CFLAG} -I${srcdir} -I${srcdir}/.. -I..

#sg_cam_SOURCES = sg_camera.c args.c args.h buffer.c buffer.h mac_camera.h ../com_proc.c \
#  ../com_proc.h ../ipc_utils.c ../ipc_utils.h processing.c processing.h macwebcam.c
#sg_cam_LDADD = -lltr -lobjc -lpthread
#sg_cam_LDFLAGS = ${AM_CFLAGS} ${SLEOPARD_LDFLAG} -framework QuickTime -framework CoreServices
#sg_cam_CFLAGS = ${AM_CFLAGS} ${SLEOPARD_CFLAG} -I${srcdir} -I${srcdir}/.. -I..
#sg_cam_OBJCFLAGS = ${AM_CFLAGS} ${SLEOPARD_CFLAG} -I${srcdir} -I${srcdir}/.. -I..

WiiServer_SOURCES = ../com_proc.h ../wii_com.h wiimote.m wiimote.h \
  wiimote_server.m wiimote_server.h wiisrvr_main.m ../ipc_utils.h
WiiServer_LDADD = ../libltr.la -lobjc -lpthread
WiiServer_LDFLAGS = ${AM_CFLAGS} ${SLEOPARD_LDFLAG} -framework Cocoa -framework CoreData \
  -framework AppKit -framework Foundation -framework IOBluetooth
WiiServer_CFLAGS = ${AM_CFLAGS} ${SLEOPARD_CFLAG} -I${srcdir} -I${srcdir}/.. -I..
WiiServer_OBJCFLAGS = ${AM_CFLAGS} ${SLEOPARD_CFLAG} -I${srcdir} -I${srcdir}/.. -I..

