---
title: Área do Inscrito
parent: Módulos
nav_order: 16
---

# Área do Inscrito

A **Área do Inscrito** é uma página pública onde qualquer pessoa que já se inscreveu em algum evento seu consegue, sozinha, informar o e-mail, receber um link de acesso e enxergar as próprias inscrições — com o comprovante, a credencial e o certificado, quando cada um já estiver disponível. Ela existe para o caso mais comum de chamado de suporte: *"perdi o e-mail de confirmação, e agora?"*

{: .note }
> **A página é criada sozinha na atualização** para a v1.79.0 — procure por "Área do inscrito" em **Páginas** do WordPress. Se preferir montá-la em outro endereço (ou reconstruir o visual com o construtor de página do seu tema), use o shortcode `[v3revent_area_inscrito]` — veja **[Shortcodes e API](/modulos/shortcodes-e-api/)**.

## Por que isto importa

Antes da v1.79.0, um inscrito que perdia o e-mail de confirmação só tinha um caminho: escrever para a organização e esperar alguém localizar a inscrição e reenviar os dados manualmente. Em evento grande, isso vira uma fila de pedidos repetitivos na sua caixa de entrada, sempre pela mesma coisa.

Com a Área do Inscrito, a pessoa resolve isso sozinha, a qualquer hora, sem depender de ninguém do seu time estar disponível — e você só entra no fluxo quando o problema for outro (pagamento não identificado, dado errado no formulário etc.).

## Como funciona, para você mostrar ao seu público

1. A pessoa acessa a página e digita o e-mail que usou na inscrição.
2. Ela recebe um e-mail com um link de acesso.
3. Ao abrir o link, vê as inscrições associadas àquele e-mail — com comprovante, credenciais e certificados, cada um só quando já disponível.

![Tela para solicitar o link de acesso](/assets/screenshots/area-inscrito-solicitar-link.png)

{: .tip }
> **Divulgue o endereço.** A página só ajuda quem sabe que ela existe. Vale colocar o link no rodapé dos seus e-mails de confirmação, no site do evento e na página "Fale conosco" — é o tipo de recurso que ninguém procura, mas todo mundo usa quando encontra.

## O que a pessoa vê

O que aparece depende de **como ela participou** daquela inscrição — o sistema reconhece dois papéis possíveis para o mesmo e-mail, e nunca mistura os dois:

- **Quem fez a inscrição (o responsável/pagador)** — inclusive quando inscreveu um grupo inteiro num único pedido — vê **o comprovante do pagamento** e a **credencial e o certificado de todos os participantes daquele pedido**, os dela e os dos colegas.
- **Quem só participa** — foi incluído num grupo que outra pessoa comprou e pagou — vê **apenas a própria credencial e o próprio certificado**. Não vê os colegas de grupo, nem o comprovante, **nem o código da inscrição** — o código some junto porque é ele que abre o comprovante para quem o tem em mãos.

![Área do inscrito para quem fez a inscrição de um grupo — vê o comprovante e a credencial de todos os participantes](/assets/screenshots/area-inscrito-responsavel-grupo.png)

![Área do inscrito para quem só participa — vê apenas a própria credencial](/assets/screenshots/area-inscrito-participante.png)

Uma inscrição **aguardando pagamento** aparece marcada como tal, sem documentos (eles só existem depois da confirmação); uma inscrição **cancelada** simplesmente não aparece.

{: .important }
> **A página não cria nenhuma permissão nova.** Ela só mostra, a quem já tinha aquele e-mail numa inscrição, o que já estava disponível para aquele e-mail — comprovante, credencial e certificado seguiam existindo antes, só não havia um lugar único para reencontrá-los.

## Por que a resposta é sempre a mesma

Peça o link para um e-mail que existe na base ou para um que nunca se inscreveu em nada: a tela mostra **exatamente a mesma mensagem** nos dois casos.

![Mensagem de confirmação — a mesma para e-mail cadastrado ou não](/assets/screenshots/area-inscrito-link-enviado.png)

Isso é proposital, não uma limitação: se a resposta variasse ("e-mail não encontrado" vs. "link enviado"), qualquer pessoa poderia usar a própria página para descobrir, testando e-mail por e-mail, quem está inscrito no seu evento — um vazamento de dado pessoal por um canal que deveria só ajudar quem já é participante. Some a isso um limite de quantos pedidos de link a mesma origem pode fazer por hora, para que ninguém use a página para disparar e-mails em massa.

**Na prática, para quem responde dúvida de participante:** se a pessoa diz "recebi a mesma mensagem de sempre e o e-mail não chegou", a explicação mais provável, de longe, é que o e-mail digitado **não é o mesmo usado na inscrição** — um erro de digitação, um e-mail alternativo, ou a inscrição foi feita por outra pessoa (o responsável do grupo). Peça para ela conferir com quem organizou a inscrição, ou tentar outro e-mail que costuma usar.

## O link expira e só serve uma vez

- **Validade: 24 horas** a partir do envio.
- **Uso único**: depois de aberto, o mesmo link não abre de novo — é preciso pedir outro.

Isso é o que mantém o acesso seguro mesmo que o e-mail de confirmação seja encaminhado, fique salvo numa caixa de entrada compartilhada, ou vaze de alguma forma: o link só vale pela primeira janela de uso.

![Aviso de link expirado ou já usado](/assets/screenshots/area-inscrito-link-invalido.png)

{: .note }
> Passado o prazo (ou depois de usado), a própria tela mostra o aviso acima e já traz o campo para pedir um novo link — não é preciso voltar ao e-mail original nem procurar outra página.

## Quando dá errado

| O que a pessoa vê | O que significa | O que fazer |
|---|---|---|
| A mesma mensagem de sempre, mas o e-mail nunca chega | O e-mail digitado não é o mesmo usado na inscrição (ver acima) | Confira o e-mail exato da inscrição, ou tente outro que costuma usar; confira também a caixa de spam |
| "Este link não é mais válido — ele já foi usado ou não existe" | Passaram 24h, o link já foi aberto antes, ou o endereço foi digitado/colado errado | Peça um novo link na mesma tela |
| A área abre, mas sem credencial ou sem certificado para um evento | O organizador ainda não habilitou aquele documento para o evento, ou a pessoa ainda não é elegível (ex.: certificado depende de check-in em evento presencial) | Confirme com a organização se aquele documento está previsto para o evento |

## Limites de quem administra

Quem gerencia o evento **não vê nem monta nada** a partir desta tela — ela não aparece no painel administrativo, é inteiramente pública e voltada ao inscrito. O que a organização controla é se cada evento **oferece credencial** (aba **Credencial** do evento — veja **[Editor de evento](/modulos/editor-evento/)**) e se **emite certificado** (aba **Certificado**); a Área do Inscrito só reflete essas decisões, não as substitui.

## Privacidade

- A página é marcada como **não indexável** para buscadores (ela lida com dado pessoal, então não deve aparecer em busca).
- Um pedido de exclusão de dados (LGPD) apaga também os links de acesso daquele e-mail, mesmo que a pessoa nunca tenha se inscrito em nada.
- O e-mail de acesso sai com um texto pronto; diferente dos demais e-mails automáticos do plugin, ele **ainda não pode ser personalizado** por você — veja **[Configurações → E-mails](/modulos/configuracoes/)**.
