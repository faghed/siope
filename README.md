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

## Como hospedar no GitHub Pages

1. Crie um repositório público no GitHub (ex: `portal-remuneracao`).
2. Faça upload dos três arquivos da pasta `site/` para a raiz.
3. Em **Settings → Pages**, selecione a branch `main` e a pasta `/ (root)`. Salve.
4. Em ~1 minuto o site fica em `https://SEU-USUARIO.github.io/portal-remuneracao/`.
5. Abra `index.html` e confirme que a constante `DATA_URL` no script aponta para `./dados.json` (já está configurado assim — funciona direto do mesmo diretório).

> **Atualização de dados**: para trocar pela próxima planilha, basta substituir `dados.json` no repositório. O HTML não precisa mudar.

## Como incorporar no Wix

No editor do Wix:

1. **Adicionar → Incorporar → Incorporar HTML** (ou "Incorporar um site").
2. Escolha **"Site"** (não "Código") e cole a URL:
   `https://SEU-USUARIO.github.io/portal-remuneracao/`
3. Ajuste o tamanho do iframe (recomendado: largura 100% do container, altura mínima ~1400px). O layout é responsivo.
4. Para uma incorporação mais limpa, use o componente **HTML iFrame** com:
   ```html
   <iframe src="https://SEU-USUARIO.github.io/portal-remuneracao/"
           style="width:100%;height:1500px;border:0"
           loading="lazy"></iframe>
   ```

## Performance

- O JSON tem ~1,7 MB e é compactado automaticamente pelo GitHub Pages para ~123 KB (gzip).
- A renderização é totalmente client-side com paginação (25 linhas/página) — fluida mesmo com 4.687 registros.
- Sem dependências externas além do Google Fonts (Inter + Manrope).

## Personalização rápida

No CSS, no topo do `index.html`, ajuste as variáveis:

```css
--blue: #2342C8;   /* cor primária */
--red:  #E63946;   /* cor de destaque (folha, indenizações) */
```

## Origem dos dados

Planilha **SIOPE — Janeiro e Fevereiro 2026** fornecida pela administração municipal. 4.687 registros, 45 escolas, 11 categorias profissionais.
