# Validação da prévia 79–81

Base oficial: Dagda Capital 1.2.2, `financas/main` em `e583dcffc6360b930bbbe6d3b4844233300016cd`, conferida no GitHub em 09/11/2026. As telas, componentes e inicialização são os mesmos da base atual, com as anotações 79, 80 e 81 acrescentadas. O site oficial não foi publicado nem alterado.

- Build de homologação concluído.
- 15 testes do backend: reconhecimento e confirmação de transferências, valor exato, ambiguidade, estorno, recusa persistente, isolamento por usuário, importação e regressão do reconhecimento anterior.
- 4 testes do conector Google: escopo drive.appdata, todas as páginas da área oculta, upload e mensagens de erro.
- Chromium, sobre os arquivos copiados para este repositório: backup cifrado criado pela interface; senha errada recusada; restauração com nome e contas em perfil vazio, sem novo cadastro; restauração por código pedindo apenas nova senha; código de recuperação preservado; reinício da prévia preservando armazenamento fora do prefixo.
- Tela de celular (390 × 844): lista de backups com data e tamanho, escolha de backup anterior, restauração, regra de transferência criada pela interface, confirmação do par em A revisar, ausência de duplicação em Sem categoria e ausência de rolagem horizontal.
- Google no navegador foi simulado: a restauração encontra backups da área oculta e da pasta antiga sem modificar os originais; a prévia não apaga backups. Login real, consentimento e acesso da conta Google precisam de homologação manual após a publicação.
- Nenhum pageerror (erro de JavaScript) nos fluxos de navegador executados. Verificação de whitespace dos dois repositórios passou.

A compilação foi validada na branch `previa/anotacoes-79-81` para publicação somente em `financas-previa/main`, autorizada pelo dono. O código-fonte do app oficial não é publicado por esta operação. A pasta antiga Dagda Capital também é consultada na restauração. Os arquivos originais são preservados, sem migração automática. Backups legados sem nome só permitem recuperar o nome efetivamente disponível no arquivo.

## Correção da entrada e do backup antigo

- Google e demonstração visíveis desde a entrada, inclusive com acesso já configurado.
- Demonstração abre automaticamente com dados fictícios, em banco separado da restauração.
- Caso de navegador validado: área oculta vazia, pasta antiga com arquivo .sfin PBKDF2, seleção e senha do backup, nome e contas recuperados sem novo perfil. Todas as requisições ao Drive nesse teste foram GET.
- Google simulado nos testes; autorização real permanece com o usuário. Não foram usados dados ou backups reais na implementação.
