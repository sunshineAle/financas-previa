# Validação da prévia 79–97

Base oficial: Dagda Capital 1.2.2, `financas/main` em `e583dcffc6360b930bbbe6d3b4844233300016cd`, conferida no GitHub em 09/11/2026. As telas, componentes e inicialização são os mesmos da base atual, com as anotações 79 a 97 acrescentadas. O site oficial não foi publicado nem alterado.

- Build de homologação concluído.
- 15 testes do backend: reconhecimento e confirmação de transferências, valor exato, ambiguidade, estorno, recusa persistente, isolamento por usuário, importação e regressão do reconhecimento anterior.
- 4 testes do conector Google: escopo drive.appdata, todas as páginas da área oculta, upload e mensagens de erro.
- Chromium, sobre os arquivos copiados para este repositório: backup cifrado criado pela interface; senha errada recusada; restauração com nome e contas em perfil vazio, sem novo cadastro; restauração por código pedindo apenas nova senha; código de recuperação preservado; reinício da prévia preservando armazenamento fora do prefixo.
- Tela de celular (390 × 844): lista de backups com data e tamanho, escolha de backup anterior, restauração, regra de transferência criada pela interface, confirmação do par em A revisar, ausência de duplicação em Sem categoria e ausência de rolagem horizontal.
- Google no navegador foi simulado: a restauração encontra backups da área oculta e da pasta antiga sem modificar os originais; a prévia preserva cópias oficiais e da pasta antiga; cópias de teste têm gestão protegida, descrita abaixo. Login real, consentimento e acesso da conta Google precisam de homologação manual após a publicação.
- Nenhum pageerror (erro de JavaScript) nos fluxos de navegador executados. Verificação de whitespace dos dois repositórios passou.

A compilação foi validada na branch `previa/anotacoes-79-81` para publicação somente em `financas-previa/main`, autorizada pelo dono. O código-fonte do app oficial não é publicado por esta operação. A pasta antiga Dagda Capital também é consultada na restauração. Os arquivos originais são preservados, sem migração automática. Backups legados sem nome só permitem recuperar o nome efetivamente disponível no arquivo.

## Correção da entrada e do backup antigo

- Google disponível no primeiro acesso/restauração; removido do desbloqueio diário na anotação90. Demonstração acessível pela faixa própria da prévia.
- Demonstração abre automaticamente com dados fictícios, em banco separado da restauração.
- Caso de navegador validado: área oculta vazia, pasta antiga com arquivo .sfin PBKDF2, seleção e senha do backup, nome e contas recuperados sem novo perfil. Todas as requisições ao Drive nesse teste foram GET.
- Google simulado nos testes; autorização real permanece com o usuário. Não foram usados dados ou backups reais na implementação.

## Anotações 82–89

- 27 testes unitários passaram: 15 transferências, 8 instalação, 4 conector Google.
- Regras validada em 390 e 1366 px: três por data de criação, edição sem reordenar, popup completo, retorno da edição, Esc/foco e botão + por bloco.
- Instruções testadas com perfis iPhone Safari, iPad com identificação de desktop, Chrome iPhone, Mac e Android no Chromium. Não são testes em aparelho Apple físico. O download oficial do WebKit foi tentado e bloqueado pela rede com 403.
- Backup pelo lembrete: cancelamento sem transmissão, sucesso só após upload/readback/recuperação, falha de servidor e offline sem mudar data, destino indisponível, primeira configuração e abertura pela rota de notificação. Outro ciclo volta a pedir confirmação.
- Login compacto e Novo acesso com Voltar; backup restaurado com nome e desbloqueio por PIN, sem PIN em metadados abertos.
- Banco ativo comparado antes/depois do teste isolado e permaneceu idêntico. Cifra corrompida e conteúdo estruturalmente inválido foram recusados.
- Rotação simulada de seis para quatro cópias ocorreu só após recuperar a cópia nova em SQLite descartável.
- Exclusão manual bloqueada tanto com uma única cópia quanto com apenas uma recuperável entre várias corrompidas.
- Readback divergente não mudou a data do último backup nem autorizou exclusões.

Google simulado; nenhum backup real foi enviado, apagado ou movido. O teste isolado valida importação, integridade, referências e contagens; não substitui a homologação de todas as operações do usuário em um aparelho real.

## Anotações 90–97 (10/11/2026)

- 38 testes unitários passaram:15 transferências,8 instalação,15 conector Google.
- Desbloqueio diário por PIN sem Google/Testar; primeiro acesso conserva Google e restauração. Demonstração na faixa da prévia.
- Instalação adaptada em iPhone390px, Mac e desktop1366px; convite nativo ou instruções conforme capacidade. Prévia não instala. Orientação evita afirmação absoluta de única maneira. Apple físico/Safari continuam pendentes.
- Google simulado: reuso de token válido, recarga, expiração,401, revogação, escopo parcial/adicional, concorrência e callback atrasado após desconectar. Tokens ficam só em memória; vínculo público não prova autorização atual.
- Conferência automática após700ms ou Enter; Worker real com resposta atrasada e troca de senha/arquivo não libera resultado antigo. CTA central, sem aplicação automática. Chave mestra associada ao conteúdo específico por WeakMap, sem depender da última tentativa global.
- Entrada explica exclusão bloqueada; gestão oferece exclusão somente das cópias gerenciáveis da prévia. Oficiais/legadas somente leitura; cancelar não faz escrita remota.
- Tours interativos substituem WebP vazio de Regras e A revisar; exemplos fictícios com transferência, despesa, parcela e guardar/resgatar. Comparação das tabelas antes/depois idêntica e nenhuma chamada mutante à API em390/1366px. Categorizar parcela não vincula nem quita dívida.
- Regras390/1366px: + na extremidade oposta à implementação anterior (direita nesta compilação), três recentes, edição e popup preservados.
- Regressões de restauração local/Google legado, nome/PIN, corrupção, banco isolado, rotação6→4, última recuperável e lembretes passaram. Nenhum backup real usado.

## Correção do padrão dos tours (10/11/2026)

O dono rejeitou a apresentação interativa da compilação4368318. Os tours de Regras e A revisar voltam ao componente original, com imagem vertical da tela real, animação WebP, anel/gesto de destaque e largura original da janela. A demonstração não possui campos, seletores ou ações utilizáveis. Novas gravações usam dados fictícios em contexto de navegador descartável; não preenchem o banco do usuário. Os testes de exemplos interativos anteriores ficam como histórico da versão rejeitada, não como especificação atual.

Gravações finais: WebP300×585, quatro passos por tour, Regras12,38s e A revisar12s. Conferidos quadros de cada passo com dados preenchidos e anel animado. Testes em390/1366px passaram: imagens carregadas, avanço automático sincronizado ao texto, sem controles na demonstração, banco idêntico antes/depois e nenhuma chamada de escrita à API. Teste anterior interativo foi substituído por `tests/tours-gravados.py`.
