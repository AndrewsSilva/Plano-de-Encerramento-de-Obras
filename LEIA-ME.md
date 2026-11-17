# Plano de Encerramento de Obras · Equatorial Piauí

## Arquivos
| Arquivo | Para que serve |
|---|---|
| `index.html` | Painel. Lê os dados de `dados.json` (só a aba visível da planilha). Funciona no PC e no celular (inclusive na horizontal). |
| `dados.json` | Dados extraídos da planilha base. É o único arquivo que o botão **Atualizar planilha** altera. |
| `assets/` | Banner da marca. |

## Publicar no GitHub Pages (uma vez)
1. Crie um repositório e envie todo o conteúdo desta pasta `painel/`.
2. Em **Settings → Pages**, escolha *Deploy from a branch* → `main` → `/ (root)`.
3. O painel fica em `https://<usuario>.github.io/<repositorio>/`.

## Criar o token para o botão "Atualizar planilha" (em cada computador)
1. GitHub → **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
2. *Repository access*: **Only select repositories** → escolha só o repositório do painel.
3. *Permissions → Repository permissions → Contents*: **Read and write**. Nada mais.
4. Defina uma validade (ex.: 90 dias).

## Atualizar os dados
1. Abra o painel publicado → **Atualizar planilha**.
2. Anexe a nova revisão do `.xlsx`. O painel valida as colunas e mostra um resumo.
3. Em **⚙ Publicação no GitHub**, confira usuário/repositório (preenchidos sozinhos quando o painel roda no github.io) e cole o token.
4. Clique em **Subir e publicar no GitHub**. Isso cria um commit no `dados.json`, e o site se atualiza para todos em cerca de 1 minuto.

## Segurança
- **Nunca** coloque o token dentro de arquivos do repositório. Ele fica só no navegador de quem atualiza.
- Repositório **público** = dados (nomes de responsáveis, valores de obras) visíveis na internet. Prefira repositório **privado** com Pages restrito (GitHub Enterprise/Team) e valide com a área de Segurança da Informação.
- Se um token vazar, revogue-o imediatamente em *Developer settings*.
