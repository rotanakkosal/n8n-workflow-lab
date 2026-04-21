# n8n with PostgreSQL

This setup starts n8n with PostgreSQL as the database.

## Start

### Run n8n directly (Windows 11 path + file write access)

```bash
docker run -it --rm \
  --name n8n \
  -p 5678:5678 \
  -v n8n_data:/home/node/.n8n \
  -v "D:/CBNU_Classwork/Semester II/Big Data Analysis/assignment/n8n_installation:/home/node/.n8n-files" \
  -e N8N_BLOCK_FS_WRITE_ACCESS=false \
  docker.n8n.io/n8nio/n8n
```

### Run with Docker Compose (PostgreSQL)

Before starting, change the default username and password values in [`.env`](.env).

```bash
docker-compose up -d
```

To stop the services:

```bash
docker-compose stop
```

## Configuration

You can change the default PostgreSQL database name, username, and password in [`.env`](.env).