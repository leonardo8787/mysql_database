APPS = ./apps
BIN = ./bin
INCLUDE = ./include
LIB = ./lib
OBJ = ./obj
SRC = ./src

FLAGS = -O3 -Wall
LIBS = -lm -led -L $(LIB) -lmysqlclient

all: libed myapps

libed: \
	$(OBJ)/util.o \
	$(OBJ)/control_delete.o \
	$(OBJ)/control_select.o \
	$(OBJ)/control_insert.o \
	$(OBJ)/control_update.o \
	$(OBJ)/usuario.o \
	$(OBJ)/passo.o \
	$(OBJ)/etapa.o \
	$(OBJ)/ingrediente.o \
	$(OBJ)/receita.o \
	$(OBJ)/foto.o \
	$(OBJ)/curtida.o \
	$(OBJ)/comentario.o \
	$(OBJ)/receita_salva.o \
	$(OBJ)/control.o
	ar -rcs $(LIB)/libed.a $(OBJ)/*.o


myapps: clean_apps \
	$(BIN)/main

$(OBJ)/%.o: $(SRC)/%.cpp $(INCLUDE)/%.hpp
	g++ $(FLAGS) -c $< -I $(INCLUDE) -o $@

$(BIN)/%: $(APPS)/%.cpp
	g++ $(FLAGS) $< $(LIBS) -I $(INCLUDE) -o $@

run:
	$(BIN)/main

clean:
	rm -rf $(BIN)/* $(LIB)/* $(OBJ)/*

clean_apps:
	rm -rf $(BIN)/*

r: all run