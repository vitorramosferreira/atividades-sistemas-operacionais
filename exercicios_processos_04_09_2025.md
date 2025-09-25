Responder o questionário abaixo em seu GitHub (individual). Coloque as perguntas e respostas.

Exercícios Teóricos – Processos

1. Qual a diferença entre programa e processo?
Olha, de forma simples, o programa é o arquivo executável, o código que fica salvo no disco, sem fazer nada. O processo é esse programa quando ele está efetivamente rodando, ou seja, quando o sistema operacional carrega ele na memória e começa a executar suas instruções. Programa é estático, processo é dinâmico.
  
2. Quais são os estados de um processo e quando ocorrem as transições?
Um processo tem um ciclo de vida com alguns estados. Ele pode estar pronto, que é quando está na fila, só esperando a vez de usar o processador. Quando o sistema libera a CPU pra ele, ele passa para execução. Se ele precisar esperar por alguma coisa, tipo ler um arquivo, ele fica bloqueado. O sistema operacional é quem faz a gestão dessas transições pra garantir que tudo flua bem.

3. O que contém um Process Control Block (PCB)?
O PCB é basicamente a "ficha cadastral" do processo para o sistema operacional. É uma estrutura de dados que guarda todas as informações importantes sobre ele: o estado atual (se está rodando, esperando, etc.), qual a próxima instrução a ser executada, os valores dos registradores, informações de memória e a prioridade de execução. É o que o sistema usa pra gerenciar o processo.

4. O que acontece com os recursos de um processo quando ele termina?
Quando um processo finaliza sua execução, o sistema operacional entra em ação para "limpar a casa". Ele libera todos os recursos que estavam alocados para aquele processo, como a memória RAM que ele usava e os arquivos que estavam abertos. Isso é fundamental para que esses recursos fiquem disponíveis para outros processos.

5. Qual a diferença entre fork() e exec() no UNIX?
O fork() é uma chamada de sistema que cria um novo processo, que é uma cópia exata do processo que o chamou (o processo "pai"). Já o exec() substitui o programa que está rodando no processo atual por um programa completamente novo. Resumindo: fork() duplica o processo, exec() substitui o código que está em execução dentro dele.

6. Como funciona a hierarquia de processos em UNIX?
No UNIX, os processos são organizados como uma árvore. Existe o primeiro processo, o init, e todos os outros são "filhos" de algum processo já existente. Isso cria uma relação clara de pai e filho, o que ajuda no gerenciamento, por exemplo, se um processo pai termina, ele pode ser responsável por finalizar seus filhos também.

7. Compare memória compartilhada e troca de mensagens (IPC).
São duas formas de processos se comunicarem. Na memória compartilhada, o sistema reserva uma área da memória que vários processos podem acessar. É muito rápido porque a comunicação é direta. Na troca de mensagens, um processo envia um pacote de dados e o outro recebe, com o sistema operacional intermediando. É mais lento, mas evita conflitos de acesso.

8. Cite exemplos de chamadas de sistema usadas em IPC.
Para fazer essa comunicação entre processos, usamos algumas chamadas de sistema. Por exemplo, pipe() para criar um canal de comunicação unidirecional, shmget() para criar uma região de memória compartilhada e msgget() para criar uma fila de mensagens. Para comunicação em rede, usamos socket().

9. Por que é importante que o sistema operacional faça gerenciamento de processos?
O gerenciamento de processos é crucial para o sistema funcionar. Ele garante que a CPU e a memória sejam compartilhadas de forma justa entre todos os programas em execução. Além disso, ele isola os processos uns dos outros, impedindo que o erro em um programa afete o sistema inteiro. Sem isso, seria impossível ter um ambiente multitarefa estável.

10. Explique a diferença entre processos independentes e processos cooperativos.
Um processo independente roda por conta própria, sem afetar ou ser afetado por outros. Já um processo cooperativo é aquele que foi projetado para interagir com outros, geralmente compartilhando dados. Esses processos precisam de mecanismos de comunicação e sincronização para trabalharem juntos corretamente.

11. O que é um processo zumbi em UNIX/Linux?
Um processo zumbi é um processo que já terminou sua execução, mas sua entrada ainda consta na tabela de processos do sistema. Isso acontece porque o processo "pai" ainda não recebeu a informação de que o filho terminou. Ele não usa CPU, mas ocupa um espaço na tabela de processos até que o pai "reconheça" seu término.

12. Explique a diferença entre chamadas bloqueantes e não bloqueantes em IPC.
Uma chamada bloqueante faz o processo parar e esperar até que a operação de comunicação (enviar ou receber algo) seja concluída. Uma chamada não bloqueante permite que o processo continue executando outras tarefas. Ele faz a solicitação de comunicação e depois verifica se ela já foi completada, sem precisar ficar parado esperando.

13. Qual a diferença entre processo pesado (process) e thread (processo leve)?
Um processo tem seu próprio espaço de memória e recursos. Já as threads são unidades de execução que rodam dentro de um mesmo processo e compartilham a memória e os recursos dele. Por isso são chamadas de "processos leves". É muito mais rápido para o sistema alternar entre threads do que entre processos.

14. Por que sistemas operacionais multiprogramados precisam de troca de contexto (context switch)?
A troca de contexto é o mecanismo que permite a um processador com um só núcleo executar várias tarefas ao mesmo tempo. O sistema operacional para um processo, salva seu estado atual (o contexto), carrega o estado de outro processo e o coloca para executar. Isso acontece tão rápido que nos dá a impressão de que tudo está rodando simultaneamente.

15. Cite vantagens e desvantagens da comunicação via memória compartilhada.
A principal vantagem da memória compartilhada é a velocidade, já que não há necessidade de copiar dados entre os processos. A maior desvantagem é o risco de inconsistência. Se dois processos tentarem escrever no mesmo local ao mesmo tempo, pode corromper os dados. Por isso, exige um controle de sincronização muito cuidadoso por parte do programador.















