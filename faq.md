---
title: Perguntas Frequentes
nav_order: 6
---

# Perguntas Frequentes

## Começando

<details markdown="1">
<summary>Onde encontro o V3REvent depois de instalar?</summary>

No menu lateral do painel do WordPress, procure o item **V3REvent**. Ele reúne o
Painel, Eventos, Inscrições, Relatórios, Check-in e Configurações. Veja
**[Primeiros passos](/primeiros-passos/)**.
</details>

<details markdown="1">
<summary>Criei o evento, mas não encontro a página dele. Onde ela fica?</summary>

A página do evento é **criada automaticamente** quando você **publica** o evento — no endereço `.../evento/nome-do-evento/`. Você **não precisa criá-la** nem colar shortcode.

Ela **não aparece** no menu **Páginas** do WordPress porque o evento é um conteúdo próprio do V3REvent (gerido em **V3REvent → Eventos**), e não uma "Página" comum — isso é o esperado. Para abrir a página, use o botão **Ver página**: na lista de **Eventos**, na linha do evento, ou no topo do **editor** do evento. Se o evento ainda está em **rascunho**, o botão vira **Pré-visualizar** (só você vê). Detalhes em **[Página do evento](/modulos/pagina-do-evento/)**.
</details>

<details markdown="1">
<summary>Preciso do WooCommerce?</summary>

Sim. O V3REvent usa o **WooCommerce** para o carrinho, o checkout e o pagamento
das inscrições. Ele precisa estar instalado e ativo. Eventos **gratuitos**
funcionam: basta configurar o preço como R$ 0 — o pedido passa pelo WooCommerce
mesmo assim.
</details>

<details markdown="1">
<summary>Preciso de conta na nuvem ou mensalidade de plataforma?</summary>

Não. O V3REvent é um plugin que roda no **seu próprio WordPress**. Os dados ficam
no seu servidor e você trabalha inteiramente dentro do `wp-admin`.
</details>

<details markdown="1">
<summary>Qual é a primeira coisa que devo configurar?</summary>

O **perfil da organização** (V3REvent → Configurações → Organização): nome, CNPJ,
endereço, contato e logo. Ele alimenta recibos, credenciais e e-mails de todos os
eventos. Passo a passo em **[Primeiros passos](/primeiros-passos/)**.
</details>

<details markdown="1">
<summary>Preciso dar acesso ao painel do WordPress para minha equipe?</summary>

Não. Publique uma página comum do site com o shortcode `[v3revent_gestao]` e
compartilhe o link com quem tem papel em algum evento — a pessoa gerencia
Painel, Eventos, Inscrições, Check-in e Relatórios por ali, com login próprio,
sem nunca entrar no `wp-admin`. Veja **[Gestão pelo site](/modulos/gestao-pelo-site/)**.
</details>

<details markdown="1">
<summary>Por que minha equipe não vê todos os eventos?</summary>

