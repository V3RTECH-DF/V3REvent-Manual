---
title: Novidades
nav_order: 7
---

# Novidades

O que mudou no V3REvent, em linguagem simples — **da mais recente para a mais antiga**. Cada novidade traz a **versão** em que foi introduzida, para você saber o que é realmente novo.

{: .note }
> A versão instalada aparece no cabeçalho do painel do V3REvent (ex.: `v1.32.0`). Compare com a lista abaixo para ver o que você já tem.

---

## Expurgo da avaliação poupa as notas, e o pedido de exclusão não mexe nos comentários de ninguém
**v1.90.0 · setembro de 2026**

- **Passado o prazo de retenção, só os comentários escritos das avaliações são apagados.** As notas e as respostas de múltipla escolha **continuam**, para você comparar uma edição com a anterior — é só o texto digitado à mão que some, porque é onde alguém pode ter se identificado ou citado outra pessoa. A aba **[Avaliação](/modulos/editor-evento/#avaliação)** do evento e a tela de **[Configurações → Avançado](/modulos/configuracoes/#avançado)** agora avisam isso.
- **Um pedido de exclusão de participante não altera as respostas de avaliação.** A pesquisa é anônima, então não existe "a resposta desta pessoa" — apagar pelo único vínculo disponível apagaria o comentário de todos os respondentes daquele evento. Veja **[Política de Privacidade](/legal/privacidade/)**.

## Avisa quem tenta se inscrever de novo, mais quatro modelos de e-mail editáveis, e o Painel com um nome só
**v1.89.0 · setembro de 2026**

- **Quem tenta se inscrever de novo no mesmo evento agora é avisado.** O formulário público mostra que a pessoa já está inscrita e aponta o caminho até a própria inscrição — mas não bloqueia, porque às vezes a segunda inscrição é mesmo intencional. A comparação é pelo **CPF** (quando o evento pede) ou pelo **e-mail**. A lista de **[Inscrições](/modulos/inscricoes/#duplicidade--quando-a-pessoa-já-está-inscrita)** ganhou a coluna **Duplicidade**, para quem organiza revisar os casos depois.
- **Recibo, credencial, convite de avaliação e certificado agora têm o texto do e-mail editável**, em **[Configurações → E-mails](/modulos/configuracoes/#e-mails)** — antes só confirmação, relatório e acesso à área do inscrito podiam ser personalizados.
- **Configurações e Shortcodes e API deixaram de aparecer para Coordenador de Eventos e Equipe de Evento.** As duas telas são de administração da organização; antes elas abriam para os outros papéis e davam erro ao salvar.
- **A tela inicial chama-se "Painel" nos dois lugares** — painel administrativo e gestão pelo site. Antes, o painel administrativo ainda dizia "Dashboard".
- O código que identifica recibo, credencial, comprovante e certificado ficou **mais longo** (mais difícil de adivinhar por tentativa). Nada muda para quem já tem um link em mãos: **todo link já emitido continua funcionando**.

## Correções na edição de participante: aviso de devolução manual e caixa de aviso no painel do site
**v1.86.1 · setembro de 2026**

Duas correções da tela **[Editar participante](/modulos/editar-participante/)**, lançada na v1.86.0:

- No **painel de gestão pelo site** (veja **[Gestão pelo site](/modulos/gestao-pelo-site/)**), a caixa **Avisar o participante** não aparecia na tela (ficava sem tamanho, invisível) — o valor continuava marcado por padrão, então o aviso saía do mesmo jeito, mas não dava para desmarcar. Agora ela aparece normalmente, igual no `wp-admin`.
- Numa troca que **barateia**, quando o meio de pagamento não devolve automaticamente, a tela agora **avisa antes de você confirmar** que o valor vai precisar ser devolvido por fora (Pix, transferência ou dinheiro) — e confirma de novo, **depois de salvar**, que a devolução ficou registrada como manual. Antes, esse aviso só existia no histórico, depois do fato.

De quebra, o **histórico de alterações** da tela passou a mostrar a situação da diferença (cobrada, cortesia, devolvida, devolução manual…) em **português**, em vez do termo técnico interno.

## Editar participante — corrija sem cancelar, e resolva a diferença quando o valor muda
**v1.86.0 · setembro de 2026**

Errou a modalidade, o nome ou o e-mail de alguém na hora da inscrição? Agora dá para **corrigir direto**, sem cancelar a inscrição e pedir para a pessoa se inscrever de novo. Um botão **Editar participante**, por linha, abre o mesmo formulário do público já preenchido — vale por pessoa, não em lote — na lista **[Inscrições](/modulos/inscricoes/)** (`wp-admin` e painel de gestão pelo site) e na aba **Inscritos** do evento. Por padrão, o participante recebe de novo a confirmação com os dados corrigidos; a tela guarda um **histórico** de quem alterou o quê, e avisa se a pessoa já fez check-in.

Quando a correção muda a **modalidade** e isso muda o preço, o sistema calcula a diferença na hora, no lote em que a pessoa se inscreveu, e oferece o caminho para resolver: **cobrar** (com link de pagamento sem login, ou marcar como paga por fora) ou dar de **cortesia**, quando encarece; **devolver** (automático, quando o meio de pagamento aceita) ou **não devolver**, quando barateia. Um padrão por evento, em **Preços → Troca com diferença de valor**, evita repetir a escolha a cada troca. Veja **[Editar participante](/modulos/editar-participante/)**.

{: .important }
> **Reembolso total pela tela do pedido cancela a inscrição inteira.** Para acertar uma troca de modalidade, use sempre a tela **Editar participante** — nunca o reembolso integral do pedido no WooCommerce.

## Correção de privacidade no comprovante individual: modalidade removida, data mais legível
**v1.85.1 · setembro de 2026**

Duas correções no **[comprovante individual](/modulos/documentos/#comprovante)**, lançado na v1.85.0:

- O comprovante **não mostra mais a modalidade** da inscrição. Em alguns eventos, o campo usado para calcular o preço carrega um dado sensível (por exemplo, "Pessoa com Deficiência") — e ele aparecia ali, num documento pensado para circular por WhatsApp. Agora o comprovante traz só nome e código do participante, além dos dados do próprio evento (evento, data, local e situação).
- A **data do evento** passou a aparecer em formato legível (ex.: "19/09/2026"), em vez do valor cru gravado no sistema.

## Comprovante individual de inscrição — um documento próprio para cada participante
**v1.85.0 · setembro de 2026**

Além do recibo (que é só do responsável pelo pagamento), cada **participante confirmado** agora tem um **comprovante individual de inscrição**: uma página no celular e um PDF para baixar ou imprimir, com nome, código, evento, data, local e situação — **sem valor pago, sem dados de quem pagou e sem os nomes dos outros participantes do grupo**. Pode ser mandado com segurança a qualquer participante, mesmo quando quem pagou a inscrição foi outra pessoa, e serve também para eventos que **não emitem credencial**.

O comprovante chega ao participante de três formas: pela **[Área do Inscrito](/modulos/area-do-inscrito/)**, pelo **link no e-mail de confirmação** (que o ícone de envelope reenvia, inclusive em lote, na lista de Inscrições), e por um **link para copiar e colar numa conversa** — novo ícone na lista de **[Inscrições](/modulos/inscricoes/)**, disponível para quem coordena o evento e para a administração. Veja **[Documentos → Comprovante](/modulos/documentos/#comprovante)**.

{: .tip }
> Personalizou o e-mail de confirmação antes desta versão? Não precisa editar nada: se o seu texto não usa a nova variável `{voucher_url}`, o link do comprovante é acrescentado automaticamente ao final da mensagem.

## A busca da lista de Inscrições agora encontra pelos dois lados
**v1.84.0 · setembro de 2026**

Na lista **Inscrições**, o campo de busca passou a encontrar a pessoa pelo nome ou e-mail do **participante**, além do nome ou e-mail do **responsável** — antes só o responsável era encontrado. Se você lembra do nome de quem participou mas não de quem pagou, agora a busca encontra do mesmo jeito. Veja **[Inscrições → Filtros e busca](/modulos/inscricoes/#filtros-e-busca)**.

## Coluna "Envio da confirmação": saiba quem recebeu e quem não recebeu
**v1.83.0 · setembro de 2026**

A lista **Inscrições** ganhou uma coluna própria para o e-mail de confirmação — separada do status da inscrição, que só diz se o **pagamento** foi confirmado, não se o e-mail chegou. Antes, quando o envio falhava, não havia como saber pela tela: só o próprio participante reclamando é que revelava o problema. Agora a coluna mostra, para cada participante, uma entre quatro situações: **Enviado**, **Em nova tentativa**, **Falhou** (com o motivo ao passar o mouse) ou **Não enviado**. Ela vem marcada para aparecer por padrão.

Também há um **filtro por situação de envio**, ao lado dos outros filtros da lista, e um **aviso no topo** quando existe alguma falha no recorte que você está vendo — com um botão que já aplica o filtro "Falhou", para você ir direto a quem precisa de atenção. Veja **[Inscrições → Envio da confirmação](/modulos/inscricoes/#envio-da-confirmação-saiba-quem-recebeu-e-quem-não-recebeu)**.

{: .tip }
> **Quando o e-mail do participante está registrado de duas formas diferentes** (por exemplo, um campo de e-mail do formulário do evento e um cadastro interno divergem), a confirmação passa a ir para os **dois endereços**, em mensagens separadas — melhor um e-mail a mais do que a pessoa não receber nada.

## O menu do V3REvent agora se agrupa com os outros produtos V3RTECH no menu lateral
**v1.83.0 · setembro de 2026**

Quando outros produtos da V3RTECH instalados no mesmo site também anunciam sua posição, o V3REvent passa a aparecer **agrupado com eles** no menu lateral do WordPress, em vez de espalhado em qualquer ordem. Sozinho no site — sem outros produtos da casa, ou com versões antigas deles —, nada muda: a posição do menu continua a mesma de sempre.

---

## O aviso de nova tentativa automática virou dica do ícone, não mais uma etiqueta na linha
**v1.82.2 · setembro de 2026**

A etiqueta âmbar **"Em nova tentativa"**, introduzida na v1.77.0, saiu da lista **Inscrições**. No lugar dela, o participante nesse estado aparece com o **ícone de reenvio acinzentado e desabilitado** — passe o mouse sobre ele (no computador) para ver a previsão, algo como *"Nova tentativa automática a caminho, prevista para 06/09/2026, 22:11:38"*, somada ao histórico de reenvio quando já houver um. O comportamento por trás continua o mesmo (o sistema tenta de novo sozinho, até 3 vezes); só a forma de avisar mudou, para caber na coluna mais enxuta introduzida na v1.82.1. Veja **[Inscrições → Nova tentativa automática](/modulos/inscricoes/#nova-tentativa-automática-quando-o-envio-falha)**.

{: .note }
> **No celular não há como passar o mouse**, então a previsão não aparece lá — só o ícone acinzentado, indicando que o envio está sendo cuidado sozinho.

## Coluna Ações mais enxuta na lista de inscritos
**v1.82.1 · setembro de 2026**

Na lista **Inscrições**, o número do pedido ao lado do ícone de reenvio (antes escrito por extenso, "Pedido #1319") virou um **ícone**, e o número passa a aparecer só ao **passar o mouse** sobre ele. O histórico de reenvio ("Reenviado Nx, último em...") saiu de baixo do botão e foi para a **dica do próprio ícone de reenvio** — nessa versão, o aviso "Em nova tentativa" ainda seguia visível como etiqueta na linha (isso mudou logo em seguida, veja a novidade da v1.82.2 acima). A coluna fica mais curta e mais fácil de ler, sobretudo com muitos participantes na tela.

{: .note }
> **No celular não há como passar o mouse**, então o número do pedido e o histórico de reenvios não aparecem lá — é uma escolha deliberada, não uma falha. No celular, toque no ícone de link para abrir o pedido. Veja **[Inscrições → Reenvio individual](/modulos/inscricoes/#reenvio-individual)**.

## Reenvio em lote: pedido novo entra na fila, e o envio que não saía foi corrigido
**v1.82.0 · setembro de 2026**

Pedir um reenvio em lote enquanto **outro já está em andamento** deixou de ser recusado — agora o pedido novo **entra no fim da fila** e começa a ser despachado assim que o anterior terminar. Isso ajuda quem reenvia aos poucos, conforme vai encontrando quem precisa em páginas ou filtros diferentes da lista: manda para um grupo, acha outro grupo depois, manda de novo, sem esperar. O ritmo continua o mesmo para todos (100 mensagens a cada 5 minutos), então acumular pedidos na fila **alonga a espera**, nunca acelera. Veja **[Inscrições → Reenvio em lote](/modulos/inscricoes/#reenvio-em-lote)**.

Também corrigimos um defeito: em algumas situações, o **reenvio em lote não estava enviando nada**, embora a tela confirmasse o pedido normalmente. Se você usou o reenvio em lote entre as versões afetadas, vale conferir se as pessoas realmente receberam o e-mail — pelo Mailpit/log de envio do seu servidor, ou perguntando a quem deveria ter recebido.

## E-mail de acesso à área do inscrito agora é editável
**v1.81.0 · setembro de 2026**

O texto do **e-mail de acesso à Área do Inscrito** — o que leva o link para quem pede para reencontrar as próprias inscrições — deixou de ser fixo. Em **Configurações → E-mails** ele ganhou seu próprio bloco, com **assunto**, **corpo**, a explicação de quando é disparado, e as variáveis `{access_url}`, `{valid_hours}`, `{site_name}` e `{site_url}`. Veja **[Configurações → E-mails](/modulos/configuracoes/#e-mails)**.

---

## Correção de privacidade na Área do Inscrito
**v1.79.2 · setembro de 2026**

Quem só participava de um grupo comprado por outra pessoa não via o botão do comprovante — como deve ser, já que ele traz o nome de quem pagou e o valor. Mas a tela mostrava o **código da inscrição** logo ao lado, e esse código é justamente o que abre o comprovante pelo endereço público. Na prática, a regra existia e a própria página entregava o caminho para contorná-la.

Agora o código aparece só para quem fez a inscrição, exatamente como o botão. Quem fez a inscrição continua vendo o código mesmo antes do pagamento ser confirmado — é o número que ele usa para falar com você. **Nenhuma ação é necessária da sua parte**; quem já tinha a versão anterior instalada passa a se comportar assim ao atualizar.

## O shortcode da Área do Inscrito na lista de shortcodes
**v1.79.1 · setembro de 2026**

A Área do Inscrito nasceu funcionando, mas o shortcode dela não aparecia em **Shortcodes e API** — e essa lista é onde você descobre o que pode colar numa página. Agora `[v3revent_area_inscrito]` está lá, com a explicação de que a página já é criada sozinha e de que o shortcode serve só para montá-la em outro endereço. Veja **[Shortcodes e API](/modulos/shortcodes-e-api/)**.

## Área do Inscrito: quem se inscreveu reencontra tudo sozinho
**v1.79.0 · setembro de 2026**

Antes, quem perdia o e-mail de confirmação só tinha um caminho: escrever para a organização e esperar. Agora existe a **Área do Inscrito**, uma página pública criada automaticamente no seu site: a pessoa informa o e-mail, recebe um link de acesso e vê ali suas inscrições — com comprovante, credencial e certificado, cada um só quando já disponível.

O que aparece depende de como a pessoa participou: quem **fez a inscrição** (inclusive de um grupo inteiro) vê o comprovante e a credencial/certificado de todos os participantes; quem **só participa** de um grupo comprado por outra pessoa vê apenas a própria credencial e o próprio certificado — nunca os colegas nem o valor pago. Por segurança, a página sempre responde a mesma coisa, exista ou não o e-mail na base, e o link vale 24 horas e serve uma vez só. Veja **[Área do Inscrito](/modulos/area-do-inscrito/)**.

## Controle para oferecer ou não credencial por evento
**v1.79.0 · setembro de 2026**

A aba **Credencial** do editor de evento ganhou um controle **Oferecer credencial para este evento**, no mesmo formato do controle de emissão do certificado. Desligado, a credencial deixa de existir por completo para aquele evento: some da Área do Inscrito, o link público para de responder e ela não sai mais anexada no e-mail. **Nasce ligado** em todo evento — os que já existiam e os novos — então nada muda para quem não mexer. Veja **[Editor de evento → Credencial](/modulos/editor-evento/#credencial)**.

{: .note }
> **v1.80.0** saiu sem novidades para você: foi uma mudança interna, em que a sugestão de correção de e-mail passou a vir da biblioteca compartilhada dos plugins da V3RTECH, em vez de uma cópia própria do V3REvent. O comportamento na tela é o mesmo.

---

## Envio de e-mail em massa sem limite, com nova tentativa automática
**v1.77.0 · setembro de 2026**

O reenvio "para todos os que correspondem ao filtro" deixou de ter um teto de alcance — antes, um filtro com mais de mil participantes deixava o excedente inalcançável, mesmo repetindo a operação. Agora o envio chega a todos, em qualquer volume, só que de forma **gradual**: em lotes de 100 mensagens a cada 5 minutos, para não sobrecarregar o servidor de e-mail do site. Antes de confirmar um envio grande, a tela avisa que ele será gradual e estima quanto tempo leva; enquanto ele roda, um aviso mostra quantos lotes ainda faltam — para você não achar que travou e mandar de novo.

Além disso, uma indisponibilidade passageira no envio de e-mail (servidor fora do ar por instantes, limite de taxa, caixa cheia) deixa de derrubar o envio de vez: o V3REvent **tenta de novo sozinho**, até três vezes, com intervalo crescente — com o participante marcado como **"Em nova tentativa"** enquanto isso acontece (a partir da v1.82.2 esse aviso deixou de ser uma etiqueta na linha e passou a aparecer ao passar o mouse sobre o ícone de reenvio acinzentado). E-mail ausente ou claramente inválido não entra nessa recuperação automática, porque nesse caso o problema é o dado, não o envio. Veja **[Inscrições → Reenviar a confirmação de inscrição](/modulos/inscricoes/#reenviar-a-confirmação-de-inscrição)**.

## Sugestão de correção de e-mail no formulário público
**v1.76.0 · setembro de 2026**

Quando alguém digita um domínio quase certo no formulário de inscrição — `gmail.con`, `hotmial.com`, `outlok.com` — aparece uma sugestão gentil logo abaixo do campo, com um clique para corrigir. **Nunca bloqueia**: quem tem um domínio próprio ou incomum, ou simplesmente prefere ignorar, segue normalmente com o que digitou. Vale para o e-mail do responsável e para qualquer campo de e-mail que você tenha configurado no evento. Veja **[Formulário público → Sugestão de correção de e-mail](/modulos/formulario-publico/#sugestão-de-correção-de-e-mail)**.

De quebra, o e-mail gravado passou a ter espaços removidos e letras uniformizadas em minúsculas — sem isso, "Nome@Gmail.com" e "nome@gmail.com" podiam ser tratados como pessoas diferentes por quem consultasse esse dado depois.

## Lista de inscritos pronta para eventos grandes
**v1.75.0 · setembro de 2026**

A lista de **Inscrições** ganhou um seletor de **itens por página** — 20, 50, 100 ou Todos —, com a escolha salva para as próximas vezes, do mesmo jeito que já acontecia com as colunas. Em "Todos", passando de mil participantes a tela avisa que está mostrando só uma parte, para ninguém achar que viu a lista inteira.

O reenvio em lote de confirmação, lançado na versão anterior, ganhou a opção de **"selecionar todos os participantes deste filtro"** — antes, marcar "todos" só alcançava a página aberta (20 de cada vez); num evento com centenas de inscritos, reenviar para todo mundo exigia repetir a operação várias vezes. Veja **[Inscrições → Itens por página](/modulos/inscricoes/#itens-por-página)**.

## Reenvio da confirmação de inscrição, individual e em lote
**v1.74.0 · setembro de 2026**

Até aqui, quando um inscrito dizia não ter recebido o e-mail de confirmação, não havia nada a fazer além de orientá-lo a checar o spam. Agora cada participante da lista de **Inscrições** (nos dois painéis — `wp-admin` e o painel publicado no site) tem um botão **Reenviar confirmação**, com seleção múltipla para reenviar a vários de uma vez e uma confirmação prévia dizendo quantas pessoas vão receber.

Só participante de inscrição **confirmada** recebe reenvio — pendente ou cancelada fica com o botão desabilitado, para não confirmar ou cobrar de quem não deveria. Numa inscrição individual, o recibo acompanha o reenvio; numa inscrição em grupo, só a confirmação é reenviada — o recibo tem o valor total e os dados de quem pagou, e é assunto só do responsável. Cada reenvio fica registrado (quantas vezes e quando foi o último), visível na própria linha. Veja **[Inscrições → Reenviar a confirmação de inscrição](/modulos/inscricoes/#reenviar-a-confirmação-de-inscrição)**.

## E-mail do participante, visível na lista sem precisar configurar nada
**v1.74.0 · setembro de 2026**

A lista de **Inscrições** passou a trazer, por padrão, uma coluna com o **e-mail do participante** — antes só aparecia o e-mail de quem fez a inscrição, e conferir se um participante específico tinha digitado o e-mail certo exigia abrir o pedido no WooCommerce. Continua funcionando em evento cujo campo de e-mail tenha outro nome, e fica vazia (sem quebrar nada) em evento sem campo de e-mail. Quem já tinha escolhido suas próprias colunas não teve nada alterado. Veja **[Inscrições → Colunas visíveis](/modulos/inscricoes/#colunas-visíveis)**.

---

## Atualizações automáticas pelo painel do WordPress
**v1.73.0 · agosto de 2026**

O V3REvent passa a se **atualizar como qualquer outro plugin do seu site**: uma nova versão aparece na tela de **Plugins** do WordPress, com o aviso de atualização de sempre — sem precisar que alguém envie o arquivo por FTP ou peça para a equipe da V3RTECH publicar manualmente.

Junto com isso, o plugin passa a **reconhecer a licença de uso** da V3RTECH, com uma tela própria para isso: a aba **Licença**, em **Configurações** (ao lado de Organização, E-mails, Aparência, Avançado e Administradores). Nela você vê o estado atual da licença (chave mascarada, validade, ativações usadas e a última verificação), ativa uma chave nova, e — com a licença já ativa — verifica o status a qualquer momento, desativa ou troca de chave.

Duas coisas importantes:

- **Licença vencida não desliga o plugin.** O que a licença cobre é o direito a receber atualizações e correções — com ela vencida, o V3REvent continua funcionando **normalmente e por inteiro**; só as atualizações automáticas param, até a licença ser renovada. É a própria tela quem avisa disso, logo no topo.
- **Nada do que já existe muda de lugar ou de comportamento.** Se você não usa licenciamento, não precisa fazer nada.

---

## Relatório do evento reformulado: indicadores legíveis e descrição sob controle
**v1.71.0 · agosto de 2026**

O **Relatório do evento** (aba **Relatório** do editor) ganhou uma revisão completa. O bloco "Inscritos e presença" — que em alguns casos quebrava numa lista vertical e fazia cada número colar no rótulo seguinte, dando a entender que a arrecadação era zero — agora sai com os indicadores lado a lado, cada número junto do seu próprio rótulo, com uma nota curta explicando como cada um é calculado. "Realização do previsto" mostra **"sem meta definida"** em vez de um percentual sem sentido, quando o evento não tem meta de arrecadação. Todas as páginas passaram a ter **cabeçalho** (com o logo da organização) e **rodapé** (evento e numeração de página), e os títulos e destaques seguem as **cores da sua organização**. A maior mudança visível: agora você escolhe, por evento, como a **descrição** entra no relatório — **resumo curto** (padrão), **texto puro** ou **completo** com a formatação da página pública. Antes, a descrição formatada podia tomar as três primeiras páginas do documento. Veja **[Editor de evento → Relatório](/modulos/editor-evento/#relatório)**.

## Coluna de valor nas inscrições e nas exportações
**v1.70.0 · agosto de 2026**

As telas **Inscrições** e **Relatórios** (e as exportações em CSV, XLSX e PDF) ganharam duas colunas no seletor de colunas: **"Valor da inscrição"** (o total cobrado pelo pedido, mostrado só na primeira linha — para não inflar a soma numa inscrição em grupo) e **"Valor por participante (média)"**. Inscrição **pendente ou cancelada** aparece com o valor **entre parênteses**, para deixar claro que ele não entra na soma — assim, somar a coluna na planilha bate com o total que você vê em Relatórios. Veja **[Inscrições](/modulos/inscricoes/#exportar)**.

## O valor arrecadado passa a ser o que foi realmente cobrado
**v1.69.0 · agosto de 2026**

Corrigimos uma distorção importante: quando uma inscrição era paga com **cupom de desconto**, o V3REvent contabilizava o **preço cheio** — o total que você via no Painel, em Relatórios e no PDF do evento ficava maior do que o dinheiro que de fato entrou. Agora o valor registrado é sempre o **do pedido**, cupom incluído, e não é mais recalculado depois. Uma consequência para quem já usava cupons: **inscrições feitas antes desta atualização continuam pelo valor de tabela** (sem correção retroativa) e aparecem identificadas numa nota junto do total — então é esperado que a receita total **caia** um pouco em eventos que tiveram cupons, e essa queda é a correção, não um erro. Veja **[Descontos com cupom](/guia-do-gestor/descontos-com-cupom/)**.

---

## O painel de gestão no site passou a respeitar a largura da sua página
**v1.68.5–v1.68.8 · agosto de 2026**

Quando você cola o `[v3revent_gestao]` numa página montada com Elementor, Divi ou outro construtor, o painel agora **respeita a largura que você definiu** para o container em vez de encolher para o tamanho do conteúdo ou ignorar o limite configurado. Corrigimos também dois casos mais específicos: container estreito dentro de outro container estreito (comum em layouts com colunas aninhadas) e a largura recalculada pelo site quando a tela muda de tamanho. Quer o painel mais largo ou mais estreito? **Ajuste a largura do container na própria página** — não há nada a configurar no plugin, ele sempre acompanha o espaço que você deu a ele. Veja **[Gestão pelo site](/modulos/gestao-pelo-site/)**.

## Botões e campos maiores no celular e no tablet
**v1.68.1 · agosto de 2026**

Nas telas de gestão (Painel, Eventos, Inscrições, Check-in, Relatórios), os botões e campos ficaram **maiores em celular e tablet** — no tamanho mínimo recomendado para toque, sem precisar mirar com precisão. No computador, com o mouse, tudo continua do mesmo tamanho de sempre. O ganho é mais sentido no **Check-in**: quem faz check-in em pé, na portaria, com o celular na mão, tem menos chance de errar o toque no botão certo.

## Gestão de eventos direto no site, sem precisar do wp-admin
**v1.68.0 · agosto de 2026**

Agora dá para gerenciar eventos **sem entrar no painel do WordPress**. Cole o shortcode `[v3revent_gestao]` numa página comum do site e quem tem papel em algum evento passa a acessar **Painel, Eventos (com o editor completo), Inscrições, Check-in e Relatórios** — inclusive exportar em CSV, XLSX e PDF — por ali, com as **mesmas permissões** que teria no `wp-admin`. É a solução para equipe que faz check-in ou acompanha inscrições sem precisar (nem dever) ter uma conta de administrador do WordPress. As Configurações da organização continuam exclusivas do painel, e a página não aparece para quem não tem papel em nenhum evento. Veja **[Gestão pelo site](/modulos/gestao-pelo-site/)**.

## Hora, além da data, nas inscrições e nos lotes
**v1.63.0 · agosto de 2026**

A **Data de abertura**, a **Data limite de inscrições** (aba Detalhes) e o **início/fim de cada lote de preço** (aba Preços) agora aceitam **hora**, não só data — dá para encerrar as inscrições ao meio-dia ou fazer um lote virar às 18h, por exemplo. A hora é **opcional**: sem ela, tudo continua como sempre (abertura à meia-noite, limite até o fim do dia). O sistema já sugere o início de um lote novo como o minuto seguinte ao fim do anterior, e avisa se perceber um buraco ou sobreposição entre lotes — um buraco fecha as inscrições nesse intervalo, então vale conferir. A página do participante também **atualiza o preço sozinha** quando o lote vira, sem precisar recarregar. Veja **[Editor de evento → Detalhes](/modulos/editor-evento/#data-e-hora-não-só-data)** e **[Preço por lote](/modulos/editor-evento/#início-e-fim-com-hora-e-o-encadeamento-automático)**.

## Inscritos do evento direto no editor
**v1.58.0 · julho de 2026**

Agora, ao abrir um evento no editor, há uma aba **Inscritos** (logo depois de **Detalhes**) que mostra **só os inscritos daquele evento** — sem precisar ir até a tela geral **Inscrições** e filtrar. É a mesma lista de sempre, já focada no evento: dá para **ver** as inscrições, **trocar o status** de cada uma clicando na etiqueta colorida (**Pendente / Confirmada / Cancelada**) e **exportar** em **CSV**, **XLSX** ou **PDF**. A tela geral **Inscrições** (todos os eventos) continua existindo igual — a aba é um atalho para quando você está acompanhando um evento específico. Veja em **[Editor de evento → Inscritos](/modulos/editor-evento/#inscritos)**.

## A inscrição agora passa pelo carrinho
**v1.57.0 · julho de 2026**

Antes, ao confirmar a inscrição, o participante ia **direto para a tela de pagamento**, pulando o carrinho. Isso o impedia de **revisar ou desistir** e, se ele saísse no meio (fechar o navegador, acabar a energia) e voltasse depois, uma **nova inscrição se somava** à anterior — acumulando pedidos. Agora a inscrição vai para a **página do carrinho**, onde ele pode **revisar, remover, esvaziar ou continuar comprando** antes de pagar (como em qualquer loja WooCommerce). O botão passou a dizer **"Confirmar inscrição e ir para o carrinho"**, e o item no carrinho **lista os nomes das pessoas inscritas** — o que ajuda a identificar inscrições ou participantes repetidos, sobretudo na inscrição de **grupo**. Como o número de inscritos vem dos participantes preenchidos no formulário, o item **não tem seletor de quantidade** no carrinho: para mudar quantas pessoas se inscrevem, é só **refazer a inscrição** no formulário. Veja em **[Formulário público](/modulos/formulario-publico/)**.

## Trocar o status da inscrição ficou mais simples
**v1.56.0 · julho de 2026**

Na tela **Inscrições**, a coluna **Status** tinha uma etiqueta colorida **e** um menu suspenso logo abaixo, repetindo a mesma informação. Agora a **própria etiqueta é clicável**: clique nela e escolha o status no menu (**Pendente / Confirmada / Cancelada**), cada um com seu ícone e cor, com o atual marcado. Mais limpo e direto, sem perder clareza. O **filtro por status** no topo da lista continua igual. Veja em **[Inscrições](/modulos/inscricoes/#status-de-uma-inscrição)**.

## Controles de tamanho de texto dentro do topo do evento
**v1.55.0 · julho de 2026**

Os controles de acessibilidade **A− / A / A+** deixaram de ocupar uma faixa de largura inteira no topo da página e agora aparecem numa **caixinha discreta no canto superior direito do topo do evento (hero)** — economizando espaço e mantendo o recurso à mão. A caixinha é translúcida e legível sobre qualquer tipo de topo (imagem, imagem+texto ou só texto), no tema claro ou escuro; no **celular**, fica compacta no canto sem cobrir o título. O funcionamento é o mesmo (aumenta/diminui o conteúdo, memoriza a escolha, liga/desliga na aba **Aparência**). Veja em **[Página do evento](/modulos/pagina-do-evento/#acessibilidade-tamanho-do-texto)**.

## Largura dos campos no formulário
**v1.54.0 · julho de 2026**

Agora você define a **largura de cada campo** do formulário de inscrição: **1 coluna (⅓)**, **2 colunas (⅔)** ou **3 colunas (linha inteira)**. Na aba **Campos do Formulário**, cada campo tem a opção **Largura** — dá para montar linhas compactas (ex.: **Cidade · Estado · CEP** lado a lado) e deixar campos longos, como **Nome completo**, ocupando a linha toda. No **celular** tudo empilha automaticamente. Por padrão os campos começam em **linha inteira**; se você já tinha campos aparecendo lado a lado, eles passam a empilhar até você escolher as larguras (ajuste rápido). Veja em **[Campos do Formulário](/modulos/editor-evento/#largura-do-campo)**.

## Correção: texto invisível ao digitar no formulário (tema escuro)
**v1.53.2 · julho de 2026**

Corrigimos um problema de legibilidade no **formulário de inscrição** quando o **tema do seu site** usa fundo escuro: em alguns casos, o texto que a pessoa **digitava** nos campos (texto, área de texto e listas de seleção) ficava **invisível** — texto escuro sobre fundo escuro. Agora o formulário mantém o fundo e a cor do texto sempre combinando, prevalecendo sobre o tema do site, e o conteúdo digitado volta a aparecer com clareza, tanto no modo claro quanto no escuro. (Complementa o ajuste das listas de seleção feito na v1.49.1.)

## Correção: campo de envio de arquivos aparecendo
**v1.53.1 · julho de 2026**

Logo após lançarmos o **campo de arquivo (upload)**, ele podia aparecer **sem o botão de anexar** na página pública, mostrando só o rótulo. Corrigido: o botão para escolher o arquivo agora aparece normalmente no formulário. Se você criou um campo de arquivo e ele parecia não funcionar, basta atualizar para esta versão.

## Campo de envio de arquivos
**v1.53.0 · julho de 2026**

O formulário agora tem um tipo de campo **Arquivo (upload)**: o inscrito pode **enviar documentos** (laudo, comprovante, etc.). Na aba **Campos do Formulário**, escolha o tipo **Arquivo** e defina os **tipos aceitos**, o **tamanho máximo** e se permite **um ou vários** arquivos. Os arquivos ficam **guardados de forma privada** e só você (ou quem tem permissão no evento) baixa, pela aba **Relatórios**. Tudo com segurança e conforme a LGPD — os arquivos são apagados junto com os dados do inscrito.

## Campos condicionais no formulário
**v1.52.0 · julho de 2026**

Agora você pode fazer um campo do formulário **aparecer só quando fizer sentido**. Na aba **Campos do Formulário**, cada campo tem uma seção **Condições de exibição**: por exemplo, mostrar **"Nome do guia"** apenas quando **"Precisa de guia?" = Sim**. Dá para **combinar várias condições** (exigindo **todas** ou **qualquer uma**) e usar **igual a** / **diferente de**. Um campo oculto pela condição não é exigido nem gravado. Formulários mais curtos e inteligentes, sem pedir o que não se aplica.

## Controle de tamanho do texto (acessibilidade)
**v1.51.0 · julho de 2026**

A página do evento passa a oferecer controles **A− / A / A+** para o visitante **aumentar ou diminuir o tamanho** do conteúdo — uma ajuda de acessibilidade para quem tem baixa visão. A preferência fica **lembrada** no navegador dele. Vem **ligado por padrão**; se quiser, você desliga por evento na aba **Aparência** do editor. (Vale no layout **"Página do Plugin"**.) _Na v1.55.0 esses controles passaram para uma caixinha discreta no canto do topo do evento._

## Preço por modalidade mais simples
**v1.50.0 · julho de 2026**

Ficou mais fácil definir um preço por **modalidade** (ex.: um valor com desconto para PCD). Quando o evento **não** usa desconto por quantidade, cada modalidade agora mostra um **campo simples "Preço (R$)"** — é só digitar o valor, sem precisar montar "faixas" nem ligar o desconto por quantidade. Vale tanto no evento quanto em cada **lote**. Deixando em branco, a modalidade usa o **valor base**. Eventos que já usavam faixas por quantidade continuam funcionando igual.

## Gradientes de fundo na descrição do evento
**v1.49.0 · julho de 2026**

Agora dá para usar **gradientes CSS** de fundo na **descrição do evento** — um ou vários na mesma caixa — para montar heros coloridos, faixas e efeitos decorativos direto pelo editor, sem precisar de imagem. Antes o WordPress descartava esses fundos (só aceitava um gradiente simples). Continua tudo seguro: imagens externas e trechos perigosos seguem bloqueados. Veja exemplos em **[Personalizar com CSS](/modulos/personalizar-css/)**.

## Documentos com layout melhor e título personalizável
**v1.48.0 · julho de 2026**

A seção de **Documentos** na página do evento ficou mais organizada:

- Os documentos agora aparecem em **grade** (vários por linha, preenchendo a largura) em vez de um por linha.
- A seção usa a **mesma largura do formulário de inscrição** — o mesmo vale para os **Patrocinadores** —, alinhando tudo na página.
- O **título** da seção segue o mesmo estilo do título do formulário.
- Você pode **personalizar o título** da seção na aba **Documentos** do editor (ex.: "Documentos complementares", "Leia mais"). Em branco, continua "Documentos".

## Título no formulário de inscrição
**v1.47.0 · julho de 2026**

O formulário de inscrição agora começa com um **título** — por padrão, **"Inscrição"** — que dá contexto ao bloco, em vez de começar direto na data e no local. As informações de **data e local** logo abaixo também passaram a ficar **centralizadas**. Quem quiser trocar o texto do título (por exemplo, "Garanta sua vaga") pode fazê-lo por personalização; para ocultá-lo, basta deixá-lo vazio.

## Data e local com mais destaque na página do evento
**v1.46.0 · julho de 2026**

Na página do evento, a **data** e o **local** agora aparecem em **destaque e centralizados**, logo abaixo do topo — cada um numa "pílula" com um ícone (calendário e localização). Antes esse trecho ficava pequeno e encostado à esquerda, o que parecia deslocado em telas grandes (Full HD e maiores). A **descrição do evento**, logo abaixo, também passou a ser **centralizada**. Tudo continua legível tanto no tema **claro** quanto no **escuro**, e o local segue clicável quando você informa o link do mapa. Não é preciso configurar nada: a mudança vale automaticamente para as páginas no layout **"Página do Plugin"**.

## Contagem regressiva na página do evento
**v1.44.0 · julho de 2026**

A página do evento pode mostrar uma **contagem regressiva** ao vivo — dias, horas, minutos e segundos que se atualizam sozinhos. Há **dois contadores independentes**, cada um com o seu interruptor na aba **Detalhes** do editor:

- **Início do evento** — quanto falta para o evento começar;
- **Fim das inscrições** — quanto falta para a data limite de inscrições.

Cada contador só aparece se a data correspondente estiver **preenchida** e ainda for **futura** — quando a data passa, o contador some sozinho. O contador de **fim das inscrições** é ótimo para criar urgência na reta final. Veja **[Editor de evento → Detalhes](/modulos/editor-evento/)**.

## Contato dos organizadores na página do evento
**v1.43.0 · julho de 2026**

Agora dá para exibir um cartão **"Fale com a organização"** na página do evento, com os canais de atendimento. Ligue **Exibir contato dos organizadores na página** na aba **Detalhes** e preencha o que quiser divulgar: **e-mail**, **WhatsApp** e **telefone**. Só os campos preenchidos aparecem, e o botão do WhatsApp abre a conversa direto (informe o número **com o código do país**, ex.: `55`). Um contato visível reduz dúvidas e passa confiança a quem vai se inscrever. Veja **[Editor de evento → Detalhes](/modulos/editor-evento/)**.

## Aviso de inscrições e data de abertura
**v1.42.0 · julho de 2026**

Quando as inscrições **não estão abertas**, a página do evento agora mostra um **aviso claro** logo abaixo do topo, em vez de só esconder o formulário:

- **Inscrições em breve** — antes de abrir (mostra a data de abertura, se informada);
- **Inscrições encerradas** — depois da data limite;
- **Inscrições indisponíveis no momento** — quando você fecha as inscrições manualmente.

Para isso, a aba **Detalhes** ganhou o campo **Data de abertura das inscrições**, o par simétrico da **data limite**: antes dela a página mostra "Em breve" e o formulário fica bloqueado; depois, as inscrições abrem sozinhas. Com **abertura** e **limite** preenchidas, você programa a **janela de inscrição** inteira, sem precisar ligar nem desligar o formulário na mão. Se deixar a data de abertura em branco, as inscrições já começam abertas — como sempre foi. Veja **[Editor de evento → Detalhes](/modulos/editor-evento/)**.

## Escolha o tamanho da logo do evento na página
**v1.41.0 · julho de 2026**

Além de escolher **onde** a logo aparece, agora você define o **tamanho dela** na página do evento — na aba **Aparência** do editor, no seletor **Tamanho da logo na página**: **Pequeno**, **Médio** (padrão), **Grande** ou **Personalizado**.

No modo **Personalizado**, você informa **a largura _ou_ a altura** (entre **40 e 600 px**) e a outra dimensão é **calculada automaticamente**, mantendo a proporção da imagem, sem distorção. A logo continua sempre sobre o **cartão branco**. Eventos que já existiam ficam em **Médio** — mude só se quiser. Veja **[Editor de evento → Aparência](/modulos/editor-evento/)**.

## Escolha onde a logo do evento aparece na página
**v1.40.0 · julho de 2026**

Você agora decide **onde a logo do evento aparece** na página do evento — na aba **Aparência** do editor, no seletor **Posição da logo na página do evento**:

- **No topo da página (destaque)** (padrão) — a logo em destaque no alto da página;
- **Abaixo do hero** — a logo logo depois do topo;
- **Junto das informações** — a logo acompanha o bloco de informações;
- **Não mostrar na página** — a página não exibe a logo.

A logo aparece **em destaque, sobre um cartão branco**, para ficar bem legível em qualquer tema e tanto no modo claro quanto no escuro. E se você escolher **Não mostrar na página**, a logo **continua saindo normalmente nos relatórios, e-mails e credenciais** — ela só deixa de aparecer na página do evento. Veja **[Editor de evento → Aparência](/modulos/editor-evento/)**.

## Página do evento em tela cheia (sem cabeçalho e rodapé do site)
**v1.39.0 · julho de 2026**

Quando você escolhe o layout **Página do plugin** (aba **Página** do editor), a página do evento agora aparece em **tela cheia** — um *hotsite* de página única, **sem o cabeçalho e o rodapé do seu tema**. Só o conteúdo do evento, ocupando a tela inteira: uma página de divulgação limpa, que abre focada e vai direto à inscrição.

Se você prefere manter o **cabeçalho e o rodapé do seu site** ao redor do evento, basta usar o layout **Tema do site**. Veja **[Página do evento](/modulos/pagina-do-evento/)**.

## Logos de patrocinadores com melhor contraste
**v1.38.2 · julho de 2026**

Os **logos dos patrocinadores** na página do evento agora aparecem **sempre sobre um fundo branco**, em qualquer tema e também no modo escuro. Antes, no modo escuro, o quadro do patrocinador ficava escuro e logos transparentes (ou feitas para fundo claro) perdiam legibilidade — agora cada logo ganha o seu quadro branco, com bom contraste. Você pode enviar as artes em **PNG com fundo transparente** sem se preocupar. Veja **[Página do evento](/modulos/pagina-do-evento/)**.

## Combine tipos de preço no mesmo evento
**v1.38.0 · julho de 2026**

Agora você pode **combinar tipos de preço** no mesmo evento. A aba **Preços** tem **três chaves independentes**, que você liga como quiser — sozinhas ou juntas:

- **Preço por lote (data)** — o valor muda por janela de data (1º lote, 2º lote…).
- **Preço por modalidade** — cada inscrito paga conforme a categoria escolhida (ex.: Estudante × Profissional).
- **Desconto por quantidade** — o preço por inscrito cai em faixas conforme o número de inscritos.

Dá para usar **qualquer combinação** — por exemplo, lotes por data em que **cada lote** tem preços por modalidade **e** desconto para grupos. Quando o preço é por lote, cada lote ganha o **seu próprio bloco de preços**, e há o botão **Duplicar lote** para copiar tudo e só ajustar as datas e os valores.

Um detalhe importante: o **desconto por quantidade** conta o **total de inscritos do pedido**. Num pedido com 5 Estudantes + 3 Profissionais (8 no total), todos entram na faixa "a partir de 5", cada um pagando o valor dessa faixa na sua categoria. No formulário, quando o preço varia por categoria e/ou quantidade, os valores aparecem como **"Valor base"** e o valor final surge no resumo depois de escolher a categoria e adicionar os participantes.

**Ligar uma chave só funciona igual a antes**, e **eventos que já existiam continuam iguais**, sem reconfigurar nada. Veja **[Editor de evento → Preços](/modulos/editor-evento/)**.

## Nova página do manual: personalizar as telas públicas com CSS
**Manual · julho de 2026**

A pedido de quem usa o plugin, o manual ganhou uma referência de **[Personalizar com CSS](/modulos/personalizar-css/)**: a lista das **classes** e das **variáveis de estilo** que o formulário de inscrição e a página do evento deixam disponíveis. Com ela, quem sabe um pouco de CSS pode ajustar cores, fontes, cantos e espaçamentos pelo **CSS adicional** do tema — ou reaproveitar os elementos em conteúdos com design mais avançado — sem editar o plugin.

## Formulário mais claro e topo da página mais bonito
**v1.36.1–v1.37.0 · julho de 2026**

Vários acertos de usabilidade a partir do uso real:

- **Campos de "escolha" ocupam a linha inteira** — campos do tipo checkbox/opções não ficam mais espremidos ao lado dos campos de texto.
- **Inscrição individual mais enxuta** — quando a inscrição é "só para mim", os botões **"+ Adicionar participante"** e **"× Remover"** somem (não faz sentido ter mais de um). No grupo, o último participante também não pode ser removido.
- **Topo (Hero) sem imagem** — se o evento não tem imagem, o topo aparece no modo **"só texto"** (nome, data e local sobre as cores do evento), em vez de esticar o logo.
- **Toque mais fácil no celular** — checkboxes e botões um pouco maiores.

## Galeria de modelos de página + modo claro/escuro
**v1.36.0 · julho de 2026**

A página do evento (layout "Página do plugin") ganhou uma **galeria de modelos**: agora são **6 estilos com personalidades diferentes** — Moderno, Compacto, **Vibrante** (lúdico), **Clássico** (formal, com serifa), **Minimalista** e **Energia** (esportivo). Cada um tem tipografia, formas e acento próprios, e **as cores continuam vindo do seu evento**. Você escolhe pela galeria, vendo uma prévia de cada um.

E há um novo controle de **Esquema de cor** — **Claro, Escuro** ou **Sistema** (que segue o aparelho de cada visitante) — que vale para todos os modelos, com bom contraste nos dois modos. Veja **[Editor de evento](/modulos/editor-evento/)**.

## Escolha como o topo da página do evento aparece (Hero)
**v1.35.0 · julho de 2026**

Agora você decide, em cada evento, **como o topo (Hero) da página aparece** — na aba **Página** do editor:

- **Só imagem** — mostra a **arte inteira, sem cortar** e sem texto por cima. Perfeito quando a sua arte de divulgação **já traz nome, data e local** — ela aparece legível, inclusive no celular.
- **Imagem + texto** — a arte vira fundo e o plugin escreve título, data e local por cima, com contraste.
- **Só texto** — sem imagem, sobre as cores do evento.

Há também um campo **Imagem do Hero** para escolher a arte do topo. Veja **[Editor de evento](/modulos/editor-evento/)**.

## Campo de múltipla escolha e correções no formulário
**v1.34.0 · julho de 2026**

O campo **checkbox** do formulário agora pode ter **opções** — vira uma **múltipla escolha** (o participante marca mais de uma, ex.: restrições alimentares). E as opções de **escolha** (radio) e das caixas agora ficam **cada uma em sua linha**, sem se encavalar. Veja **[Editor de evento](/modulos/editor-evento/)**.

## E-mails mais limpos na inscrição
**v1.33.0 · julho de 2026**

Ao se inscrever num evento, o participante passa a receber **apenas os e-mails do V3REvent** (confirmação, recibo, credencial) — os e-mails genéricos de "pedido" do WooCommerce deixam de ser enviados nas inscrições, para não confundir.

## API e Webhooks para integrar com outros sistemas
**v1.31.0–v1.32.0 · julho de 2026**

O V3REvent ganhou uma nova tela **Shortcodes e API** com tudo para conectar seus eventos a outros sistemas (como o **n8n**):

- **API de leitura** — gere **chaves de API** (com escopo por evento) para um sistema externo ler eventos, inscrições e inscritos.
- **Webhooks** — o V3REvent **avisa automaticamente** um serviço externo quando algo acontece: inscrição confirmada, check-in, credencial emitida, evento publicado e mais (9 gatilhos). Com botão **Testar**, log de entregas e assinatura de segurança.
- **Shortcodes** — a lista dos shortcodes do plugin, com botão copiar, num lugar só.

Veja **[Shortcodes e API](/modulos/shortcodes-e-api/)**.

## Anexar documentos ao evento (regulamento, kit…)
**v1.30.0 · julho de 2026**

Agora dá para **anexar documentos ao evento** — regulamento, kit do participante, o que precisar — na nova aba **Documentos** do editor. Cada arquivo recebe um **título** e vira um **link de download** na página do evento. Você **reordena** os documentos e escolhe **onde a lista aparece** (antes ou depois da inscrição, após as informações, ou não exibir). Também há o shortcode `[v3revent_documents]` para colocar a lista em qualquer página. Veja **[Editor de evento](/modulos/editor-evento/)**.

## Descrição do evento com editor de formatação
**v1.29.0 · julho de 2026**

A **descrição do evento** (aba Detalhes do editor) agora tem um **editor com formatação** — o mesmo editor do WordPress. Dá para usar **negrito**, listas, títulos, links e citações, alternar entre **Visual** e **Texto (HTML)**, e **inserir imagens** pelo botão **Adicionar mídia**. Tudo isso aparece na página pública do evento. Veja **[Editor de evento](/modulos/editor-evento/)**.

## "Responsável pela inscrição" agora é opcional
**v1.28.0 · julho de 2026**

Antes, o formulário sempre pedia os **Dados do Responsável pela Inscrição** — o que só fazia sentido quando alguém inscrevia um grupo. Agora cada evento tem um **Tipo de inscrição** (aba Detalhes do editor):

- **O participante escolhe** (novo padrão) — o formulário pergunta **"Para quem é esta inscrição?"** e só mostra o responsável quando é para um grupo.
- **Somente individual** — esconde o responsável; o contato é o próprio participante.
- **Sempre em grupo** — mantém o responsável como passo obrigatório (comportamento anterior).

Assim, quem se inscreve sozinho não vê mais um campo que não usava. Veja **[Formulário público](/modulos/formulario-publico/)** e **[Editor de evento](/modulos/editor-evento/)**.

## Botão "Ver página" do evento
**v1.27.0 · julho de 2026**

Ficou muito mais fácil **encontrar e abrir a página pública** de um evento. Agora existe o botão **Ver página** em dois lugares: na tela **Eventos** (na linha de cada evento) e no topo do **editor** do evento. Um clique abre a página pública em uma nova aba — o link que você divulga.

Enquanto o evento está em **rascunho**, o botão vira **Pré-visualizar**: você confere como a página vai ficar antes de publicar, sem que o público veja.

{: .note }
> Lembrete útil: a página do evento é publicada **automaticamente** e **não** aparece no menu **Páginas** do WordPress — o evento é gerido pela tela **V3REvent → Eventos**. Veja **[Página do evento](/modulos/pagina-do-evento/)**.

## Preço por modalidade mais fácil e cores herdadas
**v1.26.0 · julho de 2026**

Três melhorias de usabilidade no **editor de evento**, a partir de sugestões de quem usa o plugin:

- **Preço por modalidade** virou uma opção direta no **Modo de preço** (aba Tabela de Preços), ao lado de "Por quantidade" e "Por lote". Antes era preciso descobrir um campo escondido — agora é só escolher **Por modalidade de inscrição** e apontar o campo do formulário (ex.: "Modalidade": Jovem / Chefe / Equipe), com uma tabela de preços por opção.
- **Cores dos eventos herdam as globais.** As cores definidas em **Configurações → Aparência** agora são o **padrão automático** de todo evento — você só personaliza um evento se quiser. Mudar a cor global atualiza todos os eventos que seguem o padrão.
- **Abas do editor** deixam de quebrar em duas linhas: quando são muitas, a barra **rola na horizontal**, sem esconder nenhuma.

Veja **[Editor de evento](/modulos/editor-evento/)**.

## Preço por lote (data) e data limite de inscrições
**v1.25.0 · julho de 2026**

A **Tabela de Preços** ganhou um **modo de preço**: além do "Por quantidade" (desconto por grupo), agora há **"Por lote (data)"**. Você cadastra lotes com **janela de data** e **preço** — ex.: 1º lote R$ 100, 2º R$ 110, 3º R$ 120 — e o sistema cobra automaticamente o **lote ativo na data da inscrição**, sem precisar trocar o preço na virada. Perfeito para **corridas** e eventos com lotes. Também entrou, na aba **Detalhes**, uma **Data limite de inscrições** (opcional) que **fecha o formulário automaticamente** na data marcada. Veja **[Editor de evento](/modulos/editor-evento/)**.

## Relatório do evento em PDF
**v1.24.0 · julho de 2026**

Ao fechar um evento, você agora emite um **relatório consolidado em PDF**, escolhendo **quais seções incluir e em que ordem**: dados da organização, dados gerais, patrocinadores, programação, inscritos e presença, **valores (previsto × arrecadado)**, avaliação, lições aprendidas, texto livre e equipe. Uma nova aba **Relatório** no editor guarda a configuração; o PDF é **gerado na hora** com os dados atuais e **baixado no painel** (documento interno, sem link público). Também dá para gerá-lo pelo ícone de relatório na lista de eventos. Veja **[No dia e depois](/guia-do-gestor/no-dia-e-depois/)**.

## Patrocinadores do evento
**v1.23.0 · julho de 2026**

Cada evento ganhou uma aba **Patrocinadores** (opcional) para cadastrar patrocinadores e apoiadores: nome, CNPJ/CPF, **logomarca**, site, tipo (patrocínio, apoio, realização, parceria), **valor** (dinheiro ou permuta, com situação previsto/confirmado/recebido) e as **contrapartidas** negociadas. Na **página pública** do evento, os **logos aparecem agrupados por tipo**; os dados financeiros e as contrapartidas ficam só no seu controle. Tudo isso também alimenta o novo **Relatório** do evento. Veja **[Editor de evento](/modulos/editor-evento/)**.

## Certificado de participação
**v1.22.0 · julho de 2026**

Chegou o **certificado de participação**: uma nova aba **Certificado** no editor, com modelos prontos (Clássico e Moderno) na logo e nas cores do evento, carga horária opcional e **envio por e-mail** aos elegíveis. Quem é elegível depende da **modalidade** do evento — em **presencial**, quem fez **check-in**; em **virtual**, quem tem inscrição confirmada. Cada certificado tem um **link público de verificação** e versão em PDF. Veja **[Documentos](/modulos/documentos/)**.

## Ações da lista de eventos mais limpas
**v1.21.0 · julho de 2026**

Na tela **Eventos**, os botões **Editar** e **Duplicar** viraram **ícones** (lápis e cópia) com uma **dica ao passar o mouse**, deixando a lista mais enxuta e fácil de ler. O comportamento é o mesmo — e agora também totalmente acessível pelo teclado. Veja **[Eventos](/modulos/eventos/)**.

## Avaliação do evento
**v1.20.0 · julho de 2026**

Chegou a **pesquisa de avaliação** do evento — uma nova aba **Avaliação** no editor, com quatro áreas:

- **Perguntas** — monte a pesquisa com tipos prontos: **nota (1–5)**, **NPS (0–10)**, escolha única, múltipla escolha e texto livre.
- **Convites** — envie o convite da pesquisa por e-mail **aos presentes** (com a opção de mandar só para quem ainda não respondeu).
- **Resultados** — veja os números **de forma anônima**: score NPS, médias das notas, distribuição das escolhas, comentários e a taxa de resposta.
- **Retrospectiva** — registre as suas **lições aprendidas** como coordenador.

A pesquisa é **anônima e respondida pelos participantes que fizeram check-in**: cada um recebe um link próprio, responde sem precisar de login, e a resposta **não fica vinculada à pessoa** — só o fato de ter respondido é registrado (para não duplicar e calcular a taxa de resposta). Veja **[No dia e depois](/guia-do-gestor/no-dia-e-depois/)**.

## Exportar a lista de presentes
**v1.19.0 · julho de 2026** *(coluna de horário de check-in a partir da v1.20.1)*

Na tela **Relatórios**, além de **Exportar todos**, agora há **Exportar presentes** — um arquivo (CSV, XLSX ou PDF) só com quem realmente compareceu (fez check-in). A partir da **v1.20.1**, esse arquivo traz também uma coluna **Check-in** com o **horário** de presença de cada pessoa. Ideal para enviar a pesquisa de avaliação a quem participou, emitir declarações ou ações de fidelização. Veja **[Relatórios](/modulos/relatorios/)**.

## Ordem das abas do editor mais natural
**v1.18.0 · julho de 2026**

As abas do editor de evento foram reordenadas para acompanhar o fluxo real de trabalho: **Detalhes → Programação → Campos do Formulário → Tabela de Preços → Aparência → Página → Credencial → WooCommerce → Equipe**.

## Check-in por QR e credenciamento
**v1.16.0 · julho de 2026**

Chegou o **check-in**: escaneie o QR da credencial (pela tela **Check-in** no painel ou pela própria página da credencial no celular) e a presença é marcada na hora, com retorno colorido — verde para confirmado, amarelo para quem já havia entrado, vermelho para código inválido. É reversível e não duplica presença. Os **Relatórios** ganharam a coluna de **Presença**. Veja **[Check-in](/modulos/checkin/)**.

## Credencial com QR e networking consentido
**v1.14.0 · julho de 2026**

Cada participante confirmado ganha uma **credencial** (crachá) com a logo e as cores do evento, em três modelos. O **QR** carrega, por padrão, apenas o código de validação; com o consentimento de **networking** do participante, passa a carregar um **cartão de contato (vCard)** para facilitar conexões — sempre preservando o código para o check-in. Dá para enviar a credencial automaticamente e gerar em lote para impressão. Veja **[Documentos](/modulos/documentos/)**.

## Suporte ao CNPJ alfanumérico
**v1.15.0 · julho de 2026**

O perfil da organização passou a aceitar o **novo CNPJ alfanumérico** da Receita Federal (ex.: `12.ABC.345/01DE-35`), com validação do dígito verificador. O CNPJ numérico continua funcionando exatamente como antes.

## Recibo automático em PDF
**v1.13.0 · julho de 2026**

Ao concluir o pedido, o responsável (pagador) recebe por e-mail um **recibo em PDF** na identidade do evento e da organização, com um **link permanente** para reemissão a qualquer momento. O recibo é um comprovante de pagamento — não substitui a nota fiscal.

## Páginas de evento por temas e compartilhamento
**v1.11.0 · julho de 2026**

Um **motor de páginas de evento** permite publicar o evento como uma **página inteira temática** (hero, informações, programação e formulário de inscrição), com botões de **compartilhamento** em redes sociais e no WhatsApp. Veja **[Página do evento](/modulos/pagina-do-evento/)**.

## Programação e galeria de imagens
**v1.9.0 – v1.10.0 · julho de 2026**

Cadastre a **programação** do evento (sessões, horários, palestrantes, trilhas) e uma **galeria de imagens** — ambos aparecem na página pública e nos blocos disponíveis.

## Precificação por modalidade
**v1.8.0 · julho de 2026**

Além do preço por faixa de quantidade, o evento pode ter um **campo de preço** (ex.: "Modalidade") em que **cada opção tem a sua própria tabela de faixas**. O total é a soma por modalidade.

## RBAC: três papéis de acesso
**v1.0.0 · julho de 2026**

O acesso passou a ser controlado por **três papéis** — Administrador da Organização, Coordenador de Eventos e Equipe de Evento —, cada um com o alcance certo. Você designa coordenadores e equipe **por evento**, na aba **Equipe**. Veja **[Primeiros passos](/primeiros-passos/)**.

## Feedback e manual no cabeçalho
**v0.8.0 · julho de 2026**

No cabeçalho de qualquer tela há dois botões: **Manual do Usuário** (abre este manual) e **Enviar Feedback**, para mandar sugestões, dúvidas ou relatos de bug à equipe V3RTECH sem sair do plugin — com um diagnóstico técnico automático que acelera o suporte, e sem expor seus dados sensíveis. Veja **[Ajuda e Feedback](/modulos/ajuda-e-feedback/)**.

---

## Recursos consolidados
*A base do V3REvent, presente desde as primeiras versões.*

### Eventos configuráveis por painel
Cada evento tem datas, local, capacidade, **faixas de preço**, **campos de formulário** (10 tipos), aparência (logo e cores) e produto no WooCommerce criado automaticamente ao publicar.

### Inscrição em lote com preço ao vivo
O responsável inscreve um grupo num único pedido, adiciona participantes à mão ou **importando uma planilha** (CSV/XLSX), e vê o **preço recalculado ao vivo** conforme a quantidade, com a faixa ativa em destaque.

### Pagamento pelo WooCommerce
A inscrição usa o carrinho, o checkout e os meios de pagamento do WooCommerce, com o preço sobrescrito pelas faixas do evento. Compatível com o armazenamento moderno de pedidos (HPOS).

### Comunicação automática
Cada participante recebe um e-mail de confirmação com o **código de inscrição**; o responsável recebe um relatório. Os e-mails são enviados em fila, para não travar o checkout em listas grandes.

### Relatórios e exportação
Painel com indicadores e gráficos, lista de inscrições com filtros e mudança de status, e relatórios por evento com colunas dinâmicas. Exportação em **CSV, XLSX e PDF**.

### LGPD por padrão
Consentimento obrigatório no formulário, **retenção** configurável com expurgo automático, e ferramentas para atender aos **direitos do titular** (exportar, excluir/anonimizar).
