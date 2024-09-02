ifdef OS  #Deteccion de Windows 
	CPL := marp.exe
	FixPath = $(subst /,\,$1)
else  	  #*NIX usando GNU make
	CPL := marp
	FixPath = $1
endif

FLAGS =--allow-local-files --html 
FLAGS += --pdf
THEME :=../src/am_nord.scss
FILE :=  $(word 1, $(MAKECMDGOALS))

$(FILE): 
	$(CPL) $(FLAGS) --theme $(call FixPath,$(THEME)) $(call FixPath,$@)

all: $(FILE)

clean:
	rm -f *.html

.PHONY: all clean pdf
