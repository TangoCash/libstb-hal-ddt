noinst_LTLIBRARIES = libmipsbox.la

AM_CPPFLAGS = \
	-I$(top_srcdir)/common \
	-I$(top_srcdir)/include

AM_CXXFLAGS = -fno-rtti -fno-exceptions -fno-strict-aliasing

AM_LDFLAGS = \
	-lOpenThreads \
	@AVFORMAT_LIBS@ \
	@AVUTIL_LIBS@ \
	@AVCODEC_LIBS@ \
	@SWRESAMPLE_LIBS@ \
	-lpthread -lass -lrt

libmipsbox_la_SOURCES = \
	hardware_caps.c \
	dmx.cpp \
	video.cpp \
	audio.cpp \
	init.cpp \
	record.cpp \
	hdmi_cec.cpp

if ENABLE_GSTREAMER_10
libmipsbox_la_SOURCES += \
	playback_gst.cpp

AM_LDFLAGS += \
	-lgstreamer-1.0 \
	-lgsttag-1.0 \
	-lgstmpegts-1.0
else
libmipsbox_la_SOURCES += \
	playback_libeplayer3.cpp

AM_CPPFLAGS += \
	-I$(top_srcdir)/libeplayer3-mips/include

AM_LDFLAGS += \
	-lass
endif

AM_CPPFLAGS += -D__STDC_FORMAT_MACROS -D__STDC_CONSTANT_MACROS
