include ../../Makefile.config
include ../../Makefile.rules

SOURCES = s3c_file.c s3c_acl.c s3c_bucket.c s3c_util.c
LOCAL_LDFLAGS = -lm -ldttools ${CCTOOLS_INTERNAL_LDFLAGS}

OBJECTS = ${SOURCES:%.c=%.o}
HEADERS = ${SOURCES:%.c=%.h} ${EXTRA_HEADERS}
LIBRARIES = libs3client.a
PROGRAMS = s3put s3get s3stat s3rm s3mkdir s3rmdir s3ls s3getacl s3setacl

PROGRAM_SOURCES = ${PROGRAMS:%=%.c}

OBJECTS = ${LIBRARY_SOURCES:%.c=%.o}

LOCAL_LDFLAGS = -ls3client -lm -ldttools ${CCTOOLS_INTERNAL_LDFLAGS}

all: ${LIBRARIES} ${PROGRAMS}

s3put: s3put.o libs3client.a 
	${CCTOOLS_LD} -o $@ $^ ${LOCAL_LDFLAGS}
s3get: s3get.o libs3client.a 
	${CCTOOLS_LD} -o $@ $^ ${LOCAL_LDFLAGS}
s3stat: s3stat.o libs3client.a 
	${CCTOOLS_LD} -o $@ $^ ${LOCAL_LDFLAGS}
s3rm: s3rm.o libs3client.a 
	${CCTOOLS_LD} -o $@ $^ ${LOCAL_LDFLAGS}
s3mkdir: s3mkdir.o libs3client.a 
	${CCTOOLS_LD} -o $@ $^ ${LOCAL_LDFLAGS}
s3rmdir: s3rmdir.o libs3client.a 
	${CCTOOLS_LD} -o $@ $^ ${LOCAL_LDFLAGS}
s3ls: s3ls.o libs3client.a
	${CCTOOLS_LD} -o $@ $^ ${LOCAL_LDFLAGS}
s3getacl: s3getacl.o libs3client.a 
	${CCTOOLS_LD} -o $@ $^ ${LOCAL_LDFLAGS}
s3setacl: s3setacl.o libs3client.a 
	${CCTOOLS_LD} -o $@ $^ ${LOCAL_LDFLAGS}

libs3client.a: s3common.o s3c_util.o s3c_file.o s3c_bucket.o s3c_acl.o
	${CCTOOLS_AR} rv $@ $^
	ranlib $@

install:

clean:
	rm -f core *~ *.o *.os *.so libs3client.a $(PROGRAMS)

test:

