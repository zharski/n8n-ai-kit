# Self-hosted AI starter kit

**Self-hosted AI Starter Kit** is an open-source Docker Compose template designed to swiftly initialize a comprehensive local AI and low-code development environment.

Forked from  


### What’s included

✅ [**Self-hosted n8n**](https://n8n.io/) - Low-code platform with over 400
integrations and advanced AI components

✅ [**Ollama**](https://ollama.com/) - Cross-platform LLM platform to install
and run the latest local LLMs

✅ [**Qdrant**](https://qdrant.tech/) - Open-source, high performance vector
store with an comprehensive API

✅ [**PostgreSQL**](https://www.postgresql.org/) -  Workhorse of the Data
Engineering world, handles large amounts of data safely.

✅ [**Redis**](https://redis.io/) -  In-memory data structure store, used for caching and session management


## Installation

### Running n8n using Docker Compose


#### For Mac / Apple Silicon users

If you’re using a Mac with an M1 or newer processor, you can't expose your GPU
to the Docker instance, unfortunately. There are two options in this case:

1. Run the starter kit fully on CPU, like in the section "For everyone else"
   below
2. Run Ollama on your Mac for faster inference, and connect to that from the
   n8n instance

If you want to run Ollama on your mac, check the
[Ollama homepage](https://ollama.com/)
for installation instructions, and run the starter kit as follows:

```
docker compose up -d
```

After you followed the quick start set-up below, change the Ollama credentials
by using `http://host.docker.internal:11434/` as the host.

#### For everyone else

```
docker compose --profile cpu up
```

To open n8n at any time, visit <http://localhost:5678/> in your browser.

## Upgrading

* ### For Nvidia GPU setups:

```bash
docker compose --profile gpu-nvidia pull
docker compose create && docker compose --profile gpu-nvidia up
```

### For Mac / Apple Silicon users

```
docker compose pull
docker compose create && docker compose up
```

* ### For Non-GPU setups:

```bash
docker compose --profile cpu pull
docker compose create && docker compose --profile cpu up
```

## 📜 License

This project is licensed under the Apache License 2.0 - see the
[LICENSE](LICENSE) file for details.
