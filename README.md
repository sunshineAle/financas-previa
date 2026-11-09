# Dagda Capital — prévia 79–89

Base: app atual 1.2.2 (`financas/main`, e583dcffc6360b930bbbe6d3b4844233300016cd), com as anotações 79–89 do Cérebro Central. O site oficial não é atualizado por esta publicação.

## Testar

- **Testar com dados fictícios** abre uma demonstração preenchida, sem cadastro ou senha, em um banco separado dos dados restaurados. Inclui um par PIX para A revisar.
- **Entrar com Google** localiza backups ocultos e da pasta antiga Dagda Capital; a senha do backup continua necessária.
- O login usa **Bem-vindo de volta**. Em Novo acesso, **Voltar** retorna às opções de entrada.
- **Regras** mostra três recentes por criação em cada bloco, botão + no topo esquerdo e **Ver todas as regras** em uma janela. No computador os blocos ficam lado a lado.
- O lembrete de backup abre uma confirmação curta usando o último destino. A data só muda depois de concluir a operação. O prazo existente é preservado; não há promessa de execução com app fechado.
- A seleção de backup abre uma janela com senha e conteúdo após descriptografia e teste de importação em SQLite descartável, sem trocar os dados ativos. O nome do perfil e o acesso por PIN são preservados quando presentes no backup.

## Proteção das cópias

Novos backups Google são baixados de volta, comparados e testados em um banco isolado antes de liberar rotação para quatro. Exclusão manual exige outra cópia recuperada com o acesso atual. Se a recuperação não puder ser comprovada, o descarte é bloqueado e mais de quatro cópias podem ser preservadas.

A prévia só gerencia arquivos `previa-*.sfin`. Cópias oficiais e pasta antiga são somente leitura aqui. A proteção do app não impede que alguém apague os dados ocultos diretamente nas configurações do Google ou em outro dispositivo. Mantenha também uma cópia local exportada. Backups na nuvem exigem criptografia ativa.

Armazenamento da restauração: `dagda-previa-79-81:`; demonstração: `dagda-previa-demo-79-81:`. Esses prefixos foram mantidos para preservar os dados já usados nesta homologação. Sem service worker e sem instalação da prévia; **Como instalar o app** mostra as orientações do app oficial.

## Validação

27 testes unitários passaram, além dos fluxos de navegador descritos em [VALIDACAO.md](VALIDACAO.md). Google foi simulado nos testes; nenhum backup real foi enviado ou excluído. Os perfis Apple foram simulados em Chromium; aparelho Apple físico permanece pendente.

## Regerar

No checkout de desenvolvimento de financas, com as alterações da prévia:

```sh
cd frontend
npm ci
npx vite build -c vite.previa.config.js
```

Copie dist-previa para este repositório, preservando .git, README, VALIDACAO, robots.txt, .nojekyll e .github. Não copie sw.js, manifest ou ícones de instalação. Use o checkout existente; não criar worktrees sem pedido explícito.
