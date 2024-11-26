# Laboratório 1.2: Comunicação com Sockets e Arquitetura do HTTP

## Identificação

* Aluno: Hiago Antônio Maia

## Formato das respostas

Exceto quando informando explicitamente, todos os resultados devem ser formatados usando a formatação de código no Markdown, conforme já feito nos laboratórios anteriores. Respostas em texto livre devem ser escritas em **texto normal**, sem formatação.

* Documentação do formato de tabelas no Markdown Github: <https://docs.github.com/en/github/writing-on-github/working-with-advanced-formatting/organizing-information-with-tables>


## Requisitos mínimos de entrega deste relatório

Conforme indicado no plano da disciplina, para obter nota mínima de 6,0 do relatório será necessário que ele atenda a **todos** os requisitos abaixo indicados:

1. Todas as tarefas na seção "Resultados" devem ser respondidas e devem seguir o formato solicitado.
2. Não deve haver qualquer tipo de cópia deste relatório com o que outro aluno. Os experimentos e o relatório são individuais.
3. O seu relatório deverá ser submetido pelo Github Classroom.

A complementação da nota pela avaliação qualitativa do relatório, considerará as respostas das questões abertas (em texto livre).

A seção [**"Feedback"**](#Feedback) ao fim deste relatório conterá uma descrição da avaliação do professor.


## Resultados

As indicações **ref. X**, indicam de qual atividade do enunciado do laboratório a tarefa faz referência. 

1. Descreva o cenário para o experimento utilizado para o laboratório, conforme seção "Cenário de Experimentação no Mininet". 
   Descreva o cenário utilizado em termos de largura de banda (vazão) e atrasos. (texto livre)
   Indique o comando mininet utilizado para estabelecer o cenário do ambiente.
```
No cenário criado foi usado duas estações com apenas um switch, uma largura de banda de 100 megabits por segundo (Mbps), e um
atraso de 5 ms. O comando utilizado foi sudo mn --link tc,bw=100,delay=5ms
```

2. (**ref. 3.1**) Identifique o cabeçalho recebido pelo a uma requisição simples HTTP.

```
GET /dir1/ HTTP/1.1
Host: localhost:8888
User-Agent: Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/119.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,/;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
```

3. (**ref. 3.2**) Qual é o valor do cabeçalho `USER-AGENT`?

```
Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/119.0
```

4. (**ref. 3.5**) Identifique o cabeçalho HTTP das seguintes respostas:

   * `/1.html`
  
   ```
   HTTP/1.0 200 OK
   Server: SimpleHTTP/0.6 Python/3.8.5
   Date: Fri, 10 Nov 2023 14:23:21 GMT
   Content-type: text/html
   Content-Length: 170
   Last-Modified: Mon, 07 Jun 2021 18:30:39 GMT
   ```

   * `/1.txt`

   ```
   HTTP/1.0 200 OK
   Server: SimpleHTTP/0.6 Python/3.8.5
   Date: Fri, 10 Nov 2023 14:31:50 GMT
   Content-type: text/plain
   Content-Length: 77
   Last-Modified: Mon, 07 Jun 2021 18:30:39 GMT
   ```

   * `/1.pdf`

   ```
   HTTP/1.0 200 OK
   Server: SimpleHTTP/0.6 Python/3.8.5
   Date: Fri, 10 Nov 2023 14:24:59 GMT
   Content-type: application/pdf
   Content-Length: 14630
   Last-Modified: Mon, 07 Jun 2021 18:30:39 GMT
   ```

   * `/1.png`

   ```
   HTTP/1.0 200 OK
   Server: SimpleHTTP/0.6 Python/3.8.5
   Date: Fri, 10 Nov 2023 14:29:25 GMT
   Content-type: image/png
   Content-Length: 1466
   Last-Modified: Mon, 07 Jun 2021 18:30:39 GMT
   ```

5. (**ref. 3.6**) Explique o comportamento do browser na ocorrência da troca dos cabeçalhos (o que ocorreu e por que ocorreu). (texto livre)

```
O navegador usa os cabeçalhos HTTP para determinar se deve armazenar em cache o recurso e por quanto tempo. Se os cabeçalhos 
estiverem errados, o navegador pode armazenar em cache a resposta incorretamente ou não armazenar em cache quando deveria, 
impactando o desempenho e a experiência do usuário.
``` 

6. (**ref. 3.6**) Explique em detalhes como o browser faz utilização do cache durante o acesso ao conteúdo (em termos de uso de cabeçalhos HTTP **no seu experimento**) e indique a diferença no tempo de carregamento da página obtido no experimento. 

```
O cache desempenha um papel importante na otimização do carregamento de páginas da web, reduzindo a necessidade de baixar 
recursos repetidamente do servidor. Isso economiza tempo e largura de banda, melhorando a experiência do usuário. Os 
cabeçalhos HTTP são usados para controlar o comportamento do cache nos navegadores. Quando o cache estava configurado 
corretamente, o navegador verificou seu cache local antes de solicitar um recurso ao servidor. Como o recurso estava em
cache, o navegador usou a cópia em cache, reduzindo o tempo de carregamento da página.
```

7. (**ref. 5.1 e 5.6**) Indique os tempos de carregamento da página `fig/grafite.html` obtido nos experimentos com e sem conexões simultâneas. (texto livre)

```
Usando conexões simultâneas, o tempo estimado foi de 4.69 segundos para o carregamento da página, e quando não utilizado,
foram 27.58 segundos.
```

8. Explique o resultado obtido no experimento anterior. (texto livre)

```
As conexões simultâneas além de permitirem que o navegador baixe vários recursos ao mesmo tempo, também permitem que ele 
aproveite melhor o cache, pois se um recurso já foi baixado em uma solicitação anterior, ele pode ser reutilizado em 
vez de ser baixado novamente, economizando tempo e largura de banda, por isso o tempo de carregamento da página usando 
conexões simultâneas foi cerca de 6 vezes mais rápido. Sem conexões simultâneas, o navegador tem que esperar o término de 
cada solicitação antes de iniciar a próxima, fazendo com que o carregamento seja muito mais demorado.
```

## Feedback do Professor

*Esta seção será escrita pelo professor ao final da avaliação do seu relatório*.

