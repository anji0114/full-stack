# Makefile for Docker shortcuts

# Docker containers
API_CONTAINER = nestjs-api
DB_CONTAINER = dynamodb-local
DB_ADMIN_CONTAINER = dynamodb-admin

# Default shell
.PHONY: shell
shell: shell-api

# API container shell
.PHONY: shell-api
shell-api:
	docker exec -it $(API_CONTAINER) /bin/sh

# DynamoDB container shell
.PHONY: shell-db
shell-db:
	docker exec -it $(DB_CONTAINER) /bin/bash

# DynamoDB Admin container shell
.PHONY: shell-db-admin
shell-db-admin:
	docker exec -it $(DB_ADMIN_CONTAINER) /bin/sh

# Logs
.PHONY: logs
logs:
	docker-compose logs -f

.PHONY: logs-api
logs-api:
	docker-compose logs -f api

.PHONY: logs-db
logs-db:
	docker-compose logs -f dynamodb-local

# Docker operations
.PHONY: up
up:
	docker-compose up -d

.PHONY: down
down:
	docker-compose down

.PHONY: restart
restart:
	docker-compose restart

.PHONY: restart-api
restart-api:
	docker-compose restart api

# Build
.PHONY: build
build:
	docker-compose build

.PHONY: rebuild
rebuild:
	docker-compose build --no-cache

# Status
.PHONY: ps
ps:
	docker-compose ps

# Help
.PHONY: help
help:
	@echo "Available commands:"
	@echo "  make shell       - Enter API container shell (default)"
	@echo "  make shell-api   - Enter API container shell"
	@echo "  make shell-db    - Enter DynamoDB container shell"
	@echo "  make shell-db-admin - Enter DynamoDB Admin container shell"
	@echo "  make logs        - Show all container logs"
	@echo "  make logs-api    - Show API container logs"
	@echo "  make logs-db     - Show DynamoDB container logs"
	@echo "  make up          - Start all containers"
	@echo "  make down        - Stop all containers"
	@echo "  make restart     - Restart all containers"
	@echo "  make restart-api - Restart API container only"
	@echo "  make build       - Build containers"
	@echo "  make rebuild     - Rebuild containers (no cache)"
	@echo "  make ps          - Show container status"