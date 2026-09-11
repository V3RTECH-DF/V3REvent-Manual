---
title: Editar participante
parent: Módulos
nav_order: 4.5
---

# Editar participante

Quando um participante erra a modalidade na hora de se inscrever, digita o nome com um erro de português ou troca uma letra do e-mail, você não precisa cancelar a inscrição e pedir para a pessoa refazer tudo. A tela **Editar participante** corrige os dados **daquela pessoa**, sem mexer no resto do pedido.

Está disponível em três lugares — a lista geral **[Inscrições](/modulos/inscricoes/)**, a aba **Inscritos** do **[editor de evento](/modulos/editor-evento/#inscritos)** e a mesma tela dentro da **[página de gestão pelo site](/modulos/gestao-pelo-site/)** — sempre como um botão **Editar participante** na linha da pessoa. É por participante, **não existe em lote**: cada edição é uma pessoa de cada vez, porque cada pessoa pode ter uma modalidade, um nome e um e-mail diferentes.

Quem tem acesso: **Coordenador de Eventos** do evento e **Administrador da Organização** — o mesmo alcance de quem já edita o evento e reenvia confirmações.

![Botão "Editar participante" (ícone de lápis) na coluna Ações da lista de Inscrições](/assets/screenshots/inscricoes-editar-participante.png)

## Por que isto importa

Antes desta tela, corrigir um erro de cadastro exigia cancelar a inscrição inteira e pedir para o participante se inscrever de novo — o que, numa inscrição em grupo, arriscava desmontar o pedido todo por causa de uma letra errada num e-mail. Agora a correção é pontual: você ajusta só o que está errado, o histórico registra o que mudou, e — quando a troca envolve dinheiro — o sistema já calcula a diferença e te dá o caminho para cobrar, dar de cortesia, devolver ou registrar que a devolução foi feita por fora.

## O que dá para editar

O formulário que abre é **o mesmo formulário público de inscrição**, já preenchido com os dados atuais da pessoa — e valem **as mesmas regras** de lá: campos obrigatórios continuam obrigatórios, CPF e e-mail passam pela mesma validação, e os **campos condicionais** aparecem ou somem exatamente como apareceriam no formulário público, conforme as respostas.

{: .note }
> **O campo de arquivo (upload) não é editável por aqui.** Se o evento pede um documento (laudo, comprovante), ele não pode ser trocado nesta tela — apenas os campos de texto, seleção, data e afins.

## Passo a passo

1. Na lista de **Inscrições** (ou na aba **Inscritos** do evento), localize a linha do participante e clique em **Editar participante**.
2. Ajuste os campos necessários — nome, e-mail, modalidade, ou qualquer campo do formulário daquele evento.
3. Se a modalidade mudou e isso muda o preço, a tela mostra a **diferença de valor** na hora (veja a seção abaixo) e pede que você escolha o que fazer com ela.
4. Confira a caixa **Avisar o participante** (vem marcada por padrão).
5. Salve. A mudança vale na hora, e fica registrada no **histórico de alterações** da própria tela.

![Formulário de edição do participante, com a caixa "Avisar o participante"](/assets/screenshots/editar-participante-formulario.png)

## Avisando o participante

A caixa **Avisar o participante** vem **marcada por padrão**: ao salvar, a pessoa recebe de novo o e-mail de confirmação, agora com os dados corrigidos e o link do comprovante. Se o e-mail foi um dos dados alterados, o aviso vai para o **endereço novo** — não para o antigo.

{: .tip }
> Desmarque o aviso só quando a correção for irrelevante para o participante saber (ex.: um ajuste interno de grafia que não muda nada do que a pessoa vê). Na dúvida, deixe marcada: um e-mail a mais nunca confundiu ninguém, um e-mail que devia ter ido e não foi já gerou muito "não me avisaram".

## Histórico de alterações

A própria tela de edição mostra o **histórico** de mudanças já feitas naquele participante: **quem** alterou, **quando**, e **o que era antes** e **o que passou a ser**. É a forma de saber se um dado que parece estranho foi corrigido de propósito ou se é a informação original.

Quando a alteração envolve diferença de valor, o histórico também mostra a **situação da diferença** — cobrada, dada de cortesia, devolvida automaticamente ou devolvida por fora — sempre em **português**, direto no que você lê, sem termo técnico.

## Aviso de check-in já feito

Se o participante **já fez check-in** no evento, a tela de edição avisa isso antes de você salvar — para você saber que está corrigindo o cadastro de alguém que já está no local, e não de alguém que ainda vai chegar.

## Troca que muda o valor

Quando a edição muda a **modalidade** (ou qualquer campo que entre no cálculo do preço), o sistema compara o **preço de tabela** da opção antiga com o da nova — **no lote em que a pessoa se inscreveu** (se o evento usa preço por lote, é o lote vigente na data da inscrição original, não o lote de hoje) — e mostra a diferença antes de você confirmar.

### Ficou mais caro

Você escolhe uma das duas:

- **Cobrar a diferença** — o valor vem preenchido com a diferença calculada, mas é **editável**: dá para cobrar menos do que o valor cheio, por exemplo como upgrade promocional para quem já estava inscrito.
- **Não cobrar (cortesia)** — a modalidade muda e ninguém paga a diferença.

![Confirmação de uma troca que encarece: opção atual, nova opção, diferença e a escolha entre cobrar e dar de cortesia](/assets/screenshots/editar-participante-diferenca.png)

Escolhendo cobrar, o sistema gera um **link de pagamento** para você copiar e mandar por WhatsApp ou e-mail; o participante paga **sem precisar de login**, pelos meios de pagamento que o site já aceita.

Enquanto não for paga, a lista de Inscrições mostra **"diferença pendente de R$ X"** na linha da pessoa; quando o pagamento é concluído, o aviso **some sozinho**.

![Lista de Inscrições mostrando "diferença pendente" na linha do participante](/assets/screenshots/inscricoes-diferenca-pendente.png)

Se a pessoa pagar por **Pix ou dinheiro**, direto com a coordenação (fora do link), use **Marcar como paga por fora** para zerar a pendência sem exigir um novo pagamento pelo site. Se a coordenação decidir **não cobrar** depois de já ter oferecido o link, use **Dispensar**.

{: .tip }
> **Nem todo meio de pagamento aceita pagar pelo link.** Alguns meios configurados no checkout do site simplesmente não suportam cobrança avulsa por link. O caminho **por fora** (Pix, dinheiro, transferência combinada diretamente) sempre funciona, independentemente disso — é o plano B que nunca falha.

### Ficou mais barato

Você escolhe uma das duas:

- **Devolver a diferença** — se o meio de pagamento original aceitar reembolso automático parcial, o sistema devolve sozinho. Se **não** aceitar, a tela avisa **antes de você confirmar** que o valor vai precisar ser devolvido **por fora** (Pix, transferência ou dinheiro) — e, depois de salvar, confirma de novo que a devolução ficou registrada como manual, para não passar despercebido.
- **Não devolver** — a modalidade muda e a diferença fica com a organização.

{: .tip }
> **O aviso de devolução manual é sobre você, não sobre o sistema.** Ele não movimenta dinheiro nenhum — é o lembrete de que **você** precisa devolver o valor ao participante por fora, porque o meio de pagamento usado naquele pedido não faz isso sozinho.

{: .note }
> **Pedido de valor zero não tem o que devolver.** Se a inscrição saiu de graça (por exemplo, um cupom de 100%), não existe diferença a estornar — a troca de modalidade só muda o cadastro.

![Troca que barateia: decisão "Devolver a diferença" com o aviso de que o meio de pagamento não devolve automaticamente](/assets/screenshots/editar-participante-devolucao-manual.png)

## ⚠️ Nunca reembolse o valor total do pedido pela tela da loja

Para acertar uma troca de modalidade, **não use o reembolso total** disponível na tela do pedido do WooCommerce. Reembolso **integral** de um pedido de inscrição **cancela a inscrição inteira** — não é assim que se registra uma diferença de valor. Para qualquer ajuste ligado a uma troca (cobrar, dar de cortesia, devolver ou registrar pagamento por fora), use sempre a tela **Editar participante**, nunca a tela de reembolso da loja.

## Política padrão do evento

Repetir a mesma escolha (cobrar ou cortesia; devolver ou não) a cada troca cansa em eventos com muitas modalidades. Defina um **padrão** na aba **[Preços → Troca com diferença de valor](/modulos/editor-evento/#troca-com-diferença-de-valor)** do editor do evento — dois seletores, um para quando a troca encarece e outro para quando barateia. É só o ponto de partida: em cada edição de participante você ainda pode escolher diferente do padrão.

## Relatório financeiro

O **arrecadado** do evento (o número comparado com a meta na aba Relatório, e a Receita total do Painel) passa a **descontar os reembolsos** feitos por troca e **somar as diferenças pagas** — tanto as pagas pelo link de pagamento quanto as marcadas como pagas por fora. O número reflete o que de fato entrou e saiu por causa das trocas, não só o valor do pedido original.

## Dicas e armadilhas

- **Corrija em vez de cancelar.** Cancelar e pedir para refazer é mais trabalho para você e para o participante, e ainda arrisca perder o lugar dele no lote de preço mais barato. A edição resolve sem esse risco.
- **A diferença é calculada pelo lote da inscrição original**, não pelo lote vigente hoje. Uma troca de modalidade meses depois do 1º lote ter fechado ainda compara com o preço daquele 1º lote, porque foi nele que a pessoa se inscreveu.
- **Cobrar menos que a diferença cheia é uma ferramenta, não um erro.** O campo de valor ao cobrar é editável de propósito — use para oferecer um upgrade promocional sem cobrar o valor integral da diferença.
- **"Diferença pendente" que não some pode ser meio de pagamento sem suporte a link.** Se demorar demais, confira com o participante se ele conseguiu usar o link; se não, resolva por fora e marque como paga.

## Glossário

- **Diferença pendente** — o valor que falta ser pago numa troca que encareceu, enquanto o link de pagamento não foi usado.
- **Cortesia** — decisão de não cobrar a diferença de uma troca que encareceu.
- **Pago por fora** — pagamento recebido fora do link (Pix, dinheiro, transferência combinada), registrado manualmente pela coordenação para zerar a pendência.
- **Dispensar** — desistir de cobrar uma diferença pendente, sem marcar como paga.
