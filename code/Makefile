SOURCES := drop.cpp Player.cpp myrand.cpp Hihats.cpp tables.cpp BassDrum.cpp Compressor.cpp Drumpf.cpp mymath.cpp
HEADERS := $(wildcard *.hpp)
# Objs are all the sources, with .cpp replaced by .o
OBJS := $(SOURCES:.cpp=.o)
CXXFLAGS += -std=c++1y -g

all: drop.wav

drop.wav: drop.exe
	./drop.exe
	aplay $@

drop.exe: $(OBJS)
	$(CXX) $(CXXFLAGS) -o drop.exe $(OBJS) $(LFLAGS) $(LIBS) 

# Get a .o from a .cpp by calling compiler with cflags and includes (if defined)
%.o: %.cpp $(HEADERS)
	$(CXX) $(CXXFLAGS) $(INCLUDES) -c $<

clean:
	rm -f *.o drop.exe drop.wav
