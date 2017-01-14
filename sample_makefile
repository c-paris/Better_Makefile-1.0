NAME = 
SRC_NAME = 
SRC =   $(addprefix src/, $(SRC_NAME:=.c))
OBJ = $(SRC:%.c=%.o)
	LIB_PATH = ./libft/
	LIB = ./libft/libft.a
	INC = ./include/
	CC = gcc
	FLAGS = -g -Wall -Werror -Wextra -I ./include

all: $(EXEC)

msg:
	@echo "\033[0;29m⌛  Making Project : \c"

$(EXEC): msg $(OBJ)
	@echo ""
	@make -C ./libft/ -j 8
	@$(CC) -o $(EXEC) $(OBJ) $(LIB)
	@echo "\033[0;34m✅  Executable created !\033[0;29m"

src/%.o: src/%.c $(INC)
	@$(CC) $(FLAGS) -o $@ -c $<
	@echo "\033[0;32m.\c\033[0;29m"

clean:
	@make $@ -C $(LIB_PATH)
	@echo "\033[0;31m🔥  Cleaning Project Objects...\033[0;29m"
	@rm -rf $(OBJ)

fclean: clean
	@make $@ -C $(LIB_PATH)
	@echo "\033[0;31m🔥  Cleaning Project Executable...\033[0;29m"
	@rm -rf $(EXEC)

re: fclean all

.PHONY: all clean fclean re msg
