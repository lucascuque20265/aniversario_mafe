# Convite Digital — Beatriz 18 Anos

Convite interativo em HTML puro, pronto para deploy estático.

---

## Estrutura

```
convite-beatriz/
└── index.html   ← arquivo único, tudo embutido (CSS + JS)
```

---

## 1. Subir no GitHub

```bash
git init
git add .
git commit -m "first commit"
git remote add origin https://github.com/seu-usuario/convite-beatriz.git
git push -u origin main
```

---

## 2. Deploy na Vercel

1. Acesse [vercel.com](https://vercel.com)
2. Clique em **Add New Project**
3. Importe o repositório do GitHub
4. Clique em **Deploy**

A URL gerada (`convite-beatriz.vercel.app`) é o link final para enviar aos convidados.

---

## 3. Congelar o deploy (não atualizar ao fazer push)

Por padrão, qualquer push para o GitHub re-deploya o site automaticamente.
Para congelar a versão publicada:

**Vercel → Settings → Git → Ignored Build Step**

Cole o valor abaixo e salve:

```
exit 1
```

A partir daí, nenhum push vai alterar o site no ar.

---

## 4. Atualizar o site manualmente

**Opção A — Redeploy pelo painel**
> Vercel → Deployments → clique no deploy mais recente → **Redeploy**

**Opção B — Liberar push temporariamente**
1. Remova o `exit 1` do campo Ignored Build Step
2. Faça o push normalmente
3. Recoloque o `exit 1` depois

---

## 5. Personalizar o convite

Abra o `index.html` e localize as seções abaixo para editar:

| O que alterar | Onde encontrar no código |
|---|---|
| Nome da aniversariante | Buscar por `Beatriz` |
| Data do evento | Buscar por `2025-12-14` |
| Horário | Buscar por `13h00` |
| Local e endereço | Buscar por `Espaço Villa Nobre` |
| Número do WhatsApp | Buscar por `5511999999999` |
| Nome da família | Buscar por `Família Silva` |
| Música de fundo | Tag `<audio>` — substituir o `src` |
| Vídeo de abertura | Função `setVideoUrl('sua-url.mp4')` |

---

## 6. Adicionar vídeo de abertura

**Via URL (recomendado para produção):**
Localize no `index.html` a função `setVideoUrl` e chame-a com o link do vídeo:

```html
<script>
  setVideoUrl('https://seu-servidor.com/video.mp4');
</script>
```

**Via arquivo local (só funciona em modo teste):**
Use o botão que aparece na tela de vídeo ao abrir o convite no navegador.

---

## Referência rápida

| Situação | Ação |
|---|---|
| Congelar o site publicado | Ignored Build Step → `exit 1` |
| Liberar atualização via push | Remover o `exit 1`, fazer push, recolocar |
| Forçar atualização sem push | Deployments → Redeploy |
