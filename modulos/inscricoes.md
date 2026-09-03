---
title: Inscrições
parent: Módulos
nav_order: 4
---

# Inscrições

A tela **Inscrições** é a lista de todos os participantes inscritos. Aqui você busca, filtra, muda o status, reenvia a confirmação por e-mail e exporta.

![Lista de inscrições com filtros e status editável](/assets/screenshots/inscricoes.png)

{: .note }
> **Precisa das inscrições de um único evento?** Além desta tela geral, cada evento tem a aba **Inscritos** no editor, já filtrada só para aquele evento — com a mesma lista, a mesma troca de status e a mesma exportação (CSV/XLSX/PDF). Veja **[Editor de evento → Inscritos](/modulos/editor-evento/#inscritos)**.

## Filtros e busca

No topo, você filtra por:

- **Evento**;
- **Status** (pendente, confirmada, cancelada);
- **Período** (data de início e fim);
- **Busca** por nome ou e-mail do responsável.

## A tabela

Cada linha é um **participante**, não um pedido. Numa inscrição de grupo (uma empresa ou escola inscrevendo várias pessoas num único pedido), cada pessoa aparece na sua própria linha — as linhas do mesmo pedido ficam visualmente agrupadas por uma borda, com o responsável (quem fez e pagou a inscrição) exibido como coluna em todas elas.

Para trocar o status, **clique na etiqueta de status** (a "pílula" colorida) de qualquer linha do pedido: abre um menu com os status disponíveis (Pendente / Confirmada / Cancelada), com o atual marcado. Escolha um e a mudança é **aplicada na hora**.

{: .note }
> **O status é do pedido, não da pessoa.** Trocar o status numa linha muda o status de **todos os participantes** daquele pedido — não existe "confirmar" um participante e deixar outro pendente no mesmo pedido. Num pedido com mais de um participante, a troca pede confirmação avisando quantas pessoas serão afetadas.

Quando um pedido ultrapassou a capacidade do evento, a inscrição aparece **sinalizada como excedente**.

Há também um **link para o pedido no WooCommerce**, para conferir o pagamento e os dados de cobrança.

## Colunas visíveis

![Seletor de colunas aberto, com a opção "E-mail do participante", e o seletor de itens por página ao lado](/assets/screenshots/inscricoes-colunas-itens-pagina.png)

{: .note }
> *Print pendente desta tela (barra com o botão Colunas e o seletor de itens por página) — depende de sessão autenticada no painel. Será acrescentado após a captura.*

O botão **Colunas**, acima da tabela, abre a lista de colunas disponíveis — incluindo qualquer **campo do formulário** que o evento tenha (por exemplo, Modalidade ou Organização) — para você marcar as que quer ver. A escolha fica **salva por usuário**: da próxima vez que você abrir a tela, continua do jeito que deixou.

Por padrão, a lista já traz o **e-mail do participante** ao lado do e-mail do responsável — antes só o e-mail de quem fez a inscrição aparecia, e conferir se um participante específico digitou o e-mail certo exigia abrir o pedido. Se o seu evento tiver um campo de e-mail com outro nome (ou nenhum), a coluna simplesmente fica vazia para aquele evento, sem quebrar nada.

{: .tip }
> **Já tinha escolhido suas próprias colunas?** Nada muda para você — a coluna nova de e-mail do participante entra na lista de opções, mas não força a exibição em quem já tinha uma seleção personalizada.

As mesmas colunas escolhidas na tela valem para a **exportação** (veja mais abaixo) e para os **relatórios**.

## Itens por página

Acima da tabela, escolha quantos participantes aparecem por página: **20, 50, 100 ou Todos**. A escolha fica salva para as próximas visitas, do mesmo jeito que a escolha de colunas.

{: .warning }
> **"Todos" tem um teto.** Em eventos muito grandes, mostrar todo mundo de uma vez travaria a tela (e, no painel aberto pelo site, o celular de quem está gerenciando). Passando de **1000 participantes**, a tela avisa que está mostrando só uma parte e sugere refinar os filtros ou reduzir o tamanho da página — ela nunca finge que você está vendo a lista inteira quando não está.

## Status de uma inscrição

| Status | Significado |
|---|---|
| **Pendente** | A inscrição começou, mas o pagamento não foi concluído. |
| **Confirmada** | Pagamento concluído — inscritos registrados e e-mails enviados. |
| **Cancelada** | A inscrição foi cancelada. |

## Reenviar a confirmação de inscrição

Quando um participante diz que não recebeu o e-mail de confirmação — foi para o spam, digitou o e-mail errado e já corrigiu, ou simplesmente sumiu —, você reenvia direto da lista, sem precisar pedir para a pessoa se inscrever de novo.

{: .note }
> *Print pendente desta tela — depende de sessão autenticada no painel. Será acrescentado após a captura.*

### Reenvio individual

![Lista de inscritos com o botão "Reenviar confirmação" em cada linha e a barra de ação em lote com participantes selecionados](/assets/screenshots/inscricoes-reenvio.png)

Na coluna de ações de cada participante, clique em **Reenviar confirmação**. O envio é imediato: a tela mostra na hora se foi enviado ou recusado.

Nem toda linha pode receber reenvio:

- **Só participantes de inscrição confirmada recebem reenvio.** Se o pedido estiver **pendente** ou **cancelado**, o botão aparece desabilitado — passe o mouse sobre ele para ver o motivo. Isso evita mandar "sua inscrição está confirmada" para quem ainda não pagou ou já cancelou.
- Enquanto há uma **nova tentativa automática** pendente para aquele participante (veja abaixo), o botão também fica desabilitado — o sistema já vai tentar sozinho.

{: .note }
> **O recibo só acompanha quando o participante é quem pagou.** Numa inscrição individual, reenviar a confirmação reenvia também o recibo, porque a mesma pessoa é participante e responsável. Numa inscrição em grupo (uma empresa ou escola inscrevendo várias pessoas), reenviar para um participante manda **só a confirmação dele** — o recibo tem o valor total do pedido e os dados de quem pagou, e não deveria ir para cada participante do grupo. Quem precisa do recibo é sempre o responsável, que já o recebeu por e-mail e pode reemitir pelo link permanente (veja **[Documentos](/modulos/documentos/)**).

Já reenviado antes? Abaixo do botão aparece **"Reenviado Nx • último em [data]"** — assim você não manda cinco cópias porque três pessoas já pediram a mesma coisa.

### Reenvio em lote

![Aviso de envio em lote em andamento, informando quantos participantes e quantos lotes ainda faltam](/assets/screenshots/inscricoes-envio-gradual.png)

Marque os participantes pela caixa de seleção de cada linha, ou marque **todos os desta página** pela caixa no cabeçalho da coluna. Aparece uma barra de ação com o botão de reenviar em lote.

{: .tip }
> **Precisa de todos os que batem com o filtro, não só os da página?** Depois de marcar a página inteira, aparece a opção **"Selecionar todos os participantes deste filtro"** — ela estende a seleção a todo mundo que corresponde ao evento, status, busca e período que você tem filtrado no momento, mesmo que sejam centenas de pessoas em várias páginas. Antes disso existir, reenviar para uma lista grande obrigava a repetir a operação página por página.

Antes de disparar, uma confirmação mostra **quantas pessoas realmente vão receber** o e-mail — o sistema já desconta quem está pendente/cancelado desse número, então a confirmação nunca superestima. Esse envio "por filtro" tem um teto de **1000 participantes por disparo**; se o filtro tiver mais gente que isso, o excedente não é processado e o resultado avisa isso explicitamente.

{: .important }
> **Envio grande é gradual — e isso é esperado, não travamento.** Passando de um certo volume, o V3REvent não manda tudo de uma vez: ele despacha em **lotes de 100 mensagens a cada 5 minutos** (esses dois números são configuráveis pela equipe técnica, se o seu servidor de e-mail exigir outro ritmo), para não sobrecarregar o envio de e-mail do site. A confirmação já avisa quando isso vai acontecer e estima a duração; enquanto o envio corre, um aviso na própria tela mostra quantos participantes e quantos lotes ainda faltam. Se você tentar disparar outro envio em lote nesse meio-tempo, a tela recusa e pede para aguardar o que já está em andamento — **é para não haver dois lotes concorrentes reenviando para a mesma lista**.

### Nova tentativa automática quando o envio falha

![Linha com a etiqueta "Em nova tentativa" e a data prevista, com o botão de reenvio desabilitado](/assets/screenshots/inscricoes-em-nova-tentativa.png)

Quando um envio (automático ou reenvio) esbarra num problema **temporário** — o servidor de e-mail fora do ar, um limite de envio momentâneo, a caixa de entrada cheia —, o V3REvent **tenta de novo sozinho**, até 3 vezes, com um intervalo cada vez maior entre as tentativas. Enquanto isso, o participante aparece com a etiqueta **"Em nova tentativa"**.

{: .note }
> **"Em nova tentativa" quer dizer "não faça nada agora".** É exatamente por isso que o reenvio manual fica desabilitado nesse estado (veja acima) — reenviar por cima de uma tentativa automática já agendada duplicaria o envio assim que ela desse certo. Espere: se a nova tentativa funcionar, o estado muda sozinho para enviado; se as três tentativas se esgotarem, a falha é registrada como definitiva e o reenvio manual volta a ficar disponível.

Nem toda falha é retentada: **endereço de e-mail ausente ou claramente inválido não entra em nova tentativa automática**, porque insistir não resolve — o problema é o dado, não o envio. Nesse caso, corrija o e-mail do participante e use o reenvio manual.

{: .tip }
> **Por que isto importa.** Antes desta versão, uma instabilidade passageira no envio de e-mail (algo comum e fora do controle do plugin) derrubava todos os e-mails daquela janela sem nenhuma recuperação — alguém precisava notar e reenviar um por um. Agora a maioria dessas falhas se resolve sozinha, e sobra para você só o que de fato precisa de atenção: e-mail com dado errado.

## Exportar

Com um **evento filtrado**, aparecem os botões para exportar a lista em **CSV**, **XLSX** ou **PDF**. Veja também os cortes por presença em **[Relatórios](/modulos/relatorios/)**.

### Colunas de valor

No seletor de colunas (tela e exportação) há duas colunas de dinheiro:

- **Valor da inscrição** — o total cobrado no pedido inteiro, mostrado só na **primeira linha** de cada inscrição. Numa inscrição em grupo (vários participantes num só pedido), as demais linhas ficam em branco nessa coluna — de propósito, para que somar a coluna na planilha não infle o total contando o mesmo pedido várias vezes.
- **Valor por participante (média)** — o total dividido pelo número de inscritos do pedido. É uma **média**: numa inscrição com participantes em modalidades diferentes (ex.: um pagante e um cortesia), não é o valor individual de cada um.

Inscrição **pendente** ou **cancelada** aparece com o valor **entre parênteses** — visível, mas fora da soma. Somar a coluna "Valor da inscrição" na planilha dá o mesmo total que a **Receita total** do Painel e o indicador de Relatórios.

{: .tip }
> **Use a exportação como conferência e backup**
>
> Antes de um evento grande, exporte a lista atual em XLSX e confira nomes, e-mails e quantidades. É mais fácil corrigir um dado agora do que na fila do credenciamento.
