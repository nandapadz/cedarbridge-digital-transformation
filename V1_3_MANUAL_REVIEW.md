# Cedarbridge v1.3 — revisão de UX e regressão (teste no Edge)

**Data de preparação:** 13/11/2026  
**Versão:** v1.3 Purple Edition — HTML local  
**Tipo:** revisão da pessoa responsável pelo portfólio / smoke test manual. **Não é UAT formal, teste de segurança ou aprovação de produção.**

## Antes de começar

1. Na sua v1.2, clique em **Export JSON** e guarde o ficheiro. Não apague os dados originais.
2. Abra `Cedarbridge_Service_Requests_Violet_v1_3.html` ou `index.html` no Edge.
3. Confirme que aparece **Cedarbridge v1.3 · Training workspace** no topo.
4. Se os registos anteriores não aparecerem, clique em **Import demo JSON** e escolha o backup da v1.2.
5. Selecione **Operations Coordinator** no campo **Demo role**. Utilize apenas informações fictícias.

## Roteiro de testes

| ID | Teste | Passos | Resultado esperado | Resultado |
| --- | --- | --- | --- | --- |
| UX-01 | Design e navegação | Observe a fila, abra **Create request**, regresse à **Work queue** | Interface roxa, textos legíveis, navegação clara e sem confusão entre **Create request** e o status **New** | **Not Run** |
| REG-01 | Criar pedido | Crie uma solicitação de Facilities com resumo **Meeting room access check**, descrição fictícia e impacto **No** | Mensagem de confirmação, referência única e pedido na fila com status **New** | **Not Run** |
| REG-02 | Responsável | Abra a nova referência, selecione **Jamie Patel** em **Assigned owner** e clique em **Save changes** | Responsável atualizado e evento **Owner changed** no histórico | **Not Run** |
| REG-03 | Corrigir bug antigo (campo original) | No mesmo pedido, selecione **In Progress** em **Request status** e clique em **Save changes** | Status **In Progress** na janela e na fila; evento **Status changed** no histórico | **Not Run** |
| REG-04 | Persistência | Pressione **Ctrl + R**, abra novamente a referência | **In Progress**, **Jamie Patel** e histórico continuam guardados | **Not Run** |
| REG-05 | Viewer + exportação | Mude **Demo role** para **Read-only Viewer**, verifique edição desativada; regresse a Coordinator e clique em **Export CSV** | Viewer não edita na interface; CSV descarregado contém o novo pedido | **Not Run** |

**Se REG-03 falhar:** anote a referência e o status mostrado após **Save changes**. No Work queue, pode testar **Start work →** como alternativa, mas **isso não transforma REG-03 em PASS**. Envie print da janela antes/depois e do status na fila. Não apague ou reinicie a aplicação.

## Resultado de referência (teste técnico controlado, não Edge)

Em 13/11/2026, um teste automatizado específico da v1.3 verificou **Assigned owner → Save changes**, depois **Request status: New → In Progress → Save changes**. Todos os resultados previstos passaram (status do formulário, fila, histórico e read-back de um `localStorage` simulado). **Esse teste usou um substituto de armazenamento em memória; não valida o comportamento no Edge da utilizadora.**

## Feedback a registar

- **UX-01:** [ ] Passou [ ] Falhou
- **REG-01 a REG-05:** [ ] Tudo passou [ ] Houve falha (indicar IDs)
- **Visual roxo:** [ ] Aprovado [ ] Precisa de ajustes
- **Observações / problema:** ___________________________________

**Rastreabilidade:** Jira [SCRUM-27](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-27) (UX), [SCRUM-25](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-25) (regressão do status), [SCRUM-24](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-24) (verificações da v1.2 já concluídas), [SCRUM-26](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-26) (Sprint Review). Os cenários de UAT formal continuam **Not Run**.
