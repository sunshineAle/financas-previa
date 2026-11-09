# Dagda Capital — prévia das anotações 79, 80 e 81

**Use somente dados fictícios.** Esta prévia é gerada a partir da `main` atual do repositório privado `sunshineAle/financas`, versão 1.2.2, base `e583dcffc6360b930bbbe6d3b4844233300016cd`. Inclui as atualizações que não haviam passado pela prévia de 29/10, mais as anotações 79, 80 e 81 do Cérebro Central.

- **79:** Restaurar meu Dagda sem criar perfil antes; nome recuperado e acesso com a senha do backup. Com código de recuperação, pede apenas uma nova senha. Backups antigos só recuperam o nome que efetivamente contêm.
- **80:** backups Google na área oculta do app, com lista por data e tamanho para escolher. Entrar com Google procura na área oculta e na pasta antiga Dagda Capital, sem mover ou apagar arquivos. O login real depende da conta e da autorização Google.
- **81:** regra de transferência com nome do titular; sugestões na importação e em A revisar, com confirmação. Valores diferentes não formam par; mais de uma ponta exige escolha.

## Como testar

1. Abra a prévia e use **Testar com dados fictícios**. A demonstração abre automaticamente, sem cadastro nem senha, com contas, cartões e um par PIX para revisar. Ela usa um banco separado dos dados restaurados.
2. Para testar a anotação 79, baixe um backup fictício em Dados e backup, use **Voltar ao acesso / restaurar backup** e escolha **Restaurar meu Dagda** com esse arquivo.
3. **Entrar com Google** fica visível na entrada e também no desbloqueio de quem já criou acesso. Para restaurar, busca os backups da área oculta e os antigos em Meu Drive/Dagda Capital, mostrando data e tamanho. Novos backups da prévia usam `previa-*.sfin`; a prévia não executa limpeza automática na nuvem.
4. Para a 81, crie em **Regras** uma regra de transferência com nome completo de um titular fictício e importe um extrato fictício com PIX; confira a importação e A revisar.

O armazenamento da restauração usa `dagda-previa-79-81:`; a demonstração usa `dagda-previa-demo-79-81:` (localStorage, sessionStorage e IndexedDB), separado do app oficial e da prévia antiga. **Reiniciar prévia** limpa apenas esta versão de teste. Sem service worker e sem instalação.

## Regerar

No checkout privado de `financas`, na branch de trabalho com as três anotações:

```sh
cd frontend
npm ci
npx vite build -c vite.previa.config.js
```

Copie `dist-previa/` para este repositório, preservando `.git`, README, robots.txt e `.nojekyll`; não copie `sw.js`, manifest ou ícones de instalação. Use os checkouts existentes, sem criar worktrees salvo pedido explícito.

Os comandos de teste e detalhes estão em `financas/PREVIA-79-81.md`. A geração local e a publicação no GitHub Pages são etapas separadas.
