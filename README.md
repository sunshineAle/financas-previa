# Dagda Capital — prévia de teste

**Prévia — não use com dados reais.** Página única gerada a partir da branch `proposta-unificacao` do repositório privado `financas` (proposta de unificação das páginas: rodapé Início · Patrimônio · Transações · Compromissos · Mais).

- Endereço: https://sunshineale.github.io/financas-previa/
- Abre com dados de exemplo, guardados só neste navegador. Tudo o que a prévia grava (localStorage, IndexedDB, cache) tem o prefixo `dagda-proposta:`, então ela não lê nem apaga os dados do app real (`sunshineale.github.io/financas/`), que fica no mesmo domínio.
- Sem service worker e sem instalação.

Como atualizar: no repositório `financas`, branch `proposta-unificacao`, `cd frontend && SF_PROPOSTA=1 npm run build:demo`, trocar U+FFFD e caracteres de controle por `\uXXXX` e copiar `dist-demo/index.html` para cá.

Última publicação: 29/10/2026 (versão unificada com a 0.9 mesclada).
