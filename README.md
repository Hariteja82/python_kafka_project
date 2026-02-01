Here’s a clean **README.md** you can paste directly into your GitHub project.

---

# 📨 Kafka + Python Local Setup Guide

This project demonstrates how to:

1. Create a project directory and Python virtual environment
2. Set up Apache Kafka using Docker Compose
3. Write Python code to produce and consume messages from Kafka

---

## 📁 Step 1 – Create Directory & Python Virtual Environment

### Create Project Folder

```bash
mkdir kafka-python-project
cd kafka-python-project
```

### Create Virtual Environment

```bash
python3 -m venv venv
```

### Activate Virtual Environment

**Linux / macOS**

```bash
source venv/bin/activate
```

**Windows**

```bash
venv\Scripts\activate
```

### Install Required Library

We will use the high-performance Kafka client for Python:

```bash
pip install confluent-kafka
```

(Optional) Save dependencies:

```bash
pip freeze > requirements.txt
```

---

## 🐳 Step 2 – Setup Kafka Using Docker Compose

Create a file named:

```
docker-compose.yml
```

### docker-compose.yml

Please use above Dockaer file

### Start Kafka

```bash
docker compose up -d
```

Verify containers are running:

```bash
docker ps
```

---

## 🧵 Step 3 – Create Kafka Topic

```bash
docker exec -it kafka kafka-topics \
  --create \
  --topic orders \
  --bootstrap-server localhost:9092 \
  --replication-factor 1 \
  --partitions 3
```

Check topics:

```bash
docker exec -it kafka kafka-topics --list --bootstrap-server localhost:9092
```

---

## 🧑‍💻 Step 4 – Python Kafka Producer

Create a file:

```
producer.py
```

Run the producer:

```bash
python producer.py
```

---

## 📥 Step 5 – Python Kafka Consumer

Create a file:

```
tracker.py
```


Run the consumer in another terminal:

```bash
python consumer.py
```

---

## 🔄 Project Workflow

```
Python Producer  →  Kafka Topic (orders)  →  Python Consumer
```

---

## 🧹 Stop Kafka

```bash
docker compose down
```

---

## youtube refaral link:

https://www.youtube.com/watch?v=B7CwU_tNYIE

## 🛠 Tech Stack

* Python 3
* Apache Kafka
* Docker & Docker Compose
* confluent-kafka Python client

---

This setup provides a complete local Kafka environment with Python integration for learning and development.
