# 指令编译器和选项  
CC = gcc  
CPP = g++
AR = ar rc
DEFS = -DWEBRTC_POSIX -DWEBRTC_LINUX
CFLAGS = -Wall -std=gnu99  
CPPFLAGS = -Wall -g -std=c++11 -pthread
CPPFLAGS += $(DEFS)
  
# 目标文件  
TARGET = libvideo_coding.so
# 头文件查找路径
INC = -I./ -I/home/yanghang/Desktop/BJ_CODE/
# C文件
SRCS = $(shell ls *.cc ../../utility/*.cc ../../codecs/i420/main/source/*.cc)  
#库文件及路径
DLIBS = 
LDFLAGS = -L../lib
#指定运行时的库文件路径
RPATH = 
# 目标文件  
OBJS = $(SRCS:.cc=.o)  
  
# 链接为可执行文件  
$(TARGET):$(OBJS)  
	$(CPP) -shared -o $@ $^
	cp $(TARGET) ../../../../lib
  
clean:  
	rm -rf $(TARGET) $(OBJS)  
  
# 编译规则 $@代表目标文件 $< 代表第一个依赖文件 $^ 去除重复的所有依赖文件 
%.o:%.cc  
	$(CPP) $(CPPFLAGS) $(INC) -o $@ -fPIC -c $< 
