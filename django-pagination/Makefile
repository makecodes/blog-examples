all: help ## Displays the help message

ENV := $(shell hostname)

help: ## Displays this help message
	@cols=$$(stty size | awk '{print $$2}'); \
	bar=$$(printf '━%.0s' $$(seq 1 $$cols)); \
	echo ""; \
	echo "$$bar"; \
	echo " ℹ️  Available Commands"; \
	echo "$$bar"; \
	echo " Usage: make [target]"; \
	echo ""; \
	printf "%-25s %s\n" "Target" "Description"; \
	printf "%-25s %s\n" "-------------------------" "---------------------------------------------"; \
	awk 'BEGIN {FS = ": ## "}; /^[a-zA-Z0-9_-]+: ## / {printf "%-25s %s\n", $$1, $$2}' $(MAKEFILE_LIST) | sort; \
	echo "$$bar";

clean: ## Removes temporary cache and build files and folders
	@rm .ruff_cache \
	@find . -name "*.pyc" -exec rm -f {} \;
	@find . -name "*.pyo" -exec rm -f {} \;
	@find . -name "__pycache__" -exec rm -rf {} \;

run: ## Starts the Django development server
	@uv run python manage.py runserver

lint: ## Runs the formatter and linter (ruff)
	@uv run ruff format .
	@uv run ruff check .

fix-lint: ## Automatically fixes lint issues
	@uv run ruff check . --fix

makemigrations: ## Creates new Django migrations
	@uv run python manage.py makemigrations

migrate: ## Applies Django migrations
	@uv run python manage.py migrate

shell: ## Opens the Django interactive shell (shell_plus)
	@uv run python manage.py shell_plus

show_urls: ## Displays all Django routes/URLs
	@uv run python manage.py show_urls
