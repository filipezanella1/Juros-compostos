# Simulador de Juros Compostos — pacote PWA

Este pacote contém tudo que você precisa para publicar o simulador como um
app instalável de verdade (PWA), gratuitamente, pelo GitHub Pages.

## Arquivos

- `index.html` — o app (interface + cálculos)
- `manifest.json` — diz ao navegador que isso é um app instalável
- `service-worker.js` — permite abrir offline, depois do primeiro acesso
- `icons/` — ícones do app (192px, 512px, versão "maskable" e ícone da Apple)

## Passo a passo (uns 10 minutos, sem precisar programar)

### 1. Crie uma conta no GitHub (se ainda não tiver)
Vá em https://github.com e crie uma conta gratuita.

### 2. Crie um novo repositório
- Clique em **New repository** (botão verde, ou "+" no canto superior direito).
- Nome sugerido: `simulador-juros-compostos`.
- Marque como **Public** (o GitHub Pages gratuito exige repositório público).
- Não marque "Add a README" — vamos subir os arquivos já prontos.
- Clique em **Create repository**.

### 3. Envie os arquivos
Na página do repositório recém-criado:
- Clique em **uploading an existing file** (ou "Add file" → "Upload files").
- Arraste **todos os arquivos e a pasta `icons/`** deste pacote para a área de upload
  (mantendo a estrutura: `index.html`, `manifest.json`, `service-worker.js` na raiz,
  e a pasta `icons` com os 4 arquivos dentro dela).
- Role para baixo e clique em **Commit changes**.

### 4. Ative o GitHub Pages
- No repositório, vá em **Settings** (aba no topo).
- No menu lateral, clique em **Pages**.
- Em "Build and deployment" → "Source", selecione **Deploy from a branch**.
- Em "Branch", selecione **main** (ou "master") e a pasta **/ (root)**.
- Clique em **Save**.
- Aguarde 1–2 minutos. Atualize a página — vai aparecer um link tipo:
  `https://seu-usuario.github.io/simulador-juros-compostos/`

### 5. Abra esse link no celular
- **Android (Chrome):** vai aparecer um banner ou o menu (⋮) mostrará
  **"Instalar app"** — dessa vez de verdade, reconhecido pelo sistema.
- **iPhone (Safari):** Compartilhar → "Adicionar à Tela de Início" (como antes,
  mas agora funciona offline depois do primeiro carregamento).

## Atualizando o app no futuro

Sempre que editar `index.html` (por exemplo, para mudar o CDI de referência),
suba o arquivo atualizado pelo GitHub (**Add file → Upload files**, sobrescrevendo)
e também aumente o número em `service-worker.js`:

```js
const CACHE_NAME = 'simulador-juros-v2';  // era v1
```

Isso força quem já instalou o app a baixar a versão nova na próxima abertura.

## Sem custo, sem servidor

O GitHub Pages é gratuito para repositórios públicos. Não há backend nem banco
de dados — os valores que você digita ficam salvos só no seu celular
(localStorage do navegador), nada é enviado para lugar nenhum.
