# Project Name

## Overview

This project uses Docker and Docker Compose to set up and run the following services:

1. **ChromaDB**: A database service running on port `8099`.
2. **Chroma UI**: A Next.js application that provides a user interface for interacting with ChromaDB, running on port `8088`.

## Getting Started

To get started with ChromaDB, follow these steps:

1. Start the services using Docker Compose:

   ```shell
   docker-compose up -d
   ```

2. Wait for the services to start up. You can check the logs to see the progress:

   ```shell
   docker-compose logs -f
   ```

3. Once the services are up and running, you can access ChromaDB UI by opening your browser and navigating to [http://localhost:8088](http://localhost:8088).

## Configuration

ChromaDB can be configured using environment variables. The following variables are available:

- `CHROMADB_PORT`: The port on which ChromaDB should listen. Default is `8099`.
- `CHROMAUI_PORT`: The port on which Chroma UI should listen. Default is `8088`.

You can set these variables in the `.env` file located in the `chromadb` directory.
