---
title: Configurações
parent: Módulos
nav_order: 7
---

# Configurações

As **Configurações** valem para **toda a organização** e servem de base para os eventos. Ficam organizadas em cinco abas — **Organização, E-mails, Aparência, Avançado e Administradores** — e são acessíveis ao **Administrador da Organização**. Um botão **Salvar** grava as alterações.

## Organização

Os dados da organização que promove os eventos — reaproveitados em recibos, credenciais e e-mails.

![Configurações — aba Organização](/assets/screenshots/config-organizacao.png)

- **Nome** e **CNPJ** (aceita o formato **alfanumérico** da RFB, ex.: `12.ABC.345/01DE-35`, com validação do dígito verificador);
- **Endereço** e **contato**;
- **Logo** (pela Biblioteca de Mídia).

{: .tip }
> Preencher bem esta aba é o que faz recibos e credenciais saírem prontos, com a sua identidade, sem retrabalho a cada evento.

## E-mails

Os templates da comunicação automática — três, cada um com **assunto** e **corpo** próprios.

![Configurações — aba E-mails](/assets/screenshots/config-emails.png)

- **Remetente** (nome e e-mail), no topo, vale para os três;
- **E-mail de confirmação** (enviado a cada participante ao confirmar a inscrição);
- **E-mail de relatório** (enviado ao responsável, com o resumo e o anexo dos inscritos);
- **E-mail de acesso à área do inscrito** (enviado a quem pede o link na **[Área do Inscrito](/modulos/area-do-inscrito/)**, informando o e-mail usado na inscrição).

Cada bloco mostra, abaixo do texto, **quando aquele e-mail é disparado** e as **variáveis** que valem ali — exibidas como dica na própria tela, e diferentes entre os três (o de confirmação usa `{event_name}`, `{attendee_name}`, `{voucher_url}` etc.; o de acesso usa `{access_url}`, `{valid_hours}`, `{site_name}` e `{site_url}`). Cada evento pode sobrescrever os dois primeiros; o e-mail de acesso é único para toda a organização, já que a Área do Inscrito não é de um evento específico.

{: .tip }
> **`{voucher_url}` é o link do [comprovante individual](/modulos/documentos/#comprovante) daquele participante.** Se o seu texto personalizado do e-mail de confirmação não usa essa variável, o link é **acrescentado automaticamente ao final** da mensagem — ninguém deixa de receber o comprovante por causa de uma personalização feita antes desta variável existir.

{: .tip }
> **O e-mail de acesso à área do inscrito traz um link pessoal, de uso único, que expira em algumas horas.** Vale manter no texto a frase avisando isso (o padrão já traz) — é o que evita que alguém encaminhe a mensagem achando que o link continua valendo depois.

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
