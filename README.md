# Fatto News — PWA

Portal de notícias em React + Vite, com API RSS para Vercel e suporte inicial a Progressive Web App (PWA).

## Recursos
- Interface responsiva com identidade visual bege e marrom, efeito glassmorphism e elementos 3D em CSS
- Pesquisa e filtros por Brasil/Mundo
- API `/api/news` que agrega feeds RSS de Agência Brasil e BBC News Brasil
- Atualização da interface a cada cinco minutos
- Manifesto PWA, ícones SVG e service worker
- Cache da interface e fallback de respostas da API para uso offline limitado
- Atalho de instalação quando o navegador oferece o evento de instalação

## Executar localmente
Requer Node.js 20 ou superior recomendado.

```bash
npm install
npm run dev
```

A API `/api/news` é uma função serverless da Vercel, portanto não funciona automaticamente com o servidor simples do Vite. Para testar a integração completa localmente, instale a CLI da Vercel e use:

```bash
npx vercel dev
```

## Gerar build
```bash
npm run build
```

A saída de produção será criada em `dist/`.

## Publicar
1. Envie os arquivos extraídos para um repositório GitHub.
2. Importe o repositório na Vercel.
3. Use o comando de build `npm run build` e a pasta de saída `dist`.
4. Depois do deploy em HTTPS, teste `/api/news`, a instalação PWA e o modo offline em um celular.

## Observações importantes
- O PWA precisa ser servido por HTTPS em produção (localhost é aceito para desenvolvimento).
- O suporte a instalação varia conforme navegador e dispositivo. Se o botão não aparecer, use o menu do navegador e procure “Adicionar à tela inicial” ou “Instalar app”.
- O modo offline permite abrir a estrutura do portal e consultar respostas previamente armazenadas quando disponíveis; não garante que notícias novas sejam carregadas sem internet.
- Notificações push não estão implementadas nesta versão.
- Feeds RSS, disponibilidade, conteúdo, termos de uso e política de redistribuição devem ser verificados antes de uso público.
- A aplicação não foi publicada por este pacote. Faça build e teste os feeds antes de considerar o projeto validado.
