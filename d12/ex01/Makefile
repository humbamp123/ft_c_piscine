# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: myoung <marvin@42.fr>                      +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2016/08/22 12:51:39 by myoung            #+#    #+#              #
#    Updated: 2016/08/25 16:27:39 by myoung           ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

NAME		=	ft_cat
FILENAMES	=	ft_putchar.c ft_putstr.c ft_strcmp.c ft_strlen.c ft_swap.c
FILENAMES	+=	ft_putnbr.c ft_display_file.c ft_errno.c ft_err_print.c
FILENAMES	+=	ft_progname.c ft_fputstr.c

MAIN		=	srcs/main.c

LIB			=	libft.a

CC			=	gcc
CFLAGS		?=	-Wall -Wextra -Werror
CFLAGS		+=	-I includes
AR			?=	ar

SOURCES		=	$(addprefix srcs/, $(FILENAMES))
OBJECTS		=	$(addprefix build/, $(FILENAMES:.c=.o))

# Even if a file exisits, don't process with it.
.PHONY: all clean fclean re

#This happens to be our first command, so it is the default	
all: $(LIB) $(NAME)

$(NAME): $(MAIN)
	$(CC) $(CFLAGS) $(MAIN) $(LIB) -o $@

$(LIB): $(OBJECTS)
	$(AR) crs $@ $(OBJECTS)

build/%.o: srcs/%.c | build
	$(CC) $(CFLAGS) -c $< -o $@

clean:
	@rm -rf build/

lclean: clean
	@rm -rf $(LIB)

fclean: lclean
	@rm -f $(NAME)

re: fclean all

build:
	mkdir build/
