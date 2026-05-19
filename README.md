# Portal de Remuneração — SIOPE Jan/Fev 2026

Sistema HTML5 leve para consulta pública dos dados de remuneração dos servidores, pronto para hospedagem no GitHub Pages e incorporação em sites Wix.

## Conteúdo do pacote

```
site/
├── index.html      # Página única — todo o app (HTML + CSS + JS inline, sem build)
├── dados.json      # Base de dados (1,7 MB; ~123 KB com gzip do GitHub Pages)
└── README.md       # Este arquivo
```

## O que o sistema faz

**Aba "Remuneração"** — Tabela paginada e ordenável dos servidores, com filtros:
- **Composição salarial**: todas / apenas com 70% FUNDEB / apenas com Outras Receitas
- **Tipo de Categoria**: Profissional do Magistério / Outros Profissionais da Educação
- **Categoria Profissional** (11 categorias detalhadas)
- **Escola** e busca por nome
- Resumo visual da composição (FUNDEB vs Outras) no topo

**Aba "Professores por Escola"** — Cartões com todas as 45 escolas:
- Total de servidores, magistério vs outros
- Top 3 categorias presentes
- Busca por escola **ou por nome de servidor** (mostra em qual escola está)
- Clique em uma escola abre o detalhe completo com categoria-a-categoria e lista de pessoas

**Aba "Por Categoria"** — Visão tabular cruzando escola × categoria profissional, com contagem por escola e filtros por tipo/categoria.

**Cabeçalho com KPIs** (Janeiro/Fevereiro alternáveis): servidores, folha total, média bruto, cargos e indenizações.


## Origem dos dados

Planilha **SIOPE — Janeiro e Fevereiro 2026** fornecida pela administração municipal. 4.687 registros, 45 escolas, 11 categorias profissionais.
