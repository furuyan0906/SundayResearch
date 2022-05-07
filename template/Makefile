
# -------------------------------------------------
DOC := template
TARGET := $(DOC).pdf

# -------------------------------------------------
TOP_DIR := .

DOC_DIR := $(TOP_DIR)/docs
OBJ_DIR := $(TOP_DIR)/build
SRC_DIR := $(TOP_DIR)/src

# -------------------------------------------------
SRCS := $(shell find $(SRC_DIR) -name "*.tex")
OBJS := $(SRCS:%=$(OBJ_DIR)/%.dvi)

# -------------------------------------------------
CXXFLAGS := -g -O2 -std=c++2a -Wall -MMD -MP

LDFLAGS := $(LINK_PATH) $(LIBS) $(THIDR_LIBS)
TEST_LDFLAGS := $(TEST_LINK_PATH) $(TEST_LIBS)

CPPFLAGS := $(DEFINES) $(INCLUDE)
TEST_CPPFLAGS := $(TEST_DEFINES) $(TEST_INCLUDE)

# -------------------------------------------------
TEX2DVI := platex
DVI2PDF := dvipdfmx

MKDIR = mkdir -p
RM := rm -rf
OPEN := gv


# -------------------------------------------------
.PHONY: doc clean open

all: doc open

doc: $(OBJ_DIR) $(OBJS) $(DOC_DIR)
	$(DVI2PDF) -o $(DOC_DIR)/$(TARGET) $(OBJ_DIR)/*.dvi

clean:
	-@$(RM) $(DOC_DIR)
	-@$(RM) $(OBJ_DIR)

open:
	$(OPEN) $(DOC_DIR)/$(TARGET)

$(OBJ_DIR)/%.tex.dvi: %.tex
	$(TEX2DVI) --output-directory=$(OBJ_DIR) $<

$(OBJ_DIR):
	$(MKDIR) $(OBJ_DIR)

$(DOC_DIR):
	$(MKDIR) $(DOC_DIR)

