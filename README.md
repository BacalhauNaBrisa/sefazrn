# Sefaz/RN · Auditores 2026

Portal de acesso rápido às ferramentas dos Auditores Fiscais da Sefaz/RN, publicado via GitHub Pages.

🔗 **Site:** https://bacalhaunabrisa.github.io/sefazrn/

## Sobre

Esta página não hospeda nenhuma ferramenta em si — ela apenas reúne, em um único lugar, os links para os simuladores e sistemas de apoio já publicados em outros repositórios do GitHub Pages:

| Ferramenta | Descrição | Link |
|---|---|---|
| Simulador de remuneração | Estimativa de subsídio, vantagens e descontos na carreira da Sefaz/RN | https://tinyurl.com/remuneracaosefazrn |
| Controle de processos no SEI | Acompanhamento de processos de provimento no Sistema Eletrônico de Informações | https://tinyurl.com/seisefazrn |
| Simulador de lotações | Cenários de lotação e movimentação entre unidades da Sefaz/RN | https://tinyurl.com/lotacaosefazrn |

## Estrutura do repositório

```
.
├── index.html        # página única do portal
├── afrelefante.png   # mascote/logo exibida no topo do site
└── README.md
```

## Como publicar (GitHub Pages)

1. Faça push destes arquivos para a branch `main` (ou a branch configurada como fonte do Pages) do repositório [`BacalhauNaBrisa/sefazrn`](https://github.com/BacalhauNaBrisa/sefazrn).
2. Em **Settings → Pages**, defina a fonte como a branch `main` e a pasta raiz (`/`).
3. Após alguns instantes, o site fica disponível em https://bacalhaunabrisa.github.io/sefazrn/.

## Atualizando os links

Os três cartões de ferramentas ficam no `<body>` de `index.html`, dentro da seção `.cards`. Para adicionar, remover ou atualizar um link, edite o bloco `<a class="card ...">` correspondente (título, descrição e `href`).

## Créditos

Mascote ilustrado especialmente para a Sefaz/RN (`afrelefante.png`).
