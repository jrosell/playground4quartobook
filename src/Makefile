# Path definitions
WEB_DIR := ../docs
BOOK_DIR := _book

# Default target
all: render copy view

# Render the full book
render:
	quarto render

# Copy all output files to web directory
copy:
	mkdir -p $(WEB_DIR)
	cp -rf $(BOOK_DIR)/* $(WEB_DIR)/

view:
	Rscript -e "rlang::check_installed('plumber2'); library(plumber2); api() |> api_statics('/', '$(WEB_DIR)') |> api_run(block = TRUE)"

# example: make partial FILE=chapter4-draft.qmd
partial:
	@quarto render $(FILE)
	@cp $(FILE:.qmd=.html) _book
	@echo "To see the $(FILE) rendered file, open http://localhost:8080/$(FILE:.qmd=.html)"
	@Rscript -e "rlang::check_installed('plumber2'); library(plumber2); api() |> api_statics('/', '$(BOOK_DIR)') |> api_run(block = TRUE)"
