# Instagrams EBAT

Página com os @ dos alunos da EBAT. A lista vem de dois lugares, juntados pela própria página:

- [`perfis.txt`](perfis.txt): a lista inicial, um @ por linha.
- **Google Forms**: quem entra na página digita o @ e envia, sem precisar de login. As respostas vão para uma planilha que a página lê.

## Configurar o Google Forms (uma vez só)

1. Crie um formulário em [forms.google.com](https://forms.google.com) com **uma pergunta de resposta curta**: "Seu @ do Instagram".
   Em **Configurações**, deixe desligado "Coletar e-mails" e "Limitar a 1 resposta" (senão pede login).
2. Na aba **Respostas**, clique em **Vincular ao Planilhas** e crie a planilha.
3. Na planilha: **Compartilhar** → Acesso geral: **Qualquer pessoa com o link** (Leitor). Copie o ID da planilha (o trecho entre `/d/` e `/edit` no link).
4. No formulário, menu **⋮ → Gerar link pré-preenchido**, digite `teste` na pergunta e clique em **Gerar link** → Copiar link.
   O link tem algo como `.../forms/d/e/XXXX/viewform?usp=pp_url&entry.123456789=teste`.
5. No `index.html`, preencha o `CONFIG` no começo do `<script>`:
   - `formUrl`: o começo desse link, trocando `viewform` por `formResponse` → `https://docs.google.com/forms/d/e/XXXX/formResponse`
   - `formCampo`: o `entry.123456789`
   - `csvUrl`: `https://docs.google.com/spreadsheets/d/ID_DA_PLANILHA/gviz/tq?tqx=out:csv`

Os @ novos aparecem para todo mundo assim que a resposta cai na planilha.
Para remover um @ indevido, apague a linha na planilha.

## Publicar no GitHub Pages

1. Suba os arquivos (`index.html`, `perfis.txt`, `logo.png`, `instagram_1384063.svg`) para um repositório público.
2. **Settings → Pages** → Source: *Deploy from a branch* → `main` / `(root)`.
