# Jornal de Teatro

Site editorial estático para `jornaldeteatro.rio.br`, com crítica, agenda e bastidores das artes cênicas, integrado ao Correio Content Hub.

## Cloudflare Pages

- Framework preset: **None**
- Build command: `npm run build`
- Build output directory: `dist`
- Branch de produção: `main`
- Deploy manual: execute `npx wrangler pages deploy dist --project-name jornal-de-teatro --branch main` na raiz do repositório.

A rota `/api/articles` é uma Pages Function que consulta o Hub no servidor, evitando dependência de CORS no navegador. A resposta tem cache de edge de 60 segundos, usa o último resultado por até 24 horas quando o Hub falha e o navegador mantém uma cópia local por até 7 dias. Se não houver conteúdo do Hub, as chamadas da página mantêm a edição editorial estática.

Imagem de abertura: “Theater Show”, de Kurt Kaiser, via Wikimedia Commons, em domínio público CC0.
