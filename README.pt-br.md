# 🪱 Worm Case

[![en](https://img.shields.io/badge/lang-en-blue)](README.md)

**Worm Case** é uma convenção de nomenclatura semântica projetada para organizar informações que possuem múltiplas dimensões. Utiliza uma estrutura de **Segmentação Rítmica** para garantir clareza, escaneabilidade e ordenação lógica.

A metáfora por trás do nome vem do movimento de uma minhoca: ela rasteja pelo **solo** e salta em **arco** para avançar. Dessa imagem nasce o **Wormy** 🪱, mascote oficial do padrão. Assim como ele, o Worm Case se estica para acomodar nomes longos e se contrai para nomes curtos, sempre mantendo os pés no solo para saber onde cada pedaço de informação começa e termina.

E é justamente aí que mora a lógica do padrão:

| Caractere | Nome | Função |
|-----------|------|--------|
| `_` (Underscore) | **Solo** | O chão por onde o Wormy rasteja. Separa **Segmentos** — a transição entre diferentes contextos ou metadados (categorias, datas, escopos). |
| `-` (Hífen) | **Arco** | O salto do Wormy sobre a superfície. Separa **Palavras** dentro de um mesmo segmento, mantendo a unidade semântica de uma frase ou título. |

## 🚀 Origem e Motivação

O Worm Case nasceu da necessidade de catalogar e organizar arquivos de forma que a **ordenação alfabética do sistema operacional** trabalhasse a favor do usuário.

### Por que não `kebab-case` ou `snake_case`?

Nas convenções tradicionais, todos os separadores são idênticos — tornando impossível distinguir visualmente onde um contexto termina e outro começa:

```
kebab-case:   relatorio-vendas-anual-2025-final.pdf
snake_case:   relatorio_vendas_anual_2025_final.pdf
```

O olho precisa **ler o nome inteiro** para entender sua estrutura. Não há hierarquia visual — todo separador é igual.

Com o Worm Case, separadores distintos criam **camadas visuais diferentes**, e a estrutura se torna imediatamente escaneável:

```
worm_case:    relatorio_vendas-anual_2025_final.pdf
              ───┬────  ─────┬───── ──┬─  ──┬──
               Tipo     Assunto     Ano   Estado
```

Ao listar os arquivos, o sistema agrupa primeiro pelo **Tipo**, depois pelo **Assunto** e, por fim, pela **Versão/Ano** — tudo graças ao ritmo visual entre `_` e `-`.

## 📖 Anatomia de um Nome

Um nome em Worm Case é composto por **Segmentos** — os blocos de informação:

| Parte | Nome | Descrição | Exemplo |
|-------|------|-----------|---------|
| Segmento 1 | **Contexto / Tipo** | Define o "O Quê" (categoria principal) | `livro`, `api`, `feat` |
| Segmento 2 | **Assunto / Corpo** | Define o "Sobre O Quê" (conteúdo) | `engenharia-software` |
| Segmento 3 | **Atributo / Cauda** | Define o "Detalhe" (versão, data, estado) | `2026`, `v1`, `final` |

## 🎨 Variações de Estilo

O Worm Case se adapta a diferentes convenções através de três variações:

### 1. Lower Worm Case (Standard)

Forma original e recomendada para **sistemas de arquivos** (Windows/Linux/macOS). Utiliza apenas letras minúsculas para evitar conflitos de case-sensitivity.

```
livro_engenharia-software_2ed.pdf
```

### 2. Upper Worm Case (Scream)

Ideal para **constantes de programação**, **variáveis de ambiente** (`.env`) e **configurações globais**.

```
API_TIMEOUT_30-SECONDS
```

### 3. Pascal Worm Case (Mixed)

Mantém a elegância do Pascal Case dentro de cada segmento, preservando a separação de contextos.

```
Profile_Settings
```

## 🛠️ Especificação Técnica (Regex)

Para validar ou implementar o Worm Case em linters e ferramentas de automação:

```regex
^[a-z0-9]+(-[a-z0-9]+)*(_[a-z0-9]+(-[a-z0-9]+)*)*$
```

> **Nota:** esta regex valida o **Lower Worm Case** (standard). Adapte conforme a variação utilizada.

## 📄 Licença

Este projeto está licenciado sob a [MIT License](LICENSE).
