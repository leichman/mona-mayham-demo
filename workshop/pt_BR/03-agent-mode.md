<!-- l10n-sync: source-file="workshop/03-agent-mode.md" -->
# Parte 3: Construa o jogo com fluxos de trabalho agênticos

---

Nesta parte, o Copilot passa de planejador a implementador. Em vez de escrever código linha por linha, descreva o que você quer e deixe o Copilot executar o trabalho nos arquivos que precisam ser alterados.

## Tarefa 1: Conecte a batalha

<!-- track:vscode:start -->
1. Mude para o modo **Agent** no Copilot Chat.
2. Insira este prompt:
<!-- track:vscode:end -->

<!-- track:cli:start -->
1. Retorne o Copilot CLI ao fluxo normal de programação (ou mantenha-o no autopilot se quiser que continue trabalhando até você interrompê-lo).
2. Se ajudar, mencione o arquivo da página para fornecer mais contexto: `@src/pages/index.astro`.
3. Insira este prompt:
<!-- track:cli:end -->

   > Adicione JavaScript do lado do cliente à página de batalha para que:
   > 1. Ao clicar no botão Battle, obtenha os dois nomes de usuário dos campos.
   > 2. Valide se ambos foram preenchidos (e mostre um erro caso contrário).
   > 3. Busque em paralelo, na nossa API, os dados de contribuições dos dois usuários.
   > 4. Renderize os gráficos de contribuições em grades coloridas; cada dia deve aparecer como um quadrado colorido usando a paleta do GitHub.
   > 5. Mostre um selo VS entre os dois usuários.
   > 6. Exiba o nome de usuário, o total de contribuições e o intervalo de datas de cada usuário.
   > 7. Trate estados de carregamento e erros.
   > 8. Acione a ação também ao pressionar Enter nos campos de entrada.
   > 9. Mantenha a interface simples; a estrutura inicial já existe.
   >
   > Use interfaces do TypeScript para a estrutura dos dados de contribuições.

<!-- track:vscode:start -->
3. Deixe o Agent Mode implementar as alterações em `index.astro`.
4. Revise as alterações propostas na visualização de diff antes de aceitá-las.
<!-- track:vscode:end -->

<!-- track:cli:start -->
4. Deixe o Copilot CLI implementar as alterações em `src/pages/index.astro`.
5. Use `/diff` para inspecionar as alterações geradas e, em seguida, aprove-as.
<!-- track:cli:end -->

## Tarefa 2: Teste a batalha

> **⚠️ Não está vendo as alterações?** Se a página de batalha não tiver sido atualizada, pare o servidor de desenvolvimento (`Ctrl+C`), reinicie com `npm run dev` e atualize o navegador.

1. Digite `octocat` e `torvalds` como nomes de usuário e clique em **Battle**.
2. Os dois gráficos de contribuições deverão aparecer lado a lado em grades coloridas.
3. Teste os casos de erro:
   - Deixe um ou os dois campos vazios e clique em Battle: deverá aparecer um erro de validação.
   - Informe um nome de usuário inválido: o aplicativo deverá exibir um erro da API.
4. Pressione **Enter** em qualquer campo; a batalha deverá começar como se você tivesse clicado no botão.

## Tarefa 3: Itere com o Copilot

Se algo não estiver correto, envie comentários de acompanhamento diretamente ao Copilot. Por exemplo:

- *“Os quadrados de contribuições estão grandes demais; altere-os para 12x12px”*
- *“Adicione uma dica ao passar o cursor que mostre a data e a quantidade de contribuições”*
- *“O estado de carregamento precisa de uma animação de pulso”*

<!-- track:vscode:start -->
O Agent Mode lida naturalmente com alterações em vários arquivos e com iterações. Cada prompt de acompanhamento aproveita a conversa anterior, então você pode refinar a implementação aos poucos sem recomeçar.
<!-- track:vscode:end -->

<!-- track:cli:start -->
As sessões do Copilot CLI mantêm o histórico, então cada prompt de acompanhamento se baseia nos anteriores. Use `/session` ou `/context` para conferir o contexto que o Copilot está usando e `/review` após uma iteração maior para fazer uma revisão adicional de bugs ou melhorias.
<!-- track:cli:end -->

## Dicas para esta parte

- **Seja específico sobre o que quer**: requisitos claros levam a resultados melhores.
- **Divida tarefas grandes em prompts menores** se o Copilot sair do rumo.
- **Revise as alterações antes de aceitá-las**: é mais rápido inspecionar o código gerado do que reescrevê-lo depois.
- **Teste o aplicativo após cada etapa de implementação** para identificar os problemas enquanto ainda estão localizados.

## ✅ Parte 3 concluída

Você aprendeu a:

- Usar o Copilot para **implementar alterações em vários arquivos**
- **Iterar nos resultados** com comentários de acompanhamento específicos
- Lidar com o **ciclo completo de um recurso**: implementação, revisão, testes e refinamento
