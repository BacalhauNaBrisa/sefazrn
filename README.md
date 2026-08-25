# Sefaz/RN · Auditores 2026

Portal de acesso rápido às ferramentas dos Auditores Fiscais da Sefaz/RN, publicado via GitHub Pages.

🔗 **Site:** https://sefazrn.com

## Sobre

Esta página não hospeda nenhuma ferramenta em si — ela apenas reúne, num único lugar, os links para os simuladores e sistemas de apoio já publicados noutros repositórios:

| Ferramenta | Descrição | Link |
|---|---|---|
| Simulador de remuneração | Estimativa de subsídio, vantagens e descontos na carreira da Sefaz/RN | https://tinyurl.com/remuneracaosefazrn |
| Controlo de processos no SEI | Acompanhamento de processos de provimento no Sistema Eletrónico de Informações | https://tinyurl.com/seisefazrn |
| Simulador de lotações | Cenários de lotação e movimentação entre unidades da Sefaz/RN | https://tinyurl.com/lotacaosefazrn |
| Escala de plantões da SUMAT | Consulta da escala de plantões de 12h dos novos auditores lotados na SUMAT | https://tinyurl.com/sumatsefazrn |

A página verifica automaticamente, a cada 15 minutos, se cada uma destas ferramentas está no ar — ver [Monitorização de disponibilidade](#monitorização-de-disponibilidade) abaixo.

## Estrutura do repositório

```
.
├── index.html                          # página única do portal
├── afrelefante.png                     # mascote/logo exibida no topo do site
├── status.json                         # gerado automaticamente pelo workflow abaixo
├── CNAME                               # domínio customizado (sefazrn.com)
├── README.md
└── .github/
    └── workflows/
        └── status-check.yml            # verifica as 4 ferramentas a cada 15 min
```

## Como publicar (GitHub Pages)

1. Faça push destes arquivos para a branch `main` (ou a branch configurada como fonte do Pages) do repositório [`BacalhauNaBrisa/sefazrn`](https://github.com/BacalhauNaBrisa/sefazrn).
2. Em **Settings → Pages**, defina a fonte como a branch `main` e a pasta raiz (`/`).
3. O domínio customizado (`sefazrn.com`) já está configurado via o arquivo `CNAME` e os registos DNS na Spaceship — ver `Settings → Pages` para o estado do certificado HTTPS.

## Monitorização de disponibilidade

O workflow `.github/workflows/status-check.yml` corre a cada 15 minutos (e também pode ser disparado manualmente em **Actions → Verificar disponibilidade das ferramentas → Run workflow**). Ele faz `curl` em cada um dos 4 links, segue redirecionamentos e grava o resultado em `status.json` na raiz do repositório.

O `index.html` lê esse `status.json` (mesma origem, sem CORS) e mostra, em cada cartão, um indicador verde ("no ar") ou vermelho ("fora do ar"), além do contador "X de 4 no ar" com a hora da última verificação.

> **Nota:** a ferramenta do SEI corre a partir de um portátil pessoal via Tailscale Funnel, por isso a sua disponibilidade depende de esse portátil estar ligado e com ligação à rede.

## Atualizando os links

Os cartões de ferramentas ficam no `<body>` de `index.html`, dentro da seção `.cards`. Para adicionar, remover ou atualizar um link:

1. Edite o bloco `<a class="card ...">` correspondente em `index.html` (título, descrição e `href`), mantendo o atributo `data-status-key` único.
2. Adicione/remova a mesma chave (`key`) na lista `urls` dentro de `.github/workflows/status-check.yml`.
3. Opcionalmente, atualize a entrada correspondente em `status.json` (o workflow reescreve este ficheiro automaticamente na próxima execução).

## Créditos

Mascote ilustrado especialmente para a Sefaz/RN (`afrelefante.png`).
