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
- **Busca** por nome ou e-mail — do **participante** ou do **responsável**, dos dois lados. Antes, a busca só encontrava pelo responsável; se você digitasse o nome de quem participou mas não pagou, a linha não aparecia. Agora basta lembrar de qualquer um dos dois.

## A tabela

Cada linha é um **participante**, não um pedido. Numa inscrição de grupo (uma empresa ou escola inscrevendo várias pessoas num único pedido), cada pessoa aparece na sua própria linha — as linhas do mesmo pedido ficam visualmente agrupadas por uma borda, com o responsável (quem fez e pagou a inscrição) exibido como coluna em todas elas.

Para trocar o status, **clique na etiqueta de status** (a "pílula" colorida) de qualquer linha do pedido: abre um menu com os status disponíveis (Pendente / Confirmada / Cancelada), com o atual marcado. Escolha um e a mudança é **aplicada na hora**.

{: .note }
> **O status é do pedido, não da pessoa.** Trocar o status numa linha muda o status de **todos os participantes** daquele pedido — não existe "confirmar" um participante e deixar outro pendente no mesmo pedido. Num pedido com mais de um participante, a troca pede confirmação avisando quantas pessoas serão afetadas.

Quando um pedido ultrapassou a capacidade do evento, a inscrição aparece **sinalizada como excedente**.

Há também um **link para o pedido no WooCommerce**, para conferir o pagamento e os dados de cobrança.

## Colunas visíveis

![Seletor de colunas aberto, com a opção "E-mail do participante", e o seletor de itens por página ao lado](/assets/screenshots/inscricoes-colunas-itens-pagina.png)

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

## Envio da confirmação — saiba quem recebeu e quem não recebeu

![Coluna Envio da confirmação na lista de Inscrições, com o filtro por situação de envio](/assets/screenshots/inscricoes-envio-confirmacao.png)

O **status da inscrição** (Pendente/Confirmada/Cancelada) diz se o pagamento foi concluído — não se o participante **recebeu** o e-mail de confirmação. São coisas diferentes: uma inscrição pode estar Confirmada e, ainda assim, o e-mail ter falhado. Por isso a lista tem uma coluna própria, **Envio da confirmação**, marcada para aparecer por padrão, com uma de quatro situações por participante:

