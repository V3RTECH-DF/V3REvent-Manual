---
title: 'Documentos: recibo, comprovante, credencial e certificado'
parent: Módulos
nav_order: 10
---

# Documentos: recibo, comprovante, credencial e certificado

O V3REvent gera documentos automáticos a partir de um evento: o **recibo** (para o pagador), o **comprovante individual de inscrição** (para cada participante confirmado), a **credencial** (para cada participante, quando o evento oferece) e o **certificado de participação** (para quem é elegível). Todos usam a identidade do evento e os dados da organização, e têm um **link público por código** — imprimível e com versão em PDF.

{: .tip }
> **Quem perdeu o link de um documento não precisa pedir para você reenviar.** A **[Área do Inscrito](/modulos/area-do-inscrito/)** deixa qualquer inscrito reencontrar sozinho, a partir do e-mail usado na inscrição, os documentos que já estão disponíveis para ele: o **comprovante** (todo participante confirmado), o **recibo** (só o responsável pela inscrição), e a credencial e o certificado, quando o evento os oferecer.

## Recibo

Ao concluir o pedido, o **responsável (pagador)** recebe por e-mail um **recibo em PDF** com:

- o logo e as cores (do evento, com recuo para a organização e, por fim, o V3REvent);
- os **dados da organização** (nome, CNPJ, endereço);
- o **evento**, a **lista de inscritos** (nome e modalidade), a **quantidade**, o **valor por inscrito e o total pago**, o **número do pedido** e um **código de recibo**;
- um selo **PAGO**.

![Recibo público do evento](/assets/screenshots/recibo-publico.png)

O e-mail traz também um **link permanente** para reemissão (`recibo/{código}`): a versão em tela é imprimível, e é possível baixar o PDF a qualquer momento.

{: .important }
> **Recibo não é nota fiscal.** O recibo é um **comprovante de pagamento** de uso interno. A emissão de documento fiscal, quando exigível, é obrigação do organizador, feita à parte.

## Comprovante

Cada **participante confirmado** — pague ele a inscrição ou não — tem um **comprovante individual de inscrição** próprio, com uma página no celular e uma versão em **PDF** para baixar ou imprimir: nome, código, evento, data, local e situação. Nenhuma outra resposta do formulário aparece — nem a modalidade, que em alguns eventos é dado sensível (por exemplo, quando a opção de preço é "pessoa com deficiência").

