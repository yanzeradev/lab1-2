# Laboratório 1.2: Comunicação com Sockets e Arquitetura do HTTP

## Identificação

* Aluno: Yankarlos Dias e Santos

## Resultados

As indicações **ref. X**, indicam de qual atividade do enunciado do laboratório a tarefa faz referência. 

1. Descreva o cenário para o experimento utilizado para o laboratório, conforme seção "Cenário de Experimentação no Mininet". 
   Descreva o cenário utilizado em termos de largura de banda (vazão) e atrasos. (texto livre)
   Indique o comando mininet utilizado para estabelecer o cenário do ambiente.

```
No cenário criado foi usado duas estações com apenas um switch, uma largura de banda de 100 megabits por segundo (Mbps), e um
atraso de 4 ms.
```
        mininet@mininet-vm:~$ sudo mn --link tc,bw=200,delay=3ms
        *** Creating network
        *** Adding controller
        *** Adding hosts:
        h1 h2 
        *** Adding switches:
        s1 
        *** Adding links:
        (200.00Mbit 3ms delay) (200.00Mbit 3ms delay) (h1, s1) (200.00Mbit 3ms delay) (200.00Mbit 3ms delay) (h2, s1) 
        *** Configuring hosts
        h1 h2 
        *** Starting controller
        c0 
        *** Starting 1 switches
        s1 ...(200.00Mbit 3ms delay) (200.00Mbit 3ms delay) 
        *** Starting CLI:
        mininet> 



2. (**ref. 3.1**) Identifique o cabeçalho recebido pelo a uma requisição simples HTTP.
3. (**ref. 3.2**) Qual é o valor do cabeçalho `USER-AGENT`?
4. (**ref. 3.5**) Identifique o cabeçalho HTTP das seguintes respostas:

   * `/1.html`
   * `/1.txt`
   * `/1.pdf`
   * `/1.png`

5. (**ref. 3.6**) Explique o comportamento do browser na ocorrência da troca dos cabeçalhos (o que ocorreu e por que ocorreu). (texto livre)

6. (**ref. 3.6**) Explique em detalhes como o browser faz utilização do cache durante o acesso ao conteúdo (em termos de uso de cabeçalhos HTTP **no seu experimento**) e indique a diferença no tempo de carregamento da página obtido no experimento. 

7. (**ref. 5.1 e 5.6**) Indique os tempos de carregamento da página `fig/grafite.html` obtido nos experimentos com e sem conexões simultâneas. (texto livre)

8. Explique o resultado obtido no experimento anterior. (texto livre)