Porque o acesso é **por evento**, não geral. Só o **Administrador da
Organização** vê todos os eventos; um **Coordenador de Eventos** ou membro da
**Equipe de Evento** só enxerga (e só exporta dados de) os eventos em que foi
designado — vale tanto no painel quanto na **[página de gestão do
site](/modulos/gestao-pelo-site/)**. Para dar acesso a outro evento, adicione a
pessoa na aba **Equipe** do editor daquele evento. Veja **[Primeiros
passos](/primeiros-passos/#4-entender-os-papéis-de-acesso)**.
</details>

## Inscrições e preços

<details markdown="1">
<summary>Meu evento é individual — como tiro o campo "Responsável pela inscrição"?</summary>

No editor do evento, aba **Detalhes**, use o **Tipo de inscrição**. Escolha **"Somente individual"** para esconder de vez a seção do responsável, ou **"O participante escolhe"** (padrão) para que o formulário pergunte "Para quem é esta inscrição?" e só mostre o responsável quando for para um grupo. Em inscrições individuais, o contato passa a ser o próprio participante (nome/e-mail do checkout). Detalhes em **[Formulário público](/modulos/formulario-publico/)**.
</details>

<details markdown="1">
<summary>Como funciona o preço por faixa de quantidade?</summary>

Ligue **Desconto por quantidade** na aba **Preços** do evento: cada faixa tem uma
quantidade mínima, máxima e um preço por inscrito. Quanto maior o grupo, menor o
valor unitário. A faixa é destravada pelo **total de inscritos do pedido** (mesmo
misturando modalidades), e o formulário mostra a faixa ativa em destaque e recalcula
o total ao vivo. Veja **[Criar um evento](/criar-evento/)**.
</details>

<details markdown="1">
<summary>Posso ter preços diferentes por tipo de participante?</summary>

Sim. Ligue **Preço por modalidade** na aba **Preços**: designe um campo de seleção
(ex.: "Estudante" / "Profissional") como campo de preço, e dê a **cada opção sua
própria tabela**. O total é a soma por modalidade — e você ainda pode **combinar**
com lotes por data e desconto por quantidade. Veja
**[Editor de evento → Preços](/modulos/editor-evento/)**.
</details>

<details markdown="1">
<summary>Como o responsável inscreve muita gente sem digitar um a um?</summary>

Pelo botão de **importar planilha** no formulário: ele baixa um modelo, preenche em
CSV/XLSX e importa — os cards de participante são preenchidos automaticamente. Veja
**[Formulário público](/modulos/formulario-publico/)**.
</details>

<details markdown="1">
<summary>O que acontece quando o evento lota?</summary>

O formulário **não bloqueia**: avisa que a inscrição entrará como **excedente** e
deixa prosseguir. Na lista de inscrições, os excedentes ficam sinalizados. Para
fechar de vez, desligue **Inscrições abertas** na aba Detalhes do evento.
</details>

<details markdown="1">
<summary>Posso fechar as inscrições no meio do dia?</summary>

Sim. A **Data limite de inscrições** (aba Detalhes) e o **início/fim de cada lote**
(aba Preços) aceitam **data e hora**, não só data — informe o horário exato em que
quer encerrar (ex.: meio-dia de sexta) em vez de esperar o fim do dia. Se você não
informar hora nenhuma, o comportamento continua o de sempre: o limite vale até o
**fim do dia** (23:59). Veja **[Editor de evento → Detalhes](/modulos/editor-evento/#detalhes)**.
</details>

<details markdown="1">
<summary>Por que meu formulário diz que as inscrições estão fechadas se ainda tem lote?</summary>

Provavelmente há um **buraco entre dois lotes**: se o 1º lote termina às 12:00 e o
2º só começa às 14:00, entre 12:01 e 13:59 **nenhum lote está vigente** e o
formulário não aceita inscrição — mesmo com o evento publicado. Abra a aba
**Preços** do evento e confira se o fim de cada lote encosta no início do
seguinte; ao criar um lote novo, o início já vem sugerido como o minuto seguinte
ao fim do anterior, e o editor avisa quando percebe um buraco ou uma sobreposição.
Veja **[Editor de evento → Preço por lote](/modulos/editor-evento/#preço-por-lote-data)**.
</details>

<details markdown="1">
<summary>O formulário sugeriu corrigir o e-mail de um participante com domínio próprio (empresa, universidade). Isso vai impedir a inscrição?</summary>

Não. A sugestão de correção de e-mail é só um alerta — a pessoa pode ignorá-la e
seguir com o que digitou, mesmo que o domínio seja incomum ou pouco usado. O
formulário nunca recusa a inscrição por causa dela; só a validação normal de
formato de e-mail continua valendo. Veja
**[Formulário público → Sugestão de correção de e-mail](/modulos/formulario-publico/#sugestão-de-correção-de-e-mail)**.
</details>

## Pagamento e documentos

<details markdown="1">
<summary>O V3REvent recebe o dinheiro das inscrições?</summary>

Não. Quem processa o pagamento é o **WooCommerce** com o gateway que você
configurou. A V3RTECH não recebe, não intermedia e não retém valores. A relação de
compra é entre você (organizador) e o inscrito.
</details>

<details markdown="1">
<summary>Minha receita total caiu depois de atualizar o plugin — é um erro?</summary>

Provavelmente não. A partir da v1.69.0 (agosto/2026), o valor de cada inscrição
passou a ser o **efetivamente cobrado no pedido** — com cupom de desconto já
descontado — em vez de recalculado pelo preço cheio do evento. Se você usava
cupons, o total antigo estava **inflado**; o número menor que você vê agora é a
correção, não uma perda real. Inscrições feitas antes da atualização continuam
pelo valor de tabela da época (sem correção retroativa) e aparecem identificadas
numa nota junto do total. Veja **[Descontos com cupom](/guia-do-gestor/descontos-com-cupom/)**.
</details>

<details markdown="1">
<summary>O recibo do V3REvent é nota fiscal?</summary>

Não. O recibo é um **comprovante de pagamento** com a identidade do evento e os
dados da organização. A emissão de **nota fiscal**, quando exigível, é uma
obrigação sua, feita à parte. Veja **[Documentos](/modulos/documentos/)**.
</details>

<details markdown="1">
<summary>O participante recebe alguma confirmação?</summary>

Sim. Ao concluir o pedido, cada participante recebe um e-mail de confirmação com o
seu **código de inscrição** único, e o responsável recebe um relatório e o
**recibo em PDF**. Se você habilitar, a **credencial** também é enviada
automaticamente.
</details>

<details markdown="1">
<summary>Um participante diz que não recebeu o e-mail de confirmação. O que eu faço?</summary>

A partir da v1.79.0, a primeira resposta é indicar a **[Área do
Inscrito](/modulos/area-do-inscrito/)**: a pessoa informa lá o e-mail usado na
inscrição e recebe sozinha um link de acesso, sem depender de você. Se preferir
resolver você mesmo, peça para conferir a caixa de spam primeiro; não achando, vá
em **Inscrições**, encontre o participante e clique em **Reenviar confirmação** —
funciona para qualquer inscrição já **confirmada**. Se a linha mostrar a etiqueta
**"Em nova tentativa"**, não reenvie: o próprio sistema já está tentando de novo
sozinho, e o botão fica temporariamente desabilitado por causa disso. Veja
**[Inscrições → Reenviar a confirmação de inscrição](/modulos/inscricoes/#reenviar-a-confirmação-de-inscrição)**.
</details>

<details markdown="1">
<summary>Reenviei a confirmação para várias pessoas e a tela avisou que o envio seria "gradual". Travou?</summary>

Não. Em envios grandes, o V3REvent manda as mensagens aos poucos (por padrão, 100 a
cada 5 minutos) para não sobrecarregar o servidor de e-mail do site — a própria
tela mostra quantos lotes ainda faltam enquanto isso roda. É esperado que um envio
para centenas de pessoas leve alguns minutos ou mais; a confirmação, antes de você
disparar, já avisa a duração estimada.
</details>

## Área do Inscrito

<details markdown="1">
<summary>Um participante pediu o link de acesso e disse que "não chegou nada" — mas eu vejo o e-mail dele cadastrado. O que houve?</summary>

Confira se o e-mail digitado na Área do Inscrito é **exatamente** o mesmo usado na
inscrição. A tela responde a mesma mensagem de sucesso tanto para e-mail
cadastrado quanto para não cadastrado — de propósito, para que a página não vire
um jeito de descobrir quem está inscrito no seu evento — então "recebi a mensagem
e nada chegou" quase sempre significa e-mail diferente, não falha de envio. Peça
para a pessoa conferir com quem fez a inscrição dela (às vezes é outra pessoa, o
responsável do grupo) e tentar de novo. Veja **[Área do
Inscrito](/modulos/area-do-inscrito/)**.
</details>

<details markdown="1">
<summary>Por que a Área do Inscrito não mostra os colegas de um participante, só o dele?</summary>

Depende de quem é o dono do e-mail usado para acessar. Quem **fez a inscrição**
(pagou, inclusive de um grupo inteiro) vê o comprovante e a credencial/certificado
de **todos** os participantes daquele pedido. Quem **só participa** — foi incluído
num grupo que outra pessoa comprou — vê **apenas a própria** credencial e
certificado, nunca os colegas, o comprovante ou o **código da inscrição** (é a
chave que abre o comprovante, então some junto). Não é uma limitação a corrigir:
é para que o valor pago e os dados dos colegas não fiquem visíveis a quem não
pagou. Veja **[Área do Inscrito](/modulos/area-do-inscrito/)**.
</details>

<details markdown="1">
<summary>O link de acesso enviado por e-mail expirou. O participante perdeu o acesso?</summary>

Não — ele só precisa pedir um novo, na mesma página. O link vale **24 horas** e
serve **uma única vez**; passado esse prazo (ou depois de aberto), a própria tela
mostra o aviso e já traz o campo para solicitar outro. Veja **[Área do
Inscrito](/modulos/area-do-inscrito/)**.
</details>

<details markdown="1">
<summary>Preciso criar a página da Área do Inscrito?</summary>

Não. Ela é criada automaticamente na atualização para a v1.79.0 — procure por
"Área do inscrito" em **Páginas**. Só use o shortcode `[v3revent_area_inscrito]`
se quiser montá-la em outro endereço ou com outro visual. Vale divulgar o link no
rodapé dos e-mails e no site: a página só ajuda quem sabe que ela existe. Veja
**[Área do Inscrito](/modulos/area-do-inscrito/)**.
</details>

## Credencial e check-in

<details markdown="1">
<summary>O que é o QR da credencial e o "networking consentido"?</summary>

Cada credencial tem um **QR**. Por padrão, ele aponta só para a página de validação
(usada no check-in). Se o participante **consentir com o networking** (uma opção no
formulário), o QR passa a carregar um **cartão de contato (vCard)** com nome,
e-mail, telefone e empresa — mantendo o código para o check-in. Veja
**[Documentos](/modulos/documentos/)**.
</details>

<details markdown="1">
<summary>Como faço o check-in no dia do evento?</summary>

Pela tela **Check-in** (leitor de QR por câmera ou entrada manual do código) ou
abrindo a credencial pelo celular, onde a equipe logada vê um botão de **Confirmar
presença**. O check-in é reversível e não duplica presença. Quem faz é a **Equipe
de Evento**. Veja **[Check-in](/modulos/checkin/)**.
</details>

<details markdown="1">
<summary>Meu evento não precisa de crachá. Dá para desligar a credencial?</summary>

Sim, desde a v1.79.0. Na aba **Credencial** do editor de evento, desligue
**Oferecer credencial para este evento** — ela deixa de existir por completo para
aquele evento: some da Área do Inscrito, o link público para de responder e ela
não sai mais anexada no e-mail. Todo evento nasce com o controle **ligado**, então
nada muda se você não mexer. Veja **[Editor de evento →
Credencial](/modulos/editor-evento/#credencial)**.
</details>

<details markdown="1">
<summary>Um voluntário pode fazer só o credenciamento, sem acesso ao resto?</summary>

Sim. Adicione-o como **Equipe de Evento** na aba **Equipe** daquele evento. Ele
poderá acompanhar inscrições e fazer check-in, mas não alterará a configuração do
evento nem verá outros eventos ou as Configurações globais.
</details>

## Pós-evento: certificado, avaliação e relatório

<details markdown="1">
<summary>Quem recebe o certificado de participação?</summary>

Depende da **modalidade** do evento (aba Detalhes): em evento **presencial**, é
elegível quem fez **check-in**; em **virtual**, quem tem a inscrição confirmada.
Você ativa a emissão, escolhe o modelo e a carga horária na aba **Certificado** e
envia por e-mail aos elegíveis. Cada certificado tem um **link público de
verificação**. Veja **[Documentos](/modulos/documentos/)**.
</details>

<details markdown="1">
<summary>Os valores e as contrapartidas dos patrocinadores aparecem para o público?</summary>

Não. Na **página pública** do evento aparecem apenas o **logo, o nome e o tipo** do
patrocinador (agrupados por tipo). O **valor**, a **situação** e as
**contrapartidas** ficam só no painel e no **relatório do evento** — que é interno.
Veja **[Editor de evento](/modulos/editor-evento/)**.
</details>

<details markdown="1">
<summary>Qual a diferença entre a tela "Relatórios" e o "Relatório do evento"?</summary>

A tela **Relatórios** é de **acompanhamento e exportação** dos participantes
(indicadores, presença, CSV/XLSX/PDF). O **Relatório do evento** (aba **Relatório**
do editor) é um **PDF consolidado de fechamento**, com seções escolhíveis —
organização, patrocinadores, valores (previsto × arrecadado), avaliação, equipe e
mais. É gerado sob demanda e restrito ao painel.
</details>

<details markdown="1">
<summary>A pesquisa de avaliação é anônima?</summary>

Sim. Ela é liberada apenas para quem **fez check-in**, cada um responde por um link
próprio **sem login**, e a resposta **não fica vinculada à pessoa** — só o fato de
ter respondido é registrado (para não duplicar e calcular a taxa de resposta). Veja
**[No dia e depois](/guia-do-gestor/no-dia-e-depois/)**.
</details>

## Integração com outros sistemas

<details markdown="1">
<summary>Como integro o V3REvent com o n8n ou outro sistema?</summary>

Pela tela **Shortcodes e API**. Há dois caminhos: uma **API de leitura** (o outro sistema
usa uma **chave de API** para consultar eventos, inscrições e inscritos) e **webhooks** (o
V3REvent **avisa** o outro sistema quando algo acontece — inscrição confirmada, check-in
etc.). Passo a passo em **[Shortcodes e API](/modulos/shortcodes-e-api/)**.
</details>

## Dados e privacidade

<details markdown="1">
<summary>De quem é a responsabilidade pelos dados dos inscritos?</summary>

Sua. Ao coletar dados de participantes, **você é o controlador** pela LGPD. O
V3REvent oferece as ferramentas (consentimento no formulário, retenção com expurgo
automático, exportação e exclusão), mas a base legal e a política de privacidade
são sua responsabilidade. Veja **[Política de Privacidade](/legal/privacidade/)**.
</details>

<details markdown="1">
<summary>Por quanto tempo os dados ficam guardados?</summary>

Pelo prazo de **retenção** que você definir em Configurações → Avançado. Passada a
janela, os dados de inscritos de eventos encerrados são **expurgados
automaticamente**. Você também pode excluir uma inscrição manualmente a qualquer
momento.
</details>

<details markdown="1">
<summary>Como envio uma sugestão ou reporto um problema?</summary>

Use o botão **Enviar Feedback** no canto superior direito de qualquer tela do
V3REvent. Escolha o tipo (Sugestão, Dúvida, Bug, Depoimento ou Outros), escreva sua
mensagem e envie — um diagnóstico técnico (sem dados pessoais) vai junto para
acelerar o suporte, e você recebe uma cópia por e-mail. Veja
**[Ajuda e Feedback](/modulos/ajuda-e-feedback/)**.
</details>
