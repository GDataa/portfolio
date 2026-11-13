# Portfólio — João Atilano

Site estático (HTML, CSS e JS, sem build). Não precisa de `npm install`.

```
index.html        página completa
favicon.svg       ícone do separador
vercel.json       cache dos assets + URLs limpos
assets/img/       imagens dos projetos, foto, og.png (pré-visualização ao partilhar)
assets/video/     vídeos dos projetos (.mp4)
```

## Publicar na Vercel

### Opção A — pelo GitHub (recomendado, atualiza sozinho)
1. Cria um repositório novo no GitHub, por exemplo `GDataa/portfolio`.
2. Envia esta pasta para lá:
   ```bash
   cd portfolio
   git init
   git add .
   git commit -m "Portfólio"
   git branch -M main
   git remote add origin https://github.com/GDataa/portfolio.git
   git push -u origin main
   ```
3. Em vercel.com → **Add New… → Project** → importa `GDataa/portfolio`.
4. Framework Preset: **Other**. Build Command: vazio. Output Directory: vazio (raiz).
5. **Deploy**. O site fica em `portfolio-xxxx.vercel.app`.

A partir daí, cada `git push` publica uma nova versão automaticamente.

### Opção B — pela linha de comandos
```bash
npm i -g vercel
cd portfolio
vercel          # primeira vez: faz login e responde às perguntas (aceita os valores por defeito)
vercel --prod   # publica em produção
```

## Depois de publicar
- **Domínio:** em Project → Settings → Domains podes mudar para `atilano.vercel.app` (se estiver livre) ou ligar um domínio teu.
- **Pré-visualização em redes sociais:** troca em `index.html` a linha
  `<meta property="og:image" content="assets/img/og.png">`
  pelo URL completo, por exemplo `https://atilano.vercel.app/assets/img/og.png`.
  O LinkedIn e o WhatsApp só mostram a imagem com o URL completo.

## Trocar imagens e vídeos
Substitui os ficheiros em `assets/` mantendo o mesmo nome:
- `assets/video/<projeto>.mp4` — vídeo (MP4 H.264, idealmente até 10 MB)
- `assets/img/<projeto>-a.webp` — capa do cartão e poster do vídeo
- `assets/img/<projeto>-b.webp` — segunda imagem da galeria

Para acrescentar mais media a um projeto, edita a lista `media:` desse projeto no início do `<script>` em `index.html`.

## Testar no telemóvel antes de publicar
```bash
npx serve .      # abre http://<ip-do-computador>:3000 no telemóvel, na mesma rede Wi-Fi
```
