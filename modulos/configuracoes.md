---
title: Configurações
parent: Módulos
nav_order: 7
---

# Configurações

As **Configurações** valem para **toda a organização** e servem de base para os eventos. Ficam organizadas em seis abas — **Organização, E-mails, Aparência, Avançado, Administradores e Licença** — e só aparecem para o **Administrador da Organização** (e o administrador do site). Um botão **Salvar** grava as alterações.

{: .note }
> **Coordenador de Eventos e Equipe de Evento não veem esta tela.** Ela some do menu para os dois papéis — antes, o menu aparecia mas salvar dava erro, o que confundia mais do que ajudava. Veja os três papéis em **[Primeiros passos → Entender os papéis de acesso](/primeiros-passos/#4-entender-os-papéis-de-acesso)**.

## Organização

Os dados da organização que promove os eventos — reaproveitados em recibos, credenciais e e-mails.

![Configurações — aba Organização](/assets/screenshots/config-organizacao.png)

- **Nome** e **CNPJ** (aceita o formato **alfanumérico** da RFB, ex.: `12.ABC.345/01DE-35`, com validação do dígito verificador);
- **Endereço** e **contato**;
- **Logo** (pela Biblioteca de Mídia).

{: .tip }
> Preencher bem esta aba é o que faz recibos e credenciais saírem prontos, com a sua identidade, sem retrabalho a cada evento.

## E-mails

Os templates da comunicação automática — sete, cada um com **assunto** e **corpo** próprios, e todos editáveis. Até a v1.88, só os três primeiros (confirmação, relatório e acesso) podiam ser personalizados; os outros quatro (recibo, credencial, convite de avaliação e certificado) usavam um texto fixo. Agora todos passam por aqui.

![Configurações — aba E-mails: remetente, e-mail de confirmação e de relatório](/assets/screenshots/config-emails.png)

- **Remetente** (nome e e-mail), no topo, vale para os sete;
- **E-mail de confirmação** (participante) — enviado a cada participante ao confirmar a inscrição;
- **E-mail de relatório** (responsável) — enviado ao responsável, com o resumo e o anexo dos inscritos;
- **E-mail de acesso à área do inscrito** — enviado a quem pede o link na **[Área do Inscrito](/modulos/area-do-inscrito/)**, informando o e-mail usado na inscrição;
- **E-mail do recibo** (responsável) — enviado automaticamente a quem pagou, assim que a inscrição é confirmada, quando o recibo está ligado nas Configurações. Vai com o PDF do recibo em anexo;
- **E-mail da credencial** (participante) — enviado ao próprio participante quando o evento oferece credencial e pede o envio automático. Vai com o PDF da credencial em anexo;
- **E-mail do convite de avaliação** (participante) — enviado aos participantes presentes quando a coordenação dispara os convites na tela de avaliação do evento;
- **E-mail do certificado** (participante) — enviado aos participantes elegíveis quando a coordenação dispara a entrega na tela de certificado do evento.

![Configurações — aba E-mails: acesso à área do inscrito, recibo e credencial](/assets/screenshots/config-emails-novos.png)

![Configurações — aba E-mails: credencial, convite de avaliação e certificado](/assets/screenshots/config-emails-avaliacao-cert.png)

Cada bloco mostra, abaixo do título, uma frase dizendo **quando aquele e-mail é disparado**, e abaixo do corpo as **variáveis** que valem ali — diferentes em cada um (o de confirmação usa `{event_name}`, `{attendee_name}`, `{voucher_url}` etc.; o do recibo usa `{receipt_url}`; o da credencial usa `{credential_url}`; e assim por diante). Os quatro primeiros podem ser sobrescritos por evento; os demais (recibo, credencial, avaliação, certificado) também.

{: .tip }
> **`{voucher_url}` é o link do [comprovante individual](/modulos/documentos/#comprovante) daquele participante.** Se o seu texto personalizado do e-mail de confirmação não usa essa variável, o link é **acrescentado automaticamente ao final** da mensagem — ninguém deixa de receber o comprovante por causa de uma personalização feita antes desta variável existir.

{: .tip }
> **O e-mail de acesso à área do inscrito traz um link pessoal, de uso único, que expira em algumas horas.** Vale manter no texto a frase avisando isso (o padrão já traz) — é o que evita que alguém encaminhe a mensagem achando que o link continua valendo depois.

{: .tip }
> **Por que personalizar estes quatro agora?** Recibo, credencial, convite de avaliação e certificado chegam para o participante ou pagador do jeito que o texto padrão define — sem antes dar para trocar o tom, adaptar ao seu evento ou traduzir. Se o seu evento tem identidade própria (nome da organização, linguagem mais informal, outro idioma), vale revisar os quatro antes do primeiro disparo.

## Aparência

As cores e a fonte **padrão** que os novos eventos herdam (e que cada evento pode sobrepor na sua aba Aparência).

![Configurações — aba Aparência](/assets/screenshots/config-aparencia.png)

## Avançado

Privacidade, geração de PDF e manutenção.

![Configurações — aba Avançado](/assets/screenshots/config-avancado.png)

- **Retenção de dados (LGPD)** — por quantos meses manter os dados de inscritos de eventos encerrados (0 = desativado). Fora dessa janela, o expurgo é automático.
- **URL da política de privacidade** — o link que aparece no consentimento do formulário.
- **Gotenberg** — campo reservado para o endpoint de um serviço externo de geração de PDF de alta fidelidade. Aparece marcado como **"Em breve"** e ainda não é editável; enquanto isso, o plugin gera os PDFs internamente.
- **Excluir dados ao desinstalar** — opção para remover tudo do banco caso o plugin seja desinstalado.

{: .important }
> **Cuidado com "excluir ao desinstalar"**
>
> Com essa opção ligada, desinstalar o plugin **apaga permanentemente** eventos, inscrições e configurações. É uma ação **irreversível** — só a mantenha marcada se tiver certeza e um backup.

## Administradores

Define quem são os **Administradores da Organização** — os usuários com acesso a todo o plugin (qualquer evento e as próprias Configurações). Busque um usuário do WordPress e adicione-o à lista.

{: .note }
> Este é o topo da hierarquia de acesso. **Coordenadores** e **Equipe** são atribuídos por evento, na aba **Equipe** do editor de evento — não aqui. Veja os papéis em **[Primeiros passos](/primeiros-passos/)**.

## Licença

Onde você ativa a chave de licença do V3REvent.

![Configurações — aba Licença, sem licença ativada](/assets/screenshots/config-licenca.png)

{: .important }
> **A licença dá direito a atualizações e correções — ela nunca desliga o plugin.** Sem uma licença válida, o V3REvent continua funcionando por inteiro; o que fica parado é só o recebimento de versões novas.

Cole a chave (formato `V3RL-XXXX-XXXX-XXXX-XXXX`) e clique em **Ativar**. Depois de ativada, a tela sempre mostra a versão mascarada da chave — ela só trafega por inteiro no momento da ativação.
