# Engineering

## Infrastructure Comparision

### Model Serving

| Infrastructure | Minimum Setup                                            | Min Scale                | Maximum Setup                                               | Max Scale                | Costs                                    |
| -------------- | -------------------------------------------------------- | ------------------------ | ----------------------------------------------------------- | ------------------------ | ---------------------------------------- |
| vLLM           | 1x GPU (24GB VRAM), 32GB RAM, 8 CPU cores, 100GB storage | ~100 concurrent requests | 8x A100 80GB GPUs, 1TB RAM, 128 CPU cores, 2TB NVMe storage | ~10k concurrent requests | 3090ti (0.20 USD/hr, vast.ai) $144/month |
| LMCache        | 8GB RAM, 100GB storage                                   | ~100k cached responses   | 256GB RAM, 10TB storage                                     | ~100M cached responses   | $20/month (cloud storage)                |
| FastAPI        | 2GB RAM, 2 CPU cores                                     | ~1k requests/sec         | 32GB RAM, 32 CPU cores                                      | ~50k requests/sec        | $10/month (shared hosting)               |
| ComfyUI        | 1x GPU (8GB VRAM), 16GB RAM, 4 CPU cores                 | ~10 concurrent users     | 4x GPUs (24GB+ VRAM each), 128GB RAM, 32 CPU cores          | ~500 concurrent users    | 3070 (0.08 USD/hr, vast.ai) $58/month    |
| TorchServe     | 16GB RAM, 8 CPU cores                                    | ~100 requests/sec        | 4x GPUs, 256GB RAM, 64 CPU cores                            | ~10k requests/sec        | 3070 (0.08 USD/hr, vast.ai) $58/month    |
| Triton         | 1x GPU, 32GB RAM, 16 CPU cores                           | ~1k requests/sec         | 8x A100 GPUs, 1TB RAM, 128 CPU cores                        | ~100k requests/sec       | A100 (0.60 USD/hr, vast.ai) $432/month   |
| Ollama         | 8GB RAM, 1x GPU (8GB VRAM, optional), 50GB storage       | ~10 concurrent requests  | 128GB RAM, 2x GPUs (24GB+ VRAM), 1TB storage                | ~200 concurrent requests | 3070 (0.08 USD/hr, vast.ai) $58/month    |

### Load Balancing & Routing

| Infrastructure | Minimum Setup                       | Min Scale                    | Maximum Setup                           | Max Scale                  | Costs                         |
| -------------- | ----------------------------------- | ---------------------------- | --------------------------------------- | -------------------------- | ----------------------------- |
| NGINX          | 1GB RAM, 1 CPU core, 1Gbps network  | ~100k concurrent connections | 8GB RAM, 8 CPU cores, 40Gbps network    | ~2M concurrent connections | $10/month (shared hosting)    |
| HAProxy        | 1GB RAM, 2 CPU cores, 1Gbps network | ~200k concurrent connections | 16GB RAM, 16 CPU cores, 100Gbps network | ~3M concurrent connections | $20/month (dedicated hosting) |

### Caching & Storage

| Infrastructure | Minimum Setup                                       | Min Scale         | Maximum Setup                                           | Max Scale       | Costs                                  |
| -------------- | --------------------------------------------------- | ----------------- | ------------------------------------------------------- | --------------- | -------------------------------------- |
| Redis          | 8GB RAM, 4 CPU cores, 1Gbps network                 | ~100k ops/sec     | 256GB RAM, 8 CPU cores, 40Gbps network                  | ~2M ops/sec     | $10/month (shared hosting)             |
| PostgreSQL     | 16GB RAM, 8 CPU cores, 1TB storage, 10Gbps network  | ~10k txns/sec     | 1TB RAM, 64 CPU cores, 100TB storage, 100Gbps network   | ~200k txns/sec  | $20/month (dedicated hosting)          |
| MinIO          | 8GB RAM, 8 CPU cores, 100TB storage, 10Gbps network | ~100TB data       | 64GB RAM, 32 CPU cores, 10PB storage, 100Gbps network   | ~10PB data      | $50/month (object storage)             |
| MongoDB        | 16GB RAM, 8 CPU cores, 1TB storage, 10Gbps network  | ~50k ops/sec      | 512GB RAM, 32 CPU cores, 100TB storage, 100Gbps network | ~500k ops/sec   | $30/month (dedicated hosting)          |
| Milvus         | 32GB RAM, 16 CPU cores, 1TB storage                 | ~100M vectors     | 512GB RAM, 64 CPU cores, 100TB storage, 4x A100 GPU     | ~10B vectors    | A100 (0.60 USD/hr, vast.ai) $432/month |
| Memgraph       | 32GB RAM, 8 CPU cores, 100GB storage                | ~100M nodes/edges | 512GB RAM, 32 CPU cores, 10TB storage                   | ~5B nodes/edges | $40/month (dedicated hosting)          |

