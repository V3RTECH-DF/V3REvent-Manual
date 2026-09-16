---
title: Painel
parent: Módulos
nav_order: 1
---

# Painel (Indicadores)

O **Painel** é a primeira tela do V3REvent e a sua leitura rápida do momento: quantos inscritos, quantas inscrições, quanto de receita e quais eventos estão ativos.

![Painel do V3REvent com indicadores, gráficos e listas recentes](/assets/screenshots/painel.png)

## Inscrição e inscrito — dois números diferentes

O Painel (e o resto do plugin) distingue dois conceitos:

- **Inscrição** é um pedido feito por alguém, e pode incluir várias pessoas de uma vez (uma família, uma equipe, uma delegação).
- **Inscrito** é cada pessoa incluída numa inscrição.

Uma única inscrição de uma empresa com 8 funcionários conta como **1 inscrição** e **8 inscritos**. É por isso que o Painel tem um cartão para cada número — eles respondem perguntas diferentes.

## Os indicadores

No topo, quatro cartões resumem a operação:

- **Total de inscritos** — pessoas registradas em inscrições **confirmadas**.
- **Total de inscrições** — número de pedidos **confirmados** (cada pedido pode ter vários inscritos).
- **Receita total** — soma dos valores das inscrições confirmadas.
- **Eventos** — quantos eventos estão ativos.

Logo abaixo do número grande de cada cartão, a **divisão por situação** mostra quantos estão **Confirmados**, **Pendentes** e **Cancelados** (para inscritos) ou **Confirmadas**, **Pendentes** e **Canceladas** (para inscrições). Nenhum número some: somando as três situações você chega ao total de pessoas ou de pedidos que já passaram pelo formulário, independente do status.

{: .note }
> **Por que só confirmadas no número grande.** O número grande dos dois cartões existe para responder "quantas pessoas/pedidos eu já garanti" — pendente ainda pode não virar pagamento, e cancelada não vale mais. A divisão por situação, logo abaixo, é para quem quer acompanhar o funil inteiro (inclusive quanta gente está pendente de pagar).

{: .note }
> **O que entra na Receita total.** Só inscrições **confirmadas** somam — pendentes e canceladas ficam de fora. O valor de cada inscrição é o que foi **efetivamente cobrado** no pedido (com cupom de desconto já descontado, quando houve). Inscrições feitas antes da atualização de agosto/2026 (v1.69.0) entram pelo **valor de tabela** da época, por não terem esse dado registrado — se o seu total pareceu menor depois de atualizar o plugin, é essa correção, veja **[Descontos com cupom](/guia-do-gestor/descontos-com-cupom/)**.
>
> A partir da v1.86.0, a receita também acompanha as **trocas de modalidade**: devoluções de diferença são **descontadas**, e diferenças **pagas** (pelo link de pagamento ou marcadas como pagas por fora) são **somadas**. Diferença dispensada (cortesia) não soma. Veja **[Editar participante](/modulos/editar-participante/)**.

{: .tip }
> **Quer saber quantas pessoas estão confirmadas num evento específico?** O Painel soma todos os eventos juntos. Para o número de um evento só, filtre a lista de **[Inscrições](/modulos/inscricoes/)** por **Confirmada** — veja **[Inscrições → Filtros e busca](/modulos/inscricoes/#filtros-e-busca)**.

## Os gráficos

Dois gráficos mostram a evolução ao longo dos últimos meses:

- **Inscritos confirmados por mês** — o ritmo de adesão, contando só quem confirmou.
- **Receita por mês** — o resultado financeiro no tempo.

## Listas recentes

Abaixo, você vê as **inscrições recentes** e os **últimos eventos** — este último mostrando os **inscritos confirmados** de cada evento —, com atalhos para abrir cada um.

{: .tip }
> **Leia o Painel todo dia enquanto as inscrições estão abertas**
>
> A curva de inscritos por mês antecipa se você vai bater a meta. Uma queda no ritmo é o sinal para reforçar a divulgação — melhor agir na segunda semana do que descobrir na véspera.

## O cabeçalho do painel

No alto de qualquer tela ficam a **logo**, o **título da seção** atual, a **versão** instalada do plugin e os botões **Manual do Usuário** e **Enviar Feedback**. Veja **[Ajuda e Feedback](/modulos/ajuda-e-feedback/)**.
