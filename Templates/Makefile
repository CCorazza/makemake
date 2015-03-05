NAME = proper
CC = gcc
FLAGS = -Wall -Wextra -Werror -O
include Makefile.sources
all: $(OBJ_DIR) $(NAME)
	@echo "Done."

$(NAME): $(OBJS)
	@echo "Creating binary \033[36m$(NAME)\033[0m"
	@$(CC) $(FLAGS) $(INFLAGS) $(addprefix $(SRC_DIR)/,$(SRC)) -o $(NAME)

$(OBJ_DIR)/%.o: $(SRC_DIR)/%.c
	@echo "Compiling \033[38;5;239m$<\033[0m."
	@$(CC) $(FLAGS) $(INFLAGS) -c $< -o $@

$(OBJ_DIR):
	@mkdir -p $(OBJ_DIR)

clean:
	@echo "Deleting obj files."
	@rm -f $(OBJS)
	@rm -rf $(OBJ_DIR)

fclean: clean
	@echo "Deleting binary."
	@rm -f $(NAME)

re: fclean all

.PHONY: all clean fclean re
