# Ponte São João Odontologia

Site estático da clínica. Os arquivos-fonte publicados ficam em `public/`; o build os copia para `dist/`, preservando as páginas e os assets.

## Páginas

- `/` — página inicial
- `/clinica-geral` — página de Clínica Geral
- `/urgencia-odontologica` — página de Urgência Odontológica

## Publicar na Vercel a partir do GitHub

Importe o repositório `prospeccaoleadodonto-cloud/Lp-nova` na Vercel e mantenha o **Root Directory** como `.` (raiz do repositório). O arquivo `vercel.json` define `npm run build` como build, `dist` como pasta publicada e reescreve `/` para `/index.html`. Não configure `public` como Root Directory nem troque a Output Directory: isso pode deixar de fora o build e as rotas novas.

Depois que o projeto estiver conectado ao repositório, publicar a branch `main` cria um novo deployment. Se a integração Git do projeto estiver conectada a outro repositório ou branch, ajuste a conexão no painel Vercel antes de publicar.

## Copiar para outro host estático

Na raiz do repositório, execute:

```bash
npm run build
```

Envie **o conteúdo inteiro de `dist/`** para a pasta raiz do site no host. Não envie somente o `index.html`: o build também inclui `clinica-geral/index.html`, `urgencia-odontologica/index.html`, `assets/`, CSS, JavaScript, `robots.txt` e `sitemap.xml`. Para uma publicação simples por upload/drag-and-drop, use a pasta `dist/` gerada.

## Antes de usar um domínio diferente

As URLs canônicas, metadados Open Graph, `sitemap.xml` e `robots.txt` apontam atualmente para `https://www.pontesaojoaoimplantes.com.br`. Se o site for publicado em outro domínio, atualize essas referências nos arquivos de `public/` antes de anunciar, para que buscadores recebam o endereço correto.

## Teste local

```bash
npm run build
npm start
```

Abra `http://localhost:3000/`, `http://localhost:3000/clinica-geral` e `http://localhost:3000/urgencia-odontologica`.