<!-- Captura pendente (#174): ![Comprovante público de inscrição](/assets/screenshots/comprovante-publico.png) -->

### Por que isto importa

O recibo é do **responsável** (quem pagou) e mostra o valor e os dados de quem pagou — por isso não deveria circular com cada participante do grupo. O comprovante resolve o outro lado: a prova de que a própria inscrição está confirmada, sem nenhum dado que não seja da própria pessoa.

{: .important }
> **O comprovante não mostra valor pago, dados de quem pagou nem os nomes dos outros participantes do grupo.** É por isso que pode ser mandado com segurança a qualquer participante, mesmo quando quem pagou a inscrição foi outra pessoa — uma empresa inscrevendo a equipe, um responsável inscrevendo a família.

Ele também é o que garante que **todo evento tem algum documento para entregar ao participante**, mesmo os que **não emitem credencial** (veja a nota sobre o controle **Oferecer credencial** mais abaixo): antes do comprovante, um participante de um evento sem credencial e que não era o responsável do pedido não tinha nenhum documento próprio para mostrar.

### Como o comprovante chega ao participante

Três caminhos, para situações diferentes:

- **Área do Inscrito.** O próprio participante (ou o responsável, por ele) entra com o e-mail usado na inscrição e clica em **Comprovante** — veja **[Área do Inscrito](/modulos/area-do-inscrito/)**.
- **E-mail.** O e-mail de confirmação que cada participante já recebe leva o link do comprovante. Pela **[lista de Inscrições](/modulos/inscricoes/#reenviar-a-confirmação-de-inscrição)**, o ícone de **envelope** reenvia esse e-mail — inclusive em lote.
- **Link para colar numa conversa (WhatsApp, etc.).** Na lista de **[Inscrições](/modulos/inscricoes/)**, o ícone de **link em cadeia** copia um link que abre o comprovante **sem exigir login** — pronto para colar direto na conversa com o participante. Disponível para quem coordena o evento e para a administração; **sem versão em lote**, de propósito, porque é para uma pessoa de cada vez.

{: .warning }
> **O link é longo e não dá para adivinhar — mas continua sendo um link que qualquer um com ele abre, sem senha.** Evite publicá-lo num grupo aberto (redes sociais, grupo de WhatsApp com gente de fora): quem tiver o link vê o comprovante daquela pessoa específica. O uso pensado é o um-para-um, direto com o participante.

### Situações

- **Inscrição ainda não confirmada** (pagamento pendente) não tem comprovante — ele só existe depois da confirmação, como o recibo e a credencial.
- **Inscrição cancelada** depois de ter comprovante: o link para de mostrar o documento.

{: .tip }
> **Para quem personaliza os e-mails.** Em **[Configurações → E-mails](/modulos/configuracoes/#e-mails)**, o e-mail de confirmação tem a variável `{voucher_url}` (o link do comprovante). Se o seu modelo personalizado ainda não usa essa variável, o link é **acrescentado automaticamente ao final** da mensagem — você não precisa editar o texto para o participante continuar recebendo o link.

## Credencial

Cada participante confirmado tem uma **credencial** (crachá) com a logo e as cores do evento, em um dos modelos disponíveis, contendo um **QR**.

![Credencial pública com QR](/assets/screenshots/credencial-publica.png)

### O QR e o networking consentido

- **Padrão:** o QR aponta apenas para a página de validação da credencial (`credencial/{código}`), usada no **check-in**.
- **Com consentimento de networking:** o QR passa a carregar um **cartão de contato (vCard)** — nome, e-mail, telefone, organização e cargo, conforme o mapeamento que você definiu — mantendo o código embutido para o check-in.

### Envio e geração em lote

- **Envio automático** (opcional por evento): a credencial em PDF vai ao e-mail de cada inscrito.
- **Geração em lote:** um PDF com todas as credenciais (uma por página), pronto para a gráfica.

{: .note }
> O QR da credencial é o que liga o participante ao **[Check-in](/modulos/checkin/)**. Mesmo quando o QR carrega o vCard de networking, o código de inscrição continua embutido — então a leitura no credenciamento funciona igual.

{: .note }
> Nem todo evento precisa de credencial. Na aba **[Credencial](/modulos/editor-evento/)** do editor há um controle **Oferecer credencial para este evento** — desligado, ela deixa de existir por completo para aquele evento: some da Área do Inscrito, o link público para de responder e ela não sai mais anexada no e-mail. Nasce ligado em todo evento.

## Certificado de participação

Quem é elegível recebe um **certificado** na logo e nas cores do evento, em um dos modelos disponíveis (ex.: Clássico e Moderno), com a carga horária quando você a informa.

![Certificado de participação](/assets/screenshots/certificado-publico.png)

- **Elegibilidade por modalidade:** em evento **presencial**, é elegível quem fez **check-in**; em evento **virtual**, quem tem a inscrição **confirmada**.
- **Emissão:** você ativa o certificado, escolhe o modelo e a carga horária na aba **[Certificado](/modulos/editor-evento/)** do editor, e **envia por e-mail** aos elegíveis (envio manual, quando quiser).
- **Verificação:** cada certificado tem um **link público** (`certificado/{código}`) que serve de comprovação — o código é a chave de validação. Há versão imprimível em tela e em PDF.

{: .note }
> O certificado é liberado **só para quem é elegível**. Em evento presencial, isso liga o certificado ao **[Check-in](/modulos/checkin/)**: sem presença registrada, não há certificado.

## Geração de PDF

Os documentos são gerados **internamente pelo plugin**, sem depender de nenhum serviço externo — no limite, com uma versão imprimível em HTML. Para **fidelidade máxima** ao layout, está prevista a integração com o serviço **Gotenberg** (campo marcado como "Em breve" em **[Configurações → Avançado](/modulos/configuracoes/)**).
