# carteira-capas — memória do projeto (Claude)

Repositório **PÚBLICO** da **allee** que **hospeda as capas** (PNG) de cada peça
do **fluxo Meta Ads**, servidas por **hotlink** (`raw.githubusercontent.com`).
Este repo **só armazena e serve** arte; **não é onde a arte nasce**. Leia
`README.md` e `ARQUITETURA.md` antes de agir.

## O que é (e o que não é)

- **É:** prateleira pública de capas, consumidas por URL sem re-upload.
- **Não é:** ferramenta, app ou gerador de arte. **Sem software** — não há build,
  runtime, testes nem deploy. Nada a rodar.

## Regras duráveis

- **Arte vem do Claude Design / `assets-design`** (Allee Brand System) — humano
  aprova. **Nunca gerar capa por código** aqui (sem scripts que criem/derivem
  imagem). Este repo apenas **recebe o PNG pronto**.
- **Identidade = `assets-design`.** A identidade canônica da allee **não** vive
  aqui; **não criar `IDENTIDADE.md`** — referenciar o `assets-design`.
- **Repo PÚBLICO ⇒ zero segredo.** Sem senhas, tokens, CNPJ, dados de cliente ou
  texto interno em arquivo, nome ou commit. Só arte de capa.
- **Convenção de nomes:** fluxo principal `NN-slug.png` (número = ordem 01–36);
  apoio em subpasta com `slug.png`. **PNG**, kebab-case, **sem espaço** no nome.
- **Hotlink estável = SHA fixo.** Em `main` a URL serve a arte que estiver lá;
  para produção, apontar consumidores a um commit SHA / tag.
- **Não "consertar" o acervo por conta própria:** a duplicação
  (`carteiracapas/` × `carteiracapas 2/`), o espaço na pasta e os placeholders de
  ~4 KB são **decisão do dono** (README §Atividades). Documentar, não deletar.

## Fronteiras (ação humana, não do Claude)

Criar a arte (Claude Design), aprovar, publicar o repo, dar/retirar acesso,
decidir o conjunto canônico e renomear pastas = **dono / operador**.

## Estado & contexto

- **Estado vivo:** `README.md` (§3 · Operação → Atividades).
- **Fonte da identidade/arte:** `assets-design` (Allee Brand System).
- **Família:** `assets-design` (referencia estas capas) · `carteira-motor` (mesma
  família "carteira"; possível consumidor por hotlink — a confirmar).
