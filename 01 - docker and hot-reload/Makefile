.PHONY: all build clean run

# Variables
BUILD_DIR=bin/
BINARY_NAME=$(BUILD_DIR)api
DOCKER_IMAGE_NAME=api
MAIN_FILE_PATH=cmd/api/main.go

# Comando para construir la aplicación
build:
	@echo "Construyendo la aplicación..."
	go build -o $(BINARY_NAME) $(MAIN_FILE_PATH)

# Comando para limpiar los archivos generados
clean:
	@echo "Limpiando..."
	go clean
	rm -r $(BUILD_DIR)

# Comando para correr la aplicación
run: build
	@echo "Corriendo la aplicación..."
	./$(BINARY_NAME)

# Comando para construir una imagen Docker
docker-build:
	@echo "Construyendo la imagen Docker..."
	docker build -t $(DOCKER_IMAGE_NAME) .

# Comando para correr la aplicación en un contenedor Docker
docker-run: docker-build
	@echo "Corriendo la aplicación en un contenedor Docker..."
	docker run -p 8080:8080 $(DOCKER_IMAGE_NAME)