# CORAL IA — pacote PWA

Este pacote é o seu `coral-ia.html` (agora `index.html`) com as peças que o transformam em app instalável:

| Arquivo | Função |
|---|---|
| `index.html` | O site, com manifesto, ícones, botão "Instalar app" e registro do service worker |
| `manifest.webmanifest` | Nome, cores e ícones do app |
| `sw.js` | Service worker: faz o app abrir offline |
| `icons/` | Ícones 192, 512, maskable, iOS e favicon |
| `vercel.json` | Ajustes de cache para o Vercel |

> O app só pode ser instalado a partir de um endereço **https**. Abrir o `index.html` com dois cliques funciona como site, mas sem instalação.

## Publicar no Vercel

**Opção A — pelo GitHub (mais simples)**
1. Crie uma conta em vercel.com (pode entrar com Google ou GitHub).
2. Crie um repositório no GitHub e envie **o conteúdo desta pasta** (o `index.html` precisa ficar na raiz).
3. No Vercel: **Add New → Project**, escolha o repositório e clique em **Deploy**. Não precisa mudar nenhuma configuração (Framework Preset: *Other*).

**Opção B — pela linha de comando**
```bash
npm i -g vercel
cd coral-ia-pwa
vercel        # siga as perguntas; depois: vercel --prod
```

Você receberá um endereço como `coral-ia.vercel.app`.

## Instalar o app

- **Android (Chrome):** abra o endereço → botão **Instalar app** no site, ou menu ⋮ → *Instalar app*.
- **iPhone (Safari):** abra o endereço → **Compartilhar** → **Adicionar à Tela de Início**.
- **Computador (Chrome/Edge):** ícone de instalação na barra de endereço, ou o botão **Instalar app** do site.

## Gerar .apk (opcional)

Com o site publicado, entre em **pwabuilder.com**, cole o endereço do Vercel e use *Package for stores → Android*.

## Atualizando o app

Depois de mudar qualquer arquivo, aumente o número em `sw.js` (`coral-ia-v1` → `coral-ia-v2`) para que os aparelhos baixem a versão nova.
