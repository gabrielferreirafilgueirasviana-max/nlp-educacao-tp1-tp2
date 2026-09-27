# NLP aplicado à Educação — TP1 e TP2

**Autores:** Gabriel Viana e João Victor

Trabalhos práticos de Processamento de Linguagem Natural sobre avaliações públicas de aplicativos de instituições de ensino superior brasileiras (EAD) na Google Play Store.

| Trabalho | Notebook | Abrir no Colab |
|---|---|---|
| **TP1** — Pipeline de engenharia de textos e pré-processamento | [`TP1_Pipeline_NLP_Educacao.ipynb`](TP1_Pipeline_NLP_Educacao.ipynb) | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/gabrielferreirafilgueirasviana-max/nlp-educacao-tp1-tp2/blob/main/TP1_Pipeline_NLP_Educacao.ipynb) |
| **TP2** — Motores de busca léxico (TF-IDF) e semântico (Word2Vec) | [`TP2_Motores_Busca_TFIDF_Word2Vec.ipynb`](TP2_Motores_Busca_TFIDF_Word2Vec.ipynb) | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/gabrielferreirafilgueirasviana-max/nlp-educacao-tp1-tp2/blob/main/TP2_Motores_Busca_TFIDF_Word2Vec.ipynb) |

### Redes Neurais Artificiais

Trabalho de outra disciplina, construído sobre o mesmo corpus: os textos são convertidos em atributos tabulares para treinar uma rede MLP que identifica alunos insatisfeitos.

| Trabalho | Notebook | Abrir no Colab |
|---|---|---|
| **TP2** — MultiDense Engine: MLP em TensorFlow/Keras | [`multidense_engine.ipynb`](multidense_engine.ipynb) | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/gabrielferreirafilgueirasviana-max/nlp-educacao-tp1-tp2/blob/main/multidense_engine.ipynb) |

## Corpus

[`corpus_educacao_bruto.csv`](corpus_educacao_bruto.csv) — 2.452 avaliações de 9 instituições, coletadas pelo TP1 e já higienizadas estruturalmente (sem textos vazios, duplicados ou com menos de 20 caracteres).

| Coluna | Conteúdo |
|---|---|
| `instituicao` | Instituição dona do aplicativo |
| `app_id` | Identificador do pacote na Play Store |
| `nota` | Nota da avaliação (1 a 5 estrelas) |
| `data` | Data e hora da avaliação |
| `texto` | Texto livre escrito pelo aluno |

O TP1 coleta as avaliações ao vivo, ordenadas pelas mais recentes, então cada execução da coleta traz um conjunto diferente. Este arquivo é a versão **congelada** do corpus: o TP2 carrega os dados diretamente dele pelo link *raw* do GitHub, o que garante que os resultados sejam idênticos em qualquer execução.

## Como executar o TP2

1. Clique em **Abrir no Colab** na tabela acima.
2. Menu **Ambiente de execução → Executar tudo**.

O notebook instala as dependências, lê o CSV deste repositório e baixa o modelo Word2Vec do NILC (skip-gram, 300 dimensões, ~1,1 GB) do [Hugging Face](https://huggingface.co/nilc-nlp/word2vec-skip-gram-300d). A execução completa leva poucos minutos.
