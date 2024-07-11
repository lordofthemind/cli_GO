# Application commands
run: ## Run the application
	go run main.go

build_win: ## Build the application for Windows
	GOOS=windows GOARCH=amd64 go build -o ./bin/win/liveFxGraphGo.exe main.go

build_lin: ## Build the application for Linux
	GOOS=linux GOARCH=amd64 go build -o ./bin/linux/liveFxGraphGo main.go

build_mac: ## Build the application for MacOS
	GOOS=darwin GOARCH=amd64 go build -o ./bin/mac/liveFxGraphGo main.go

build_all: ## Build the application for all platforms
	$(MAKE) build_lin
	$(MAKE) build_win
	$(MAKE) build_mac


# Testing commands
test: ## Run tests
	go test ./...

lint: ## Run linter
	golangci-lint run

# Utility commands
clean: ## Clean the build
	rm -rf bin/

generate_tree: ## Generate directory tree
	tree > tree.txt

# Help command
help: ## Show help
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-20s\033[0m %s\n", $$1, $$2}'

.PHONY: run_pg_container start_pg_container stop_pg_container remove_pg_container remove_pg_data create_db drop_db migrate_db seed_db init_db run_app run_app_utc build_app test lint clean generate_tree setup help
