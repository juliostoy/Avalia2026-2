# Projeto #7: Jogo da Memória Temático

- **Modalidade:** Projeto Oficial Sorteado (Valendo 100 pontos)
- **Estudante:** Julio Cesar dos Santos Ventura
- **Turma:** 2B
- **Chave Única:** `P26-2B-23DA-3A7A-20A1-620C`
- **URL_CLOUDFLARE:** `https://p26-2b-23da-3a7a-20a1-620c.pages.dev` *(Atualize com a URL pública real do seu deploy na Cloudflare antes de abrir o Pull Request)*

---

## Especificação do Projeto

Projete um jogo de memória baseado em pares de cartas que exigem correspondência visual ou conceitual (ex: código e sua saída). A interface deve empregar transformações CSS 3D acionadas via JavaScript vanilla para o efeito de virar as cartas, mantendo o cabeçalho com os dados do usuário obtidos via login do Discord.

A disposição das cartas é embaralhada no servidor Cloudflare no início da sessão, enviando apenas identificadores opacos para o frontend. Quando o jogador seleciona duas cartas, uma requisição consulta o backend para verificar se os identificadores formam um par válido, incrementando o contador de movimentos no banco D1 e registrando a eficiência do jogador ao descobrir todos os pares.

---

## Como Publicar esta Subpasta no Cloudflare Pages + D1

1. No painel da Cloudflare (**Workers & Pages** → **Create** → **Pages** → **Connect to Git**), selecione o seu fork do repositório `Avalia2026-2`.
2. Configure os parâmetros de build apontando para esta subpasta:
   - **Root directory (Diretório raiz):** `P26-2B-23DA-3A7A-20A1-620C`
   - **Build command:** *(deixe em branco — HTML/CSS/JS puro)*
   - **Build output directory:** `public`
3. Crie o banco de dados D1 e aplique a migração inicial (no terminal do laboratório usando Scoop):
   ```powershell
   cd P26-2B-23DA-3A7A-20A1-620C
   npx.cmd wrangler d1 create db-p26-2b-23da-3a7a-20a1-620c
   # Copie o database_id gerado para o arquivo wrangler.jsonc e execute:
   npx.cmd wrangler d1 migrations apply DB --remote
   ```
4. Atualize o campo **URL_CLOUDFLARE** no topo deste `README.md` com o endereço público gerado pela Cloudflare.
5. Na raiz do repositório, execute `node validar-local.mjs P26-2B-23DA-3A7A-20A1-620C` para validar todos os critérios antes de fazer o commit e abrir o Pull Request.
