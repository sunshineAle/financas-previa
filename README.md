# Dagda Capital — prévia das anotações 79, 80 e 81

**Use somente dados fictícios.** Esta prévia é gerada a partir da `main` atual do repositório privado `sunshineAle/financas`, versão 1.2.2, base `e583dcffc6360b930bbbe6d3b4844233300016cd`. Inclui as atualizações que não haviam passado pela prévia de 29/10, mais as anotações 79, 80 e 81 do Cérebro Central.

- **79:** Restaurar meu Dagda sem criar perfil antes; nome recuperado e acesso com a senha do backup. Com código de recuperação, pede apenas uma nova senha. Backups antigos só recuperam o nome que efetivamente contêm.
- **80:** backups Google na área oculta do app, com lista por data e tamanho para escolher. Login real no Google depende da homologação manual. Backups antigos da pasta visível continuam lá, sem migração automática.
- **81:** regra de transferência com nome do titular; sugestões na importação e em A revisar, com confirmação. Valores diferentes não formam par; mais de uma ponta exige escolha.

## Como testar

1. Abra a prévia e use **Carregar demonstração**. A senha de teste é `demonstracao`.
2. Para testar a anotação 79, baixe um backup fictício em Dados e backup, use **Reiniciar prévia** e escolha **Restaurar meu Dagda** com esse arquivo.
3. Para a 80, use uma conta de testes do Google. A prévia só lista os arquivos `previa-*.sfin` e não executa limpeza automática na nuvem.
4. Para a 81, crie em **Regras** uma regra de transferência com nome completo de um titular fictício e importe um extrato fictício com PIX; confira a importação e A revisar.

O armazenamento usa `dagda-previa-79-81:` (localStorage, sessionStorage e IndexedDB), separado do app oficial e da prévia antiga. **Reiniciar prévia** limpa apenas esta versão de teste. Sem service worker e sem instalação.

## Regerar

No checkout privado de `financas`, na branch de trabalho com as três anotações:

```sh
cd frontend
npm ci
npx vite build -c vite.previa.config.js
```

Copie `dist-previa/` para este repositório, preservando `.git`, README, robots.txt e `.nojekyll`; não copie `sw.js`, manifest ou ícones de instalação. Use os checkouts existentes, sem criar worktrees salvo pedido explícito.

Os comandos de teste e detalhes estão em `financas/PREVIA-79-81.md`. A geração local e a publicação no GitHub Pages são etapas separadas.