### Monitoring & Logging

| Infrastructure | Minimum Setup                      | Min Scale                              | Maximum Setup                         | Max Scale                                | Costs                         |
| -------------- | ---------------------------------- | -------------------------------------- | ------------------------------------- | ---------------------------------------- | ----------------------------- |
| Prometheus     | 16GB RAM, 8 CPU cores, 1TB storage | ~1M time series with 15 day retention  | 256GB RAM, 16 CPU cores, 10TB storage | ~10M time series with 1 year retention   | $30/month (dedicated hosting) |
| Grafana        | 2GB RAM, 2 CPU cores, 50GB storage | ~100 concurrent users, 1000 dashboards | 8GB RAM, 4 CPU cores, 500GB storage   | ~5000 concurrent users, 10000 dashboards | $10/month (shared hosting)    |
| Loki           | 8GB RAM, 4 CPU cores, 1TB storage  | ~100GB logs/day                        | 32GB RAM, 8 CPU cores, 50TB storage   | ~5TB logs/day                            | $20/month (dedicated hosting) |

### Message Queue & Streaming

| Infrastructure | Minimum Setup                                       | Min Scale          | Maximum Setup                                                                          | Max Scale          | Costs                         |
| -------------- | --------------------------------------------------- | ------------------ | -------------------------------------------------------------------------------------- | ------------------ | ----------------------------- |
| Kafka          | 32GB RAM, 16 CPU cores, 1TB storage, 10Gbps network | ~100k messages/sec | 128GB RAM per broker, 32 CPU cores per broker, 10TB storage per broker, 40Gbps network | ~5M messages/sec   | $50/month (dedicated hosting) |
| RabbitMQ       | 8GB RAM, 4 CPU cores, 100GB storage, 1Gbps network  | ~10k messages/sec  | 32GB RAM per node, 8 CPU cores per node, 1TB storage per node, 10Gbps network          | ~200k messages/sec | $20/month (dedicated hosting) |

### UI & Interaction

| Infrastructure | Minimum Setup                                          | Min Scale             | Maximum Setup                                                | Max Scale             | Costs                                 |
| -------------- | ------------------------------------------------------ | --------------------- | ------------------------------------------------------------ | --------------------- | ------------------------------------- |
| OpenWebUI      | 2GB RAM, 2 CPU cores, 10GB storage                     | ~100 concurrent users | 16GB RAM, 8 CPU cores, 100GB storage                         | ~2k concurrent users  | $10/month (shared hosting)            |
| Automatic1111  | 1x GPU (8GB VRAM), 16GB RAM, 4 CPU cores, 50GB storage | ~10 concurrent users  | 4x GPUs (24GB+ VRAM), 128GB RAM, 32 CPU cores, 500GB storage | ~500 concurrent users | 3070 (0.08 USD/hr, vast.ai) $58/month |
| ComfyUI        | 1x GPU (8GB VRAM), 16GB RAM, 4 CPU cores               | ~10 concurrent users  | 4x GPUs (24GB+ VRAM), 128GB RAM, 32 CPU cores                | ~500 concurrent users | 3070 (0.08 USD/hr, vast.ai) $58/month |
| Fooocus        | 1x GPU (8GB VRAM), 16GB RAM, 4 CPU cores, 20GB storage | ~5 concurrent users   | 2x GPUs (24GB+ VRAM), 64GB RAM, 16 CPU cores, 200GB storage  | ~100 concurrent users | 3070 (0.08 USD/hr, vast.ai) $58/month |

### Infrastructure

| Infrastructure | Minimum Setup                                                                                                                         | Min Scale                      | Maximum Setup                                                                                                                             | Max Scale                       | Costs                         |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------- | ----------------------------- |
| Kubernetes     | Control plane: 4GB RAM, 2 CPU cores, 50GB storage; Worker nodes (2-3): 8GB RAM per node, 4 CPU cores per node, 100GB storage per node | ~100 containers across cluster | Control plane: 16GB RAM, 8 CPU cores, 500GB storage; Worker nodes (1000+): 64GB RAM per node, 32 CPU cores per node, 1TB storage per node | ~100k containers across cluster | $50/month (dedicated hosting) |

### Security

