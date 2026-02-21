# RAG Day 2 - Naive RAG Class

Aula prática do **Dia 2** do curso **AI Engineering Academy**, onde implementamos um pipeline completo de **Naive RAG (Retrieval-Augmented Generation)** do zero, sem frameworks abstratos como LangChain.

## O que vamos construir?

Um sistema que segue o pipeline clássico de RAG:

```
Ingestão → Chunking → Embeddings → Armazenamento → Recuperação → Geração
```

1. **Carrega** documentos (PDF, TXT, Markdown)
2. **Fragmenta** o texto em chunks com estratégia recursiva
3. **Gera** embeddings vetoriais via OpenAI API
4. **Armazena** os vetores no ChromaDB
5. **Recupera** contexto relevante por similaridade de cosseno
6. **Gera** respostas usando LLM (GPT-4o-mini)

## Estrutura do Projeto

```
naive-rag-class/
├── naive_rag_tutorial.ipynb   # Notebook principal com o tutorial completo
├── class.pdf                  # Slides da aula
└── README.md
```

## Pre-requisitos

- Python 3.10+
- Chave de API da OpenAI ([obter aqui](https://platform.openai.com/api-keys))

## Instalacao

```bash
pip install openai pypdf chromadb
```

Configure a variavel de ambiente com sua chave:

```bash
export OPENAI_API_KEY="sua-chave-aqui"
```

## Conteudo do Tutorial

O notebook `naive_rag_tutorial.ipynb` cobre as seguintes etapas:

| Parte | Tema | Descricao |
|-------|------|-----------|
| 1 | Instalacao | Dependencias essenciais |
| 2 | Configuracao | Setup da API OpenAI |
| 3 | Ingestao | Carregamento de documentos (PDF/TXT/MD) com limpeza basica |
| 4 | Chunking | Fragmentacao recursiva com controle de `chunk_size` e `overlap` |
| 5 | Embeddings | Vetorizacao com `text-embedding-3-small` da OpenAI |
| 6 | Armazenamento | Indexacao no ChromaDB com similaridade de cosseno (HNSW) |
| 7 | Recuperacao | Busca semantica Top-k com scoring de similaridade |
| 8 | Geracao | Prompt engineering com contexto recuperado + GPT-4o-mini |
| 9 | Pipeline Completo | Funcao `naive_rag_pipeline()` integrando todas as etapas |
| 10 | Testes | Bateria de perguntas para validar o sistema |

## Tecnologias Utilizadas

- **OpenAI API** - Embeddings (`text-embedding-3-small`) e LLM (`gpt-4o-mini`)
- **ChromaDB** - Banco de dados vetorial local com persistencia em disco
- **PyPDF** - Extracao de texto de arquivos PDF

## Como Executar

1. Clone o repositorio
2. Instale as dependencias
3. Configure sua `OPENAI_API_KEY`
4. Abra o notebook e execute as celulas sequencialmente:

```bash
jupyter notebook naive_rag_tutorial.ipynb
```
