
# -------------------------------------------------
DOC := Non-Markov_ContinuousQuantumMeasurement
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
TEX2DVI := platex
DVI2PDF := dvipdfmx

MKDIR = mkdir -p
RM := rm -rf
OPEN := evince


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

