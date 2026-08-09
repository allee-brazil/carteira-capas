# carteira-capas — capas públicas das peças (fluxo Meta Ads)

Repositório **PÚBLICO** da **allee** que **hospeda as capas** (imagens de
cabeçalho) de cada peça do **fluxo Meta Ads** — o passo-a-passo de aquisição
(estruturar conta, pixel/CAPI, campanhas, criativos, públicos…). É público **de
propósito**: as imagens ficam **hotlinkáveis** por URL, para serem consumidas por
outros ativos da casa sem re-upload. Este repo só **guarda e serve** as artes;
**quem as cria é o Claude Design / `assets-design`** (Allee Brand System).

---

![1 · Visão](https://img.shields.io/badge/1-VIS%C3%83O-2b6cb0?style=for-the-badge)

## 1 · Visão — o que é & por quê

> **Enquadramento (allee):** cada peça do fluxo Meta Ads tem uma **capa**. Este
> repo é a **prateleira pública** dessas capas — entra uma arte (PNG), sai uma
> **URL estável e hotlinkável** que qualquer outra peça pode referenciar.

As capas ilustram as etapas do fluxo de aquisição via **Meta Ads** (do portfólio
de negócios à publicação do anúncio e além). Elas precisam aparecer em vários
lugares — material de estudo, referências do `assets-design`, telas/automação —
**sem** cada consumidor ter que hospedar sua própria cópia. Por isso o repo é
**público**: o GitHub serve o PNG por URL (`raw.githubusercontent.com`), e o
consumidor só aponta o `src` para lá.

> **Por que público (e o que isso exige):** hotlink só funciona com repo público.
> Em troca, **nada sensível pode entrar aqui** — só arte de capa, sem credenciais,
> sem dados de cliente, sem texto interno. Ver **Segredos**.

Marca / identidade visual: **não se aplica a este repo** — a identidade canônica
da allee vive no **[`assets-design`](https://github.com/allee-brazil/assets-design)**
(Allee Brand System). Por isso **não há `IDENTIDADE.md`** aqui. As capas seguem a
paleta e as regras de lá (logo da plataforma sobre creme `#F4F1EA` etc.); este
repo apenas **as armazena**.

---

![2 · Sistema](https://img.shields.io/badge/2-SISTEMA-2f855a?style=for-the-badge)

## 2 · Sistema — como funciona

Não há software neste repositório: é um **acervo de PNGs** servido pelo GitHub.
O "sistema" é a **convenção de nomes** e a **organização das pastas**. Mapa da
topologia e do esquema de hotlink: **[ARQUITETURA.md](ARQUITETURA.md)**.

### Convenção de nomes

- Capas do fluxo principal: **`NN-slug.png`** — número de ordem de 2 dígitos +
  slug da etapa (ex.: `01-portfolio.png`, `14-pixel.png`, `24-anuncio-copy.png`).
  Numeradas **01 a 36** (a ordem = a sequência do fluxo Meta Ads).
- Capas de apoio ficam em subpastas temáticas com slug descritivo, sem número
  (ex.: `carteiracapasevidencias/curva-aprendizado.png`).
- Sempre **PNG**, `slug` em minúsculas com hífen (kebab-case), sem espaços no
  nome do arquivo.

### Organização (estado atual — dump único)

O conteúdo entrou por **um upload único** (commit `Add files via upload`), então
há **redundância** que ainda não foi consolidada:

| Caminho | O que é | Observação |
|---|---|---|
| `carteiracapas/` | 36 capas `NN-slug` **otimizadas** (~40–50 KB) | Sem espaço no nome da pasta → **melhor candidata a fonte canônica de hotlink** |
| `carteiracapas 2/` | as mesmas 36 capas em **alta resolução** (~150–870 KB) + 2 subpastas | Nome da pasta **tem espaço** → vira `%20` na URL (frágil p/ hotlink) |
| `carteiracapas 2/carteiracapasevidencias/` | 5 capas de "evidências" (`curva-aprendizado`, `fragmentacao-sinal`, `objetivo-sinal`, `orcamento-50-eventos`, `relevancia-custo`) | apoio |
| `carteiracapas 2/carteiracapasnovos/` | 6 capas "novas" (`catalogo-produtos`, `conversoes-offline-crm`, `loja-commerce`, `publicos-personalizados`, `usuario-sistema-token`, `vinculos-ativos`) | apoio |
| `carteiracapas.zip` | pacote (1,5 MB) com o **conjunto otimizado** (as 36 de `carteiracapas/`) | bundle de conveniência |

> **Pendências conhecidas do acervo** (não corrigidas por este PR — só docs):
> - 6 capas do conjunto em alta (`19-conversao-cambial`, `27-bridge-page`,
>   `29-perguntas-certas`, `31-pesquisa-mercado`, `32-temperatura-trafego`,
>   `36-sistema-propostas`) estão como **placeholder de ~4 KB** — arte pendente.
> - Duplicação `carteiracapas/` × `carteiracapas 2/` e o **espaço** em
>   `carteiracapas 2/` precisam de decisão do dono. Ver **Atividades**.

### Relação com a família

- **[`assets-design`](https://github.com/allee-brazil/assets-design)** — o
  **Allee Brand System** (design system + identidade canônica). Ele **cita este
  repo** como a fonte pública das capas por peça do fluxo Meta Ads ("permite
  hotlink"). Fluxo: **arte nasce no Claude Design → `assets-design` (referência)
  → `carteira-capas` (hospeda/serve)**.
- **[`carteira-motor`](https://github.com/allee-brazil/carteira-motor)** — o
  **motor de automação da carteira** (entrega pós-venda; pilares Ads, WhatsApp,
  cobranças, contratos, acessos). Mesma família "carteira": onde o `carteira-motor`
  ou material de aquisição precisar ilustrar uma etapa do fluxo Meta Ads, a capa
  correspondente sai **deste** acervo por URL. _(TODO: preencher — confirmar se e
  onde o `carteira-motor` referencia as capas por hotlink hoje.)_

### Como se referencia (hotlink)

URL crua do GitHub:

```
https://raw.githubusercontent.com/allee-brazil/carteira-capas/<ref>/<caminho>
```

Exemplos (verificados — respondem `200 image/png`):

```
https://raw.githubusercontent.com/allee-brazil/carteira-capas/main/carteiracapas/01-portfolio.png
https://raw.githubusercontent.com/allee-brazil/carteira-capas/main/carteiracapas%202/08-acessos-papeis.png
```

> `<ref>` pode ser `main` (sempre a versão mais recente) ou um **commit SHA / tag**
> (link imutável). Para hotlink estável em produção, **prefira fixar um SHA** — em
> `main` a arte pode mudar sob a mesma URL.

---

![3 · Operação](https://img.shields.io/badge/3-OPERA%C3%87%C3%83O-b7791f?style=for-the-badge)

## 3 · Operação — como tocar & estado

### Adicionar / atualizar uma capa

1. **Gerar a arte fora daqui** — no **Claude Design / `assets-design`** (paleta e
   regras da casa). Este repo **não gera arte**; só recebe o PNG pronto.
2. **Nomear** no padrão: `NN-slug.png` para o fluxo principal (número = ordem) ou
   `slug.png` dentro da subpasta temática. Minúsculas, hífen, sem espaço, **PNG**.
3. **Subir** o arquivo (upload pela web do GitHub ou commit + push) na pasta certa.
4. **Pegar o hotlink** no formato acima e, para produção, **fixar o SHA**.
5. Se a peça já era referenciada e a arte mudou, **avisar quem consome** (o
   `assets-design` e demais consumidores) — a URL em `main` passa a servir a arte
   nova.

### Fronteiras (segurança)

- **Criação de arte = Claude Design / `assets-design` (humano aprova).** Este repo
  só **hospeda**. **Nunca gerar capa por código** aqui.
- **Publicar o repo / dar/retirar acesso** = dono. Manter **público** é decisão de
  operação (o hotlink depende disso).
- **Consolidar o acervo** (escolher conjunto canônico, remover duplicidade,
  renomear pasta com espaço) = decisão do dono antes de qualquer consumidor fixar
  URLs em massa.

### Segredos

**Repositório PÚBLICO — nada sensível, nunca.** Sem senhas, tokens, CNPJ, dados de
cliente ou texto interno. Só arte de capa. Qualquer coisa fora disso **não entra**.

### Documentos deste repo

- **README.md** (este) — visão, sistema (nomes/pastas/hotlink) e operação.
- **[ARQUITETURA.md](ARQUITETURA.md)** — mapa leve: topologia das pastas, esquema
  de hotlink e lugar na família (sem software = sem arquitetura de execução).
- **[CLAUDE.md](CLAUDE.md)** — memória/regra para o Claude operar aqui (só hospeda;
  arte vem do `assets-design`; nunca gerar arte por código).
- **IDENTIDADE.md** — **não se aplica**; a identidade canônica é o
  **[`assets-design`](https://github.com/allee-brazil/assets-design)** (Allee
  Brand System).

### Atividades

> Última seção de propósito: as tarefas se **acumulam** com o tempo; ficam no fim
> para não atrapalhar a leitura do resto.

**Concluído**
- [x] Acervo inicial no ar (36 capas `NN-slug` + evidências + novas + zip), repo
  público, hotlink funcionando (`raw.githubusercontent.com` → `200 image/png`).

**Para Fazer**
- [ ] **Decidir o conjunto canônico** de hotlink (otimizado `carteiracapas/` vs.
  alta `carteiracapas 2/`) e documentar a escolha aqui.
- [ ] **Renomear a pasta com espaço** (`carteiracapas 2/`) para um slug sem espaço
  (ex.: `capas-alta/`) — o `%20` na URL é frágil.
- [ ] **Trocar os 6 placeholders de ~4 KB** por arte final (`19-conversao-cambial`,
  `27-bridge-page`, `29-perguntas-certas`, `31-pesquisa-mercado`,
  `32-temperatura-trafego`, `36-sistema-propostas`).
- [ ] _(TODO: preencher — confirmar quem consome as capas por hotlink hoje
  (`assets-design`? `carteira-motor`? material de aquisição?) e fixar SHAs.)_
- [ ] _(TODO: preencher — avaliar se o `carteiracapas.zip` deve continuar versionado
  ou virar release/anexo.)_
