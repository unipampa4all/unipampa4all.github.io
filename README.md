# unipampa4all.github.io

Site de páginas úteis para a comunidade da UNIPAMPA, publicado em <https://unipampa4all.github.io/>.

Cada página é um guia prático de um procedimento: o fluxo, os documentos exigidos, a base normativa de cada etapa e os links oficiais, reunidos em um lugar só.

Este site é mantido pela comunidade e **não é um canal oficial da UNIPAMPA**. Nenhuma página substitui a leitura das normas nem a consulta aos setores responsáveis.

## Páginas

| Página | Área | Última revisão |
| --- | --- | --- |
| [Formalização de projetos com empresas e instituições](https://unipampa4all.github.io/nrfa/) | Administrativo | setembro de 2026 |

## Estrutura

```
/
├── index.html              índice do site, lista as páginas
├── nrfa/index.html         guia de formalização com fundações de apoio
├── 404.html                página de erro, servida pelo GitHub Pages
├── assets/
│   ├── favicon.svg
│   └── css/
│       ├── site.css        tokens, tipografia e componentes de todas as páginas
│       └── nrfa.css        estilo exclusivo de /nrfa/
├── README.md
└── LICENSE
```

Não há etapa de build. O GitHub Pages serve os arquivos como estão, e qualquer `.html` também abre localmente com duplo clique.

## Como adicionar uma página

1. Crie a pasta `minha-pagina/` e dentro dela um `index.html`, para a URL ficar `/minha-pagina/` sem extensão.
2. No `<head>`, carregue as fontes, depois `../assets/css/site.css` e, se precisar, um `../assets/css/minha-pagina.css` só com o que for exclusivo dela.
3. Copie a `div.sitebar` de `nrfa/index.html` e troque o texto de `span.cur` pelo nome da nova página.
4. Monte o conteúdo com os componentes que já existem em `site.css`: `.steps` para passos numerados, `.callout` para destaques, `.tbox` para tabelas, `.linklist` para listas de links com etiqueta, `.flow` para fluxograma em SVG, `.figbox` para envolver figura larga.
5. Adicione o cartão da página em `index.html`, dentro de `div.pages`, e a linha correspondente na tabela deste README.

### Convenções que importam

- **Use caminhos relativos** (`../assets/...`), nunca absolutos. Absoluto quebra a abertura local pelo protocolo `file://`. A única exceção é o `404.html`, e o motivo está comentado no próprio arquivo.
- **Nunca crie um diretório chamado `src/`.** O `.gitignore` já teve uma regra que o ignorava, herdada de outro projeto. A regra foi removida, mas o nome continua sendo má escolha para este repositório.
- **Todo token de cor é declarado no `:root` sem condição** em `site.css`. Os blocos de tema escuro apenas redefinem tokens existentes. Declarar uma cor só dentro de um `@media` faz a página renderizar texto de um tema sobre o fundo do outro.
- **Datas por extenso e sem abreviação ambígua**, e sempre atualize a última revisão quando mexer no conteúdo de um guia.

## Licença

[Apache 2.0](LICENSE)
