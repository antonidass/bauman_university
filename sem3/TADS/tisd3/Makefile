CC := gcc

CFLAGS := -std=c99 -pedantic -Wvla -Wextra -g

S := ./src/
O := ./out/

MK := mkdir -p


SRCS := $(wildcard $(S)*c)
OBJS := $(patsubst $(S)%.c,$(O)%.o,$(SRCS))	


app.out : $(OBJS)
	$(CC) $(CFLAGS) -o $@ $(OBJS)


$(OBJS) : $(O)%.o : $(S)%.c
	$(MK) $(O); $(CC) $(CFLAGS) -c $< -o $@


.PHONY : clean r

r : 
	./app.out

clean :
	$(RM) $(O)*.o $(O)*.out $(O)*.exe
