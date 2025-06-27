# Path definitions
WEB_DIR := ../web
BOOK_DIR := _book

# Default target
all: render copy view

# Render the full book
render:
	quarto render

# Copy all output files to web directory
copy:
	mkdir -p ../web
	cp -rf $(BOOK_DIR)/* $(WEB_DIR)/

view:
	Rscript -e "rlang::check_installed('plumber2'); library(plumber2); api() |> api_statics('/', '../web') |> api_run(block = TRUE)"