| Infrastructure | Minimum Setup                       | Min Scale          | Maximum Setup                       | Max Scale            | Costs                         |
| -------------- | ----------------------------------- | ------------------ | ----------------------------------- | -------------------- | ----------------------------- |
| Vault          | 8GB RAM, 4 CPU cores, 100GB storage | ~5k operations/sec | 32GB RAM, 8 CPU cores, 1TB storage  | ~100k operations/sec | $20/month (dedicated hosting) |
| Cert-Manager   | 512MB RAM, 1 CPU core, 10GB storage | ~500 certificates  | 2GB RAM, 2 CPU cores, 100GB storage | ~10k certificates    | $5/month (shared hosting)     |

### Model Optimization

| Infrastructure | Minimum Setup                               | Min Scale           | Maximum Setup                                       | Max Scale           | Costs                                  |
| -------------- | ------------------------------------------- | ------------------- | --------------------------------------------------- | ------------------- | -------------------------------------- |
| ONNX           | 16GB RAM, 8 CPU cores                       | ~100 inferences/sec | 2x GPUs with 16GB+ VRAM, 128GB RAM, 32 CPU cores    | ~10k inferences/sec | 3070 (0.08 USD/hr, vast.ai) $58/month  |
| TensorRT       | 1x GPU with 8GB VRAM, 32GB RAM, 8 CPU cores | ~500 inferences/sec | 4x A100 GPUs, 256GB RAM, 64 CPU cores               | ~50k inferences/sec | A100 (0.60 USD/hr, vast.ai) $432/month |
| OpenVINO       | 16GB RAM, 8 CPU cores                       | ~200 inferences/sec | 128GB RAM, 32 CPU cores, Intel Neural Compute Stick | ~5k inferences/sec  | $30/month (dedicated hosting)          |

## All feature Infrastructure for Full-Stack AI System

### Physical Infrastructure

| Component          | Specifications                                                                              | Monthly Cost                                                 | Purpose                                  |
| ------------------ | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------ | ---------------------------------------- |
| Primary GPU Server | 2x RTX 3090 Ti (24GB VRAM each), 256GB RAM, 64 CPU cores, 10TB NVMe storage, 40Gbps network | $288 (GPU: 2x 0.20 USD/hr on vast.ai) + $150 (server) = $438 | AI Model Serving, Training, Optimization |
| Database Server    | 64GB RAM, 16 CPU cores, 2TB NVMe storage, 10Gbps network                                    | $80/month                                                    | Databases, Caching, Storage              |
| Application Server | 32GB RAM, 8 CPU cores, 1TB storage, 10Gbps network                                          | $50/month                                                    | Kubernetes, Message Queues, Monitoring   |
| Frontend Server    | 16GB RAM, 4 CPU cores, 500GB storage, 10Gbps network                                        | $30/month                                                    | Load Balancing, UI Services, API Gateway |

Total Base Infrastructure Cost: ~$598/month

### Service Distribution & Resource Usage

1. Primary GPU Server ($438/month):

    - Model Serving (Uses ~80% GPU, 60% RAM, 40% CPU):
        - vLLM: 1x 3090 Ti (24GB VRAM), 100GB RAM, 24 CPU cores - $175/month
        - ComfyUI/Automatic1111/Fooocus: 1x 3090 Ti (24GB VRAM), 50GB RAM, 16 CPU cores - $175/month
        - TorchServe/Triton: Shares GPU resources, 30GB RAM, 8 CPU cores - $44/month
        - Ollama: Shares GPU resources, 20GB RAM, 4 CPU cores - $22/month
    - Model Optimization (Uses ~20% GPU, 20% RAM, 40% CPU):
        - ONNX Runtime: Shares GPU resources, 20GB RAM, 4 CPU cores - $8/month
        - TensorRT: Shares GPU resources, 20GB RAM, 4 CPU cores - $8/month
        - OpenVINO: 16GB RAM, 4 CPU cores - $6/month

2. Database Server ($80/month):

    - Storage & Caching (Resource allocation of total server):
        - MongoDB: 25% (16GB RAM, 4 CPU cores, 500GB storage) - $20/month
        - Milvus: 25% (16GB RAM, 4 CPU cores, 500GB storage) - $20/month
        - Memgraph: 15% (10GB RAM, 2 CPU cores, 300GB storage) - $12/month
        - Redis: 10% (6GB RAM, 2 CPU cores, 200GB storage) - $8/month
        - PostgreSQL: 15% (10GB RAM, 2 CPU cores, 300GB storage) - $12/month
        - MinIO: 10% (6GB RAM, 2 CPU cores, 200GB storage) - $8/month

