Repo for testing workflows using prerelease and release options

From github documentation > https://help.github.com/pt/actions/reference/workflow-syntax-for-github-actions

`on.<event_name>.types`

Seleciona os tipos de atividades que acionarão a execução de um fluxo de trabalho. A maioria dos eventos GitHub são acionados por mais de um tipo de atividade. Por exemplo, o evento para o recurso release (versão) é acionado quando uma versão é published (publicada), unpublished (a publicação é cancelada), created (criada), edited (editada), deleted (excluída) ou prereleased (versão prévia). A palavra-chave types (tipos) permite que você limite a atividade que faz com que o fluxo de trabalho seja executado. Quando somente um tipo de atividade aciona um evento de webhook, a palavra-chave types (tipos) é desnecessária.