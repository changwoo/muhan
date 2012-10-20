# for Linux
#	compiler : gcc
#	setting : OSFLAG = LINUX
#
# for DOS
#	compiler : djgpp
#	setting : OSFLAG = DOS

OSFLAG = LINUX

ifeq ($(OSFLAG), LINUX)

# linux options
CFLAGS = -O2
LIBS = -lm -s
CC = cc
RM = rm

CFLAGS += `pkg-config --cflags glib-2.0`
LIBS += `pkg-config --libs glib-2.0`

else

# dos djgpp options
CFLAGS = -DWIN32
LIBS =
CC = gcc
RM = del

endif

OBJECTS2 = editor.o editor2.o editor3.o editor4.o compress.o

OBJECTS3 = chat.o

editor: $(OBJECTS2)
	$(CC) $(CFLAGS) $(OBJECTS2) -o editor $(LIBS)
ifeq ($(OSFLAG),LINUX)
	chmod o-rwx editor
endif

chat: $(OBJECTS3)
	$(CC) $(CFLAGS) $(OBJECTS3) -o chat $(LIBS)
	chmod o-rwx chat

clean:
	$(RM) $(OBJECTS2)

