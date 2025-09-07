build:
	docker build -t ghcr.io/redvers/pony-dependency-builder:latest .

push:
	docker push ghcr.io/redvers/pony-dependency-builder:latest

run:
	docker run -it --rm ghcr.io/redvers/pony-dependency-builder:latest bash

prune:
	docker image prune
	docker container prune
	docker volume prune
