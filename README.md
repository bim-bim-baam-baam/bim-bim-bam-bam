# Deployment Repository

This repository contains all the necessary services for running the complete application stack. It uses Git submodules to manage the different components and Docker Compose for orchestration.

## Components

- `opto-llm-parser`: LLM parsing service
- `main-service`: Main application service
- `cluster_service`: Cluster management service
- `error-parser`: Error parsing service
- `logwatcher_front`: Frontend application

## Prerequisites

- Git
- Docker
- Docker Compose

## Setup Instructions

1. Clone the repository with submodules:
   ```bash
   git clone --recursive <repository-url>
   cd bim-bim-bam-bam
   ```

2. If you've already cloned the repository without submodules, initialize and update them:
   ```bash
   git submodule init
   git submodule update
   ```

3. Build and start all services:
   ```bash
   docker compose up --build
   ```

   Add `-d` flag to run in detached mode:
   ```bash
   docker compose up --build -d
   ```

4. The frontend application will be available at `http://localhost:3000`

## Managing Services

- To stop all services:
  ```bash
  docker compose down
  ```

- To view logs:
  ```bash
  docker compose logs -f
  ```

- To view logs for a specific service:
  ```bash
  docker compose logs -f <service-name>
  ```

## Updating Services

To update all submodules to their latest versions:
```bash
git submodule update --remote
```

## Troubleshooting

If you encounter any issues:

1. Make sure all submodules are properly initialized and updated
2. Check individual service logs for specific errors
3. Try rebuilding the services:
   ```bash
   docker compose down
   docker compose build --no-cache
   docker compose up
   ``` 