3. Application Server ($50/month):

    - Infrastructure (40% resources):
        - Kubernetes control plane: 8GB RAM, 2 CPU cores - $10/month
        - Worker nodes: 4GB RAM, 2 CPU cores each - $10/month
    - Messaging (30% resources):
        - Kafka: 10GB RAM, 2 CPU cores - $15/month
        - RabbitMQ: 2GB RAM, 1 CPU core - $5/month
    - Monitoring (20% resources):
        - Prometheus: 4GB RAM, 1 CPU core - $4/month
        - Grafana: 2GB RAM, 0.5 CPU core - $3/month
        - Loki: 2GB RAM, 0.5 CPU core - $3/month
    - Security (10% resources):
        - Vault: 2GB RAM, 0.5 CPU core - $2/month
        - Cert-Manager: 0.5GB RAM, 0.25 CPU core - $1/month

4. Frontend Server ($30/month):
    - Load Balancing (40% resources):
        - NGINX: 4GB RAM, 1 CPU core - $6/month
        - HAProxy: 4GB RAM, 1 CPU core - $6/month
    - UI Services (60% resources):
        - OpenWebUI: 4GB RAM, 1 CPU core - $6/month
        - FastAPI endpoints: 2GB RAM, 0.5 CPU core - $6/month
        - LMCache: 2GB RAM, 0.5 CPU core - $6/month

### Minimum Scale Capabilities

-   Model Serving: ~100 concurrent requests
-   Vector Storage: ~100M vectors
-   Graph Processing: ~100M nodes/edges
-   Message Queue: ~10k messages/sec
-   Monitoring: ~1M time series
-   Load Balancing: ~100k connections
-   Object Storage: ~100TB data
-   Database Ops: ~10k transactions/sec
-   UI Handling: ~50 concurrent users

## Ultra Minimal Setup ($254/month total)

1. Core Server ($144/month):

    Single GPU instance with:

    - 1x RTX 3090 (24GB VRAM)
    - 64GB RAM
    - 16 CPU cores
    - 500GB NVMe storage

    Running:

    - vLLM: 24GB VRAM, 32GB RAM, 8 CPU cores - $144/month (3090ti @ 0.20 USD/hr)
    - ComfyUI: Shares GPU, 16GB RAM, 4 CPU cores - Shared cost
    - OpenWebUI: 8GB RAM, 2 CPU cores - $10/month
    - FastAPI endpoints: 4GB RAM, 1 CPU core - $10/month
    - LMCache: 4GB RAM, 1 CPU core - $20/month

2. Database Server ($70/month):

    Single instance with:

    - 32GB RAM
    - 8 CPU cores
    - 250GB storage

    Running:

    - Milvus: 16GB RAM, 4 CPU cores, 100GB storage - $30/month
    - PostgreSQL: 8GB RAM, 2 CPU cores, 100GB storage - $20/month
    - RabbitMQ: 8GB RAM, 2 CPU cores, 50GB storage - $20/month

3. Support Server ($40/month):

    Single instance with:

    - 16GB RAM
    - 4 CPU cores
    - 100GB storage

    Running:

    - NGINX: 4GB RAM, 1 CPU core - $10/month
    - Grafana + Loki + Prometheus (all-in-one): 12GB RAM, 3 CPU cores - $30/month

### Minimal Scale Capabilities:

-   Model Inference: ~50 concurrent requests
-   Vector Search: ~10M vectors
-   Message Queue: ~5k messages/sec
-   Database: ~5k transactions/sec
-   Monitoring: ~100k time series
-   Load Balancing: ~50k connections
-   UI: ~25 concurrent users

# Best open source models (as of 13/11/2024)

-   All llms are quantized to 4 bits (q4_k_m)
-   GPUs that are chosen have a min 20GB/s GPU RAM Bandwidth and max 16 CPU cores

### Text gen models (multimodal input - images, audio)

-   qwen32B (24GB)
-   3090ti = 0.20 usd/hr on vast.ai
-   144 usd/month (12k inr/month)

### Image gen models

-   stable-diffusion-3.5-large-turbo (5.27GB)
-   3070 = 0.08 usd/hr on vast.ai

### Audio gen models

-   xtts v2 (1.8GB)
-   3070 = 0.08 usd/hr on vast.ai

### Video gen models

-   [tencent](https://github.com/Tencent/HunyuanVideo) (80 GB)
-   mochi 1 (40GB)
-   A100 0.6 usd/hr on vast.ai
