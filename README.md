 🤖 Chatbot Inteligente com Evolution API, LangChain, Docker, Buffer, VectorStore e FastAPI

Este projeto é um chatbot inteligente que integra processamento de linguagem natural com capacidades de memória, contexto e busca vetorial. A aplicação combina o poder da **Evolution API** com o **LangChain**, utilizando **FastAPI** para servir as requisições e **Docker** para facilitar a implantação. O sistema usa **Buffer** para controle de contexto e um **VectorStore** para buscas semânticas em grandes volumes de dados.

---

##  Tecnologias Utilizadas

- **Evolution API**: Framework para desenvolvimento de agentes de IA e integração com fontes de dados externas.
- **LangChain**: Biblioteca para orquestração de LLMs com ferramentas de memória, contextos e agentes.
- **Docker**: Containerização da aplicação para garantir portabilidade e consistência no ambiente.
- **FastAPI**: Framework leve e rápido para criação de APIs modernas com Python.
- **Buffer**: Para controle de histórico de mensagens no chat.
- **VectorStore**: Armazenamento vetorial (ex: FAISS, Chroma ou Weaviate) usado para embasamento de respostas.

---

## 📂 Estrutura do Projeto

chatbot-evolution/
│
├── app/
│ ├── main.py # API principal (FastAPI)
│ ├── chains/ # Arquivos de chains do LangChain
│ ├── agents/ # Agentes customizados
│ ├── memory/ # Implementações de Buffer e contexto
│ └── vectorstore/ # Setup e queries vetoriais
│
├── docker/
│ ├── Dockerfile # Imagem principal
│ └── docker-compose.yml # Orquestração de serviços (API, DB, VectorStore)
│
├── .env # Variáveis de ambiente
├── requirements.txt # Dependências Python
└── README.md # Este arquivo

yaml
Copiar
Editar

---

## ⚙️ Instalação e Execução Local

### 1. Pré-requisitos

- Docker instalado
- Docker Compose
- Python 3.10+

### 2. Clone o repositório

```bash
git clone https://github.com/seu-usuario/chatbot-evolution.git
cd chatbot-evolution
3. Configuração de ambiente
Crie um arquivo .env com suas chaves da Evolution API e outras configurações:

env
Copiar
Editar
EVOLUTION_API_KEY=your_key_here
VECTORSTORE_PATH=/vector_db/
LANGCHAIN_API_KEY=...
4. Suba os containers com Docker Compose
bash
Copiar
Editar
docker-compose up --build
A API ficará disponível em http://localhost:8000.

 Como Treinar o Chatbot
Prepare seus dados base (documentos, FAQs, PDFs, textos).

Use o script vectorstore/load_data.py para indexar os documentos com embeddings.

Os vetores são armazenados em uma base compatível (ex: FAISS ou Chroma).

O agente usa a base vetorial para consultas semânticas durante a conversa.

 Dificuldades Enfrentadas
Instalação do Docker em ambientes Windows com WSL.

Integração da Evolution API com os handlers do LangChain exigiu adaptações na lógica de agentes.

Gerenciamento de memória de contexto usando Buffer e token limit dos LLMs.

Armazenamento vetorial requer otimização para garantir performance em bases grandes.

Deploy em ambientes de produção exige configuração adicional de volume, segurança de tokens e autoscaling.

📈 Escalabilidade
Este projeto foi pensado para escalar em ambientes de alta demanda:

Docker facilita a replicação em clusters (ex: Kubernetes).

A FastAPI pode ser executada com Uvicorn e Gunicorn para múltiplas instâncias.

O uso de VectorStore desacoplado (via banco ou API) permite atualização dinâmica da base.

Integração futura com Redis ou Kafka para cache e fila de tarefas.

Evolution API permite extensão com múltiplos agentes independentes e módulos conectados.

 Contato
Para sugestões, dúvidas ou colaborações:

Henrique Claudino
LinkedIn | Email: contato@henriqueclaudino.com.br

