###############################################################
#
# Purpose: Makefile for "M-JPEG Streamer"
# Author.: Tom Stoeveken (TST)
# Version: 0.3
# License: GPL
#
###############################################################

OTHER_HEADERS = ../../mjpg_streamer.h ../../utils.h ../output.h ../input.h

CFLAGS += -O1 -DLINUX -D_GNU_SOURCE -Wall -shared -fPIC
#CFLAGS +=  -g
#CFLAGS += -DDEBUG
LFLAGS += -lpthread -ldl

all: output_http.so

clean:
	rm -f *.a *.o core *~ *.so *.lo

output_http.so: $(OTHER_HEADERS) output_http.c httpd.lo
	$(CC) $(CFLAGS) $(LDFLAGS) -o $@ output_http.c httpd.lo

httpd.lo: $(OTHER_HEADERS) httpd.h httpd.c
	$(CC) -c $(CFLAGS) -o $@ httpd.c