| Situação | O que significa |
|---|---|
| **Enviado** | O e-mail de confirmação foi entregue com sucesso. |
| **Em nova tentativa** | O envio falhou por um motivo temporário e o sistema está tentando de novo sozinho — veja **[Nova tentativa automática](#nova-tentativa-automática-quando-o-envio-falha)**. |
| **Falhou** | As tentativas se esgotaram (ou o e-mail está ausente/inválido) e ninguém vai tentar de novo sozinho. Passe o mouse sobre a etiqueta para ver o **motivo** da falha. |
| **Não enviado** | Ainda não houve nenhuma tentativa de envio — por exemplo, a inscrição ainda está pendente. |

### Filtro e aviso de falha

Ao lado dos outros filtros da lista (Evento, Status, Período, Busca), há um filtro **Situação do envio**, para você isolar, por exemplo, só quem está com **Falhou**.

Quando existe **pelo menos uma falha** no recorte atual (evento, período e filtros que você tem selecionados), um **aviso aparece no topo da lista** avisando quantas pessoas estão nessa situação, com um botão que já **aplica o filtro "Falhou"** para você — sem precisar caçar quem precisa de atenção linha por linha. Essa contagem é calculada **antes** de qualquer filtro de e-mail que você já tenha aplicado, então o aviso não desaparece só porque você mudou de recorte.

{: .tip }
> **Por que isto importa.** Antes desta coluna, uma falha de envio só aparecia quando o próprio participante reclamava — e a essa altura ele já podia ter se inscrito de novo, achando que a primeira tentativa não tinha ido adiante. Agora quem organiza descobre e corrige antes disso acontecer.

### Quando o e-mail do participante tem duas fontes divergentes

Alguns eventos guardam o e-mail do participante em mais de um lugar (por exemplo, um campo de e-mail do formulário do evento e um cadastro interno). Quando essas duas fontes **divergem**, a confirmação vai para **os dois endereços**, em **mensagens separadas** — nunca os dois juntos no mesmo e-mail, o que exporia um endereço ao outro. Se um dos dois for inválido ou estiver vazio, a mensagem vai só para o que for válido; se os dois forem iguais, é enviada uma única mensagem, sem duplicar. A situação **Falhou** só acontece quando nenhum dos endereços é válido.

## Duplicidade — quando a pessoa já está inscrita

A coluna **Duplicidade** marca **Duplicada** quando o mesmo participante aparece mais de uma vez no mesmo evento. A comparação é pelo **CPF**, quando o evento pede CPF no formulário; nos eventos que não pedem, é pelo **e-mail**.

{: .note }
> **A marcação é informativa — o V3REvent não bloqueia nem cancela nada sozinho.** Duas inscrições da mesma pessoa podem ser legítimas (ela se arrependeu de uma modalidade e comprou outra, por exemplo) ou um erro de fato. Cabe a quem organiza olhar o caso e decidir: manter as duas, cancelar uma pelo **menu de status** da linha, ou falar com o participante.

{: .tip }
> **Por que isto importa.** Antes desta coluna, uma inscrição repetida só aparecia quando alguém reparava manualmente — folheando a lista, ou quando o relatório fechava com um total maior do que o esperado. Agora a duplicidade salta aos olhos assim que ela acontece, na própria lista, sem precisar cruzar planilha.

O mesmo aviso aparece para quem se inscreve: se a pessoa tentar se inscrever de novo no mesmo evento, o **formulário público** avisa que ela já está inscrita e mostra um caminho para a própria inscrição — mas não impede que ela prossiga, caso a segunda inscrição seja mesmo intencional. Veja **[Formulário público → Já está inscrito?](/modulos/formulario-publico/#já-está-inscrito)**.

## Reenviar a confirmação de inscrição

Quando um participante diz que não recebeu o e-mail de confirmação — foi para o spam, digitou o e-mail errado e já corrigiu, ou simplesmente sumiu —, você reenvia direto da lista, sem precisar pedir para a pessoa se inscrever de novo.

### Reenvio individual

![Lista de inscritos com o ícone de reenvio em cada linha e a barra de ação em lote com participantes selecionados](/assets/screenshots/inscricoes-reenvio.png)

Na coluna **Ações** de cada participante há três ícones: um **envelope** (reenviar a confirmação), um **link em cadeia** (copiar o link do comprovante individual daquele participante — veja **[Comprovante](/modulos/documentos/#comprovante)**) e, ao lado, um **ícone de link externo** que abre o pedido no WooCommerce. Passe o mouse sobre qualquer um dos três para ver o que ele faz antes de clicar — é assim que você confere, sem precisar clicar, qual é o pedido (o número aparece só na dica ao passar o mouse) e se aquele participante já foi reenviado antes.

{: .note }
> **Errou um dado na inscrição de alguém?** O botão **Editar participante**, na mesma linha, corrige nome, e-mail, modalidade ou qualquer campo do formulário — sem cancelar a inscrição e refazer. Disponível para quem coordena o evento e para a administração, sempre por pessoa (não em lote). Veja **[Editar participante](/modulos/editar-participante/)**.

{: .note }
> **O ícone de copiar link do comprovante só liga para inscrição confirmada** — o mesmo motivo do envelope de reenvio: comprovante de quem ainda não confirmou ou já foi cancelado não existe. Ele não tem versão em lote de propósito: é para colar numa conversa (WhatsApp, e-mail avulso), uma pessoa de cada vez. Disponível para quem coordena o evento e para a administração.

{: .tip }
> **Em celular não há mouse, então esse hover não existe** — o número do pedido e o histórico de reenvios só aparecem em **desktop**. É uma escolha deliberada, não uma falha: no celular, toque no ícone de link para abrir o pedido diretamente.

Clique no envelope para reenviar. O envio é imediato: a tela mostra na hora se foi enviado ou recusado.

Nem toda linha pode receber reenvio:

- **Só participantes de inscrição confirmada recebem reenvio.** Se o pedido estiver **pendente** ou **cancelado**, o botão aparece desabilitado — passe o mouse sobre ele para ver o motivo. Isso evita mandar "sua inscrição está confirmada" para quem ainda não pagou ou já cancelou.
- Enquanto há uma **nova tentativa automática** pendente para aquele participante (veja abaixo), o botão também fica desabilitado — o sistema já vai tentar sozinho.

{: .note }
> **O recibo só acompanha quando o participante é quem pagou.** Numa inscrição individual, reenviar a confirmação reenvia também o recibo, porque a mesma pessoa é participante e responsável. Numa inscrição em grupo (uma empresa ou escola inscrevendo várias pessoas), reenviar para um participante manda **só a confirmação dele** — o recibo tem o valor total do pedido e os dados de quem pagou, e não deveria ir para cada participante do grupo. Quem precisa do recibo é sempre o responsável, que já o recebeu por e-mail e pode reemitir pelo link permanente (veja **[Documentos](/modulos/documentos/)**). O que cada participante do grupo recebe, com ou sem ser o responsável, é o próprio **[comprovante individual](/modulos/documentos/#comprovante)** — sem valor pago nem dados de quem pagou.

Já reenviado antes? Passe o mouse sobre o envelope: a dica mostra **"Reenviado Nx, último em [data]"** — assim você não manda cinco cópias porque três pessoas já pediram a mesma coisa.

### Reenvio em lote

![Aviso de envio em lote em andamento, informando quantos participantes e quantos lotes ainda faltam](/assets/screenshots/inscricoes-envio-gradual.png)

Marque os participantes pela caixa de seleção de cada linha, ou marque **todos os desta página** pela caixa no cabeçalho da coluna. Aparece uma barra de ação com o botão de reenviar em lote.

{: .tip }
> **Precisa de todos os que batem com o filtro, não só os da página?** Depois de marcar a página inteira, aparece a opção **"Selecionar todos os participantes deste filtro"** — ela estende a seleção a todo mundo que corresponde ao evento, status, busca e período que você tem filtrado no momento, mesmo que sejam centenas de pessoas em várias páginas. Antes disso existir, reenviar para uma lista grande obrigava a repetir a operação página por página.

Antes de disparar, uma confirmação mostra **quantas pessoas realmente vão receber** o e-mail — o sistema já desconta quem está pendente/cancelado desse número, então a confirmação nunca superestima. Esse envio "por filtro" tem um teto de **1000 participantes por disparo**; se o filtro tiver mais gente que isso, o excedente não é processado e o resultado avisa isso explicitamente.

{: .important }
> **Envio grande é gradual — e isso é esperado, não travamento.** Passando de um certo volume, o V3REvent não manda tudo de uma vez: ele despacha em **lotes de 100 mensagens a cada 5 minutos** (esses dois números são configuráveis pela equipe técnica, se o seu servidor de e-mail exigir outro ritmo), para não sobrecarregar o envio de e-mail do site. A confirmação já avisa quando isso vai acontecer e estima a duração; enquanto o envio corre, um aviso na própria tela mostra quantos participantes e quantos lotes ainda faltam.

{: .note }
> **Um segundo envio em lote, pedido enquanto o primeiro ainda corre, entra na fila — não é recusado.** Ele espera o que já está em andamento terminar e só então começa a despachar os seus próprios lotes; o ritmo (100 mensagens a cada 5 minutos) é o mesmo para todos, então pedir de novo **alonga a fila**, nunca acelera o envio. Isso ajuda o caso comum de reenviar aos poucos, conforme você vai encontrando quem precisa: seleciona um grupo numa página da lista e manda, depois acha outro grupo em outra página (ou outro filtro) e manda de novo — sem precisar esperar o primeiro terminar para pedir o segundo.

### Nova tentativa automática quando o envio falha

Quando um envio (automático ou reenvio) esbarra num problema **temporário** — o servidor de e-mail fora do ar, um limite de envio momentâneo, a caixa de entrada cheia —, o V3REvent **tenta de novo sozinho**, até 3 vezes, com um intervalo cada vez maior entre as tentativas. Enquanto isso, o **ícone de envelope daquele participante fica acinzentado e desabilitado** — sem a cor de sempre, sinal de que não há nada para você fazer ali. Passe o mouse sobre o ícone para ver a previsão: **"Nova tentativa automática a caminho, prevista para [data e hora]"**, seguida do histórico de reenvio quando já houver um (**"— reenviado Nx, último em [data]"**).

{: .tip }
> **Em celular não há como passar o mouse**, então essa previsão não aparece lá — só o ícone acinzentado, indicando que o envio está sendo cuidado sozinho. É uma escolha deliberada, do mesmo tipo já explicada para o número do pedido (veja **[Reenvio individual](#reenvio-individual)**).

{: .note }
> **Ícone acinzentado quer dizer "não faça nada agora".** É exatamente por isso que o reenvio manual fica desabilitado nesse estado — reenviar por cima de uma tentativa automática já agendada duplicaria o envio assim que ela desse certo. Espere: se a nova tentativa funcionar, o ícone volta ao normal (enviado); se as três tentativas se esgotarem, a falha é registrada como definitiva e o reenvio manual volta a ficar disponível.

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
