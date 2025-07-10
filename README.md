### Nom et Prenom : KHALLOU Nawfal
### Filiere : MSDIA
# 🧠 Projet MCP - Intégration Spring Boot & Python

Ce projet présente une architecture simple et efficace permettant la communication entre un **client Java (Spring Boot)** et un **serveur Python**, à travers le **Model Context Protocol (MCP)**. L'intelligence artificielle (IA) est alimentée localement par le modèle **Mistral** via **Ollama**.

---

## 🎯 Objectifs

- Permettre à une IA de dialoguer avec l’utilisateur via une API REST
- Intégrer des outils comme la gestion de fichiers, d'entreprises ou d’employés
- Montrer comment Spring Boot peut consommer les services d’un serveur Python avec MCP
- Utiliser un modèle IA local pour garantir la confidentialité et l’autonomie

---

## 🏗️ Composants

### 1. **Client Spring Boot**
- Gère les requêtes de l'utilisateur
- Dialogue avec le serveur MCP via SSE
- Intègre l’IA locale via Ollama

### 2. **Serveur MCP Python**
- Implémente les outils accessibles par l’IA
- Répond aux requêtes du client via MCP

### 3. **Modèle IA Mistral via Ollama**
- Chargé localement
- Sert de moteur de raisonnement de l’IA

---

## 🔧 Prérequis

- Java 17+
- Maven
- Python 3.8+
- Ollama installé : https://ollama.ai

---

## 🚀 Démarrage rapide

### 1. Démarrer Ollama avec Mistral

```bash
ollama serve
ollama pull mistral
````

### 2. Lancer le serveur Python

```bash
cd mcp-server-python
.venv\Scripts\activate      # Sous Windows
# source .venv/bin/activate  # Sous Linux/macOS

pip install -r requirements.txt
python server.py
```

### 3. Lancer le client Spring Boot

```bash
cd mcp-client
./mvnw spring-boot:run
```

---

## 🧪 Exemple d'utilisation

Une fois les services démarrés :

* Requête vers l’IA :

  ```
  http://localhost:8066/chat?query=Bonjour
  ```
* Exemples de questions possibles :

    * "Quels fichiers sont disponibles ?"
    * "Liste les employés enregistrés"
    * "Que sais-tu sur l'entreprise Orange ?"

---

## ⚙️ Configuration principale

### Fichier `application.properties`

```properties
server.port=8066

# Serveur MCP
spring.ai.mcp.client.sse.connections.server1.url=http://localhost:8899
spring.ai.mcp.client.sse.connections.server1.sse-endpoint=/sse

# Modèle IA via Ollama
spring.ai.ollama.base-url=http://localhost:10000
spring.ai.ollama.chat.model=mistral
```

---

## 📁 Arborescence simplifiée

```
mcp-project/
├── mcp-client/           # Application Spring Boot
├── mcp-server/           # Serveur Spring optionnel
├── mcp-server-python/    # Serveur Python avec outils MCP
└── README.md
```

---

## 🧰 Technologies utilisées

* **Spring Boot 3.x**
* **Java 17**
* **Python 3.x**
* **Ollama** + **Mistral**
* **MCP Protocol**
* **REST API** et **SSE**

---



