NAME        = Terri-fried

CXX         = g++

SOURCES     = $(wildcard *.cpp)

OBJ_DIR     = build/obj
OUT_DIR     = build/bin
OBJS        = $(patsubst %, $(OBJ_DIR)/%, $(SOURCES:.cpp=.o))
RES_FILES   = winres/TF-icon.res
MKDIR_P     = mkdir -p

FLAGS       = -O3 -std=c++11
LIBS        = -lSDL2main -lSDL2 -lSDL2_image -lSDL2_mixer -lSDL2_ttf -L/opt/homebrew/Cellar/sdl2_ttf/2.0.15/lib -L/opt/homebrew/Cellar/sdl2/2.0.16/lib -L/opt/homebrew/Cellar/sdl2_image/2.0.5/lib -L/opt/homebrew/Cellar/sdl2_mixer/2.0.4_2/lib


.PHONY: directories

all: directories $(NAME)

directories: $(OBJ_DIR) $(OUT_DIR)

$(OBJ_DIR):
	$(MKDIR_P) $(OBJ_DIR)

$(OUT_DIR):
	$(MKDIR_P) $(OUT_DIR)


$(NAME): $(OBJS)
	$(CXX) $(FLAGS) -o $(OUT_DIR)/$(NAME) $(OBJS) $(RES_FILES) $(LIBS)

$(OBJ_DIR)/%.o: %.cpp
	$(CXX) $(FLAGS) -c $< -o $@

clean:
	@echo clean...
	@rm -fr build
