<div style="max-width: 550px; margin: 0 auto;">
<div align="center">
<h1>Aula 04 - Laços de Repetição</h1>
<div style="border-left: 4px solid #FFD43B; background-color: #FFF8DC; padding: 12px 16px; margin: 15px 0; border-radius: 4px;">
Nesta aula, vamos introduzir o conceito de repetição. Você descobrirá que um computador é excelente em executar a mesma operação muitas vezes, e que estruturas de repetição permitem expressar isso de forma compacta e controlada.
</div>
<img src="../../imagens/py_vector.png" alt="Python" width="250">
<br>
<h2>O Problema da Repetição</h2>
Até agora, nossos programas executaram comandos de cima para baixo, uma única vez. Imagine que precisamos resolver um problema muito simples: imprimir os números de 1 a 5.
<br>
<br>
Com o que sabemos, poderíamos escrever:
<br>
<br>
<div align="left">
<pre><code>print(1)
print(2)
print(3)
print(4)
print(5)</code></pre>
</div>
<br>
Esse programa funciona. O problema não é que a solução esteja errada, o problema é que ela não <strong>escala</strong>.
<br>
<br>
E se quiséssemos imprimir os números de 1 até 100? E se fossem de 1 até 1.000.000? Pior ainda: e se o número final viesse da entrada, fornecido pelo usuário, e não soubéssemos qual é enquanto programamos?
<br>
<br>
Escrever cada instrução manualmente seria impraticável. Se olharmos com atenção, existe uma repetição clara nesse problema. Em vez de escrever <code>print(...)</code> dezenas de vezes, queremos ensinar o computador a: <em>"repita a operação de imprimir o próximo número"</em>.
<br>
<br>
<hr>
<h2>A Ideia de um Laço</h2>
Uma repetição, também chamada de <strong>laço</strong> (ou <em>loop</em>), possui algumas características fundamentais:
<br>
<br>
<ul>
<li>Uma <strong>ação</strong> que será repetida;</li>
<li>Alguma <strong>informação</strong> que muda entre as repetições (por exemplo, o número que será impresso);</li>
<li>Uma <strong>regra</strong> que determina quando continuar;</li>
<li>Uma <strong>condição</strong> que determina quando parar.</li>
</ul>
<br>
Conceitualmente, o computador trabalha assim:
<br>
<br>
<div align="left">
<pre><code>Repetição 1
→ executa a ação

Repetição 2
→ executa a ação

Repetição 3
→ executa a ação
...</code></pre>
</div>
<br>
O computador simplesmente executa o mesmo bloco de código novamente. Cada execução desse bloco é chamada de <strong>iteração</strong>. Agora precisamos aprender a dizer ao Python como essa repetição deve acontecer.
<br>
<br>
<hr>
<h2>While</h2>
A primeira estrutura de repetição que vamos conhecer é o <code>while</code>. Em português, "while" significa "enquanto". A ideia dele é: <em>enquanto uma condição for verdadeira, execute este bloco</em>.
<br>
<br>
Veja como resolvemos o problema de imprimir os números de 1 a 5:
<br>
<br>
<div align="left">
<pre><code>contador = 1

while contador &lt;= 5:
    print(contador)
    contador += 1</code></pre>
</div>
<br>
Antes de analisarmos linha por linha, leia esse código em linguagem natural:
<br>
<br>
<em>"Enquanto contador for menor ou igual a 5: mostre contador; depois aumente contador em 1."</em>
<br>
<br>
Essa leitura é a melhor maneira de interpretar um <code>while</code>. Vamos entender cada parte:
<br>
<br>
<ul>
<li><code>contador = 1</code>: é a preparação antes do laço começar.</li>
<li><code>while contador &lt;= 5:</code>: é a condição que será verificada. Note os dois pontos (<code>:</code>) no final, que indicam que um bloco de código vai começar.</li>
<li><code>print(contador)</code>: é uma das ações repetidas. Repare que ela possui um recuo à esquerda (indentação).</li>
<li><code>contador += 1</code>: faz o programa avançar, também indentado.</li>
</ul>
<br>
A indentação não é apenas visual no Python. É ela que diz ao computador que essas duas linhas pertencem ao bloco do <code>while</code> e devem ser repetidas.
<br>
<br>
<h3>Execução Passo a Passo</h3>
Não basta apenas ler o código. Vamos ver o que o Python realmente faz durante a execução. O <code>while</code> não "sabe" previamente que serão cinco repetições. Ele continua porque a condição permanece verdadeira.
<br>
<br>
<table border="1" style="width: 100%; text-align: center; border-collapse: collapse;">
<tr><th>Valor de contador</th><th>Condição <code>contador &lt;= 5</code></th><th>O que acontece</th></tr>
<tr><td>1</td><td>True</td><td>Imprime 1 → contador vira 2</td></tr>
<tr><td>2</td><td>True</td><td>Imprime 2 → contador vira 3</td></tr>
<tr><td>3</td><td>True</td><td>Imprime 3 → contador vira 4</td></tr>
<tr><td>4</td><td>True</td><td>Imprime 4 → contador vira 5</td></tr>
<tr><td>5</td><td>True</td><td>Imprime 5 → contador vira 6</td></tr>
<tr><td>6</td><td>False</td><td>Laço termina</td></tr>
</table>
<br>
A condição é verificada <strong>novamente</strong> depois de cada execução completa do bloco. Quando a condição se torna falsa (no caso, quando chega em 6), ele para e o programa continua nas linhas que não estão indentadas.
<br>
<br>
<hr>
<h2>Contador e Atualização</h2>
Vamos aprofundar o papel das linhas <code>contador = 1</code> e <code>contador += 1</code>.
<br>
<br>
A variável <code>contador</code> acompanha o progresso da repetição. A primeira linha define o <strong>ponto de partida</strong>. A linha <code>contador += 1</code> faz o contador avançar. Como vimos na aula sobre operadores de atribuição, isso é apenas uma forma abreviada de escrever <code>contador = contador + 1</code>.
<br>
<br>
Esse padrão não depende apenas dos números 1 e 5. Veja esta variação:
<br>
<br>
<div align="left">
<pre><code>contador = 3

while contador &lt;= 7:
    print(contador)
    contador += 1</code></pre>
</div>
<br>
A lógica é exatamente a mesma: o ponto de partida agora é 3 e ele repete enquanto for menor ou igual a 7.
<br>
<br>
<hr>
<h2>Condição de Parada</h2>
Um laço precisa ter uma maneira de chegar ao fim. No nosso exemplo original:
<br>
<br>
<div align="left">
<pre><code>while contador &lt;= 5:</code></pre>
</div>
<br>
A repetição continua enquanto a condição for verdadeira. Quando <code>contador</code> passa a valer 6, a expressão <code>contador &lt;= 5</code> se torna falsa. Portanto, o laço termina.
<br>
<br>
Visualmente, a ideia é:
<br>
<br>
<div align="left">
<pre><code>condição verdadeira → continua
condição falsa → para</code></pre>
</div>
<br>
Essa mudança não acontece "automaticamente". Alguma variável usada na condição precisa mudar dentro do laço de maneira que permita que a condição eventualmente deixe de ser verdadeira.
<br>
<br>
<hr>
<h2>Loop Infinito</h2>
O que acontece se esquecermos de atualizar o nosso contador?
<br>
<br>
<div align="left">
<pre><code>contador = 1

while contador &lt;= 5:
    print(contador)</code></pre>
</div>
<br>
O que está faltando? O <code>contador += 1</code>. 
<br>
<br>
Sem ele, <code>contador</code> nunca é alterado e continua valendo 1 para sempre. Consequentemente, a condição <code>contador &lt;= 5</code> continua verdadeira para sempre. O programa ficará imprimindo o número 1 sem parar.
<br>
<br>
Isso é conhecido como um <strong>loop infinito</strong>. Como regra prática: <em>"Se a condição do while depende de uma variável, precisamos prestar atenção em como essa variável muda dentro do laço."</em> O uso de um contador mudando a cada iteração é um padrão extremamente comum.
<br>
<br>
<hr>
<h2>While com Quantidade Determinada por Entrada</h2>
Lembra que perguntamos como faríamos se o número final viesse do usuário? O <code>while</code> resolve isso perfeitamente, pois não precisamos saber a quantidade de repetições enquanto escrevemos o programa.
<br>
<br>
<div align="left">
<pre><code>n = int(input())

contador = 1
while contador &lt;= n:
    print(contador)
    contador += 1</code></pre>
</div>
<br>
O usuário fornece <code>n</code>. O programa não sabe antecipadamente qual será esse valor. Se <code>n</code> for 5, serão cinco repetições. Se <code>n</code> for 20, serão vinte.
<br>
<br>
Isso demonstra uma das grandes vantagens dos laços, que conectamos diretamente ao modelo das nossas primeiras aulas:
<br>
<br>
<div align="left">
<pre><code>Entrada:
n

Processamento:
repetir a impressão enquanto contador &lt;= n

Saída:
os números de 1 até n</code></pre>
</div>
<br>
<hr>
<h2>For</h2>
Existe uma situação na programação que acontece com tanta frequência que o Python criou uma estrutura especialmente para ela: <em>"Quero executar uma ação para cada valor de uma sequência."</em>
<br>
<br>
Para esses casos, usamos o <code>for</code>. Veja a solução do nosso problema inicial (imprimir de 1 a 5) usando o <code>for</code>:
<br>
<br>
<div align="left">
<pre><code>for i in range(1, 6):
    print(i)</code></pre>
</div>
<br>
Lendo em português, temos: <em>"Para cada valor de 1 até 5, execute o bloco."</em>
<br>
<br>
Na sintaxe, <code>for i in ...</code> significa que a variável <code>i</code> receberá, uma de cada vez, as informações produzidas pela sequência. 
<br>
<br>
O comando <code>range(1, 6)</code> produz os valores: 1, 2, 3, 4, 5. Então, a execução ocorre assim:
<br>
<br>
<div align="left">
<pre><code>i = 1 → executa
i = 2 → executa
...
i = 5 → executa</code></pre>
</div>
<br>
Quando não há mais valores na sequência, o <code>for</code> termina.
<br>
<br>
<h3>Comparação Imediata</h3>
Ambos os códigos abaixo produzem a mesma saída (1 a 5):
<br>
<br>
<div align="left">
<pre><code># Usando while
contador = 1
while contador &lt;= 5:
    print(contador)
    contador += 1

# Usando for
for contador in range(1, 6):
    print(contador)</code></pre>
</div>
<br>
Eles resolvem o mesmo problema, mas expressam ideias diferentes.
<br>
<br>
No <code>while</code>, a ideia é: <em>"continue enquanto a condição for verdadeira."</em>
<br>
No <code>for</code>, a ideia é: <em>"para cada valor da sequência, execute."</em>
<br>
<br>
O <code>for</code> não é simplesmente "um while mais fácil". Eles são estruturas diferentes, cada uma brilhando mais em determinadas situações.
<br>
<br>
<hr>
<h2>Range()</h2>
O <code>range()</code> é uma ferramenta que você utilizará constantemente junto com o <code>for</code>. Ele serve para gerar sequências de números e possui três formatos diferentes. Vamos entendê-los na ordem.
<br>
<br>
O primeiro formato recebe apenas o limite final:
<br>
<br>
<div align="left">
<pre><code>for i in range(5):
    print(i)</code></pre>
</div>
<br>
Isso produzirá os números 0, 1, 2, 3, 4. 
<br>
Note que <strong>o início padrão é 0</strong> e <strong>o limite final não é incluído</strong>.
<br>
<br>
O segundo formato recebe início e fim:
<br>
<br>
<div align="left">
<pre><code>for i in range(1, 6):
    print(i)</code></pre>
</div>
<br>
Isso produz 1, 2, 3, 4, 5. Ele começa no 1 e para antes do 6, avançando de 1 em 1.
<br>
<br>
O terceiro formato recebe <strong>início, fim e passo</strong>:
<br>
<br>
<div align="left">
<pre><code>for i in range(1, 10, 2):
    print(i)</code></pre>
</div>
<br>
Isso produz 1, 3, 5, 7, 9. O terceiro argumento determina os "saltos". 
<br>
<br>
A regra mental principal para o <code>range()</code> que você deve levar é: <em>"começa em início, vai até antes de fim, avançando de passo em passo."</em>
<br>
<br>
<hr>
<h2>Contagem Regressiva</h2>
E se quisermos contar de trás para frente? O <code>passo</code> do <code>range()</code> também pode ser negativo.
<br>
<br>
<div align="left">
<pre><code>for i in range(5, 0, -1):
    print(i)</code></pre>
</div>
<br>
Isso mostrará: 5, 4, 3, 2, 1.
<br>
<br>
<ul>
<li><code>5</code> → é o início.</li>
<li><code>0</code> → é o limite final, que não é incluído.</li>
<li><code>-1</code> → é o passo, que nos faz andar uma unidade para trás.</li>
</ul>
<br>
<div style="border-left: 4px solid #FFD43B; background-color: #FFF8DC; padding: 12px 16px; margin: 15px 0; border-radius: 4px;">
<strong>Observação importante:</strong> Como o <code>range(5, 0, -1)</code> não inclui o limite final 0, se quisermos que o 0 apareça na tela, precisamos recuar o limite para uma unidade antes. Portanto, faríamos <code>range(5, -1, -1)</code> para incluir o zero no processamento.
</div>
<br>
<hr>
<h2>For Percorrendo uma String</h2>
O <code>for</code> não serve apenas para números gerados pelo <code>range()</code>. Ele pode percorrer outros tipos de sequências, como por exemplo, um texto (string).
<br>
<br>
<div align="left">
<pre><code>palavra = "Python"

for caractere in palavra:
    print(caractere)</code></pre>
</div>
<br>
A cada iteração, a variável <code>caractere</code> receberá uma letra da palavra. A execução será:
<br>
<br>
<div align="left">
<pre><code>1ª iteração → 'P'
2ª iteração → 'y'
3ª iteração → 't'
...</code></pre>
</div>
<br>
Esse é o poder do <code>for</code>: ele entende naturalmente a ideia geral de "percorrer uma sequência".
<br>
<br>
<hr>
<h2>Contadores</h2>
No início da aula, usamos a variável <code>contador</code> para controlar a quantidade de repetições do <code>while</code>. Porém, podemos usar a mesma ideia de contador para responder a uma pergunta muito valiosa nos algoritmos: <em>"Quantas vezes algo aconteceu?"</em>.
<br>
<br>
Imagine que queremos descobrir quantos números pares existem entre 1 e 10.
<br>
<br>
<div align="left">
<pre><code>quantidade = 0

for i in range(1, 11):
    if i % 2 == 0:
        quantidade += 1

print(quantidade)</code></pre>
</div>
<br>
Acompanhe o raciocínio: a variável <code>quantidade</code> começa em 0. O laço percorre os números e, cada vez que o <code>if</code> detecta que um número é par, o nosso contador aumenta uma unidade (<code>quantidade += 1</code>). Ao final do laço, a variável contém o número exato de casos encontrados.
<br>
<br>
Note a diferença fundamental: o <code>i</code> é a variável usada para percorrer os valores da sequência. A <code>quantidade</code> é a variável que criamos para acumular ativamente <strong>quantos</strong> casos encontramos que nos interessam.
<br>
<br>
<hr>
<h2>Acumuladores</h2>
Muito parecidos com os contadores, os acumuladores também acompanham o progresso de um laço, mas com uma diferença essencial: enquanto o contador geralmente aumenta de 1 em 1 para registrar uma quantidade de ocorrências, o acumulador <strong>mantém um valor que vai sendo construído</strong> ao longo das repetições.
<br>
<br>
Se quisermos somar todos os números de 1 até 5:
<br>
<br>
<div align="left">
<pre><code>soma = 0

for i in range(1, 6):
    soma += i

print(soma)</code></pre>
</div>
<br>
A evolução da variável <code>soma</code> fica assim:
<br>
<br>
<ul>
<li><strong>início:</strong> <code>soma = 0</code></li>
<li><strong>depois de processar 1:</strong> <code>soma = 1</code></li>
<li><strong>depois de processar 2:</strong> <code>soma = 3</code></li>
<li><strong>depois de processar 3:</strong> <code>soma = 6</code></li>
<li><strong>depois de processar 4:</strong> <code>soma = 10</code></li>
<li><strong>depois de processar 5:</strong> <code>soma = 15</code></li>
</ul>
<br>
<div style="border-left: 4px solid #FFD43B; background-color: #FFF8DC; padding: 12px 16px; margin: 15px 0; border-radius: 4px;">
Tanto contadores quanto acumuladores <strong>precisam ser inicializados antes do laço</strong> começar (ex: <code>soma = 0</code>), caso contrário, o Python não saberá a partir de que valor começar a adicionar.
</div>
<br>
<hr>
<h2>Break</h2>
Às vezes não queremos apenas esperar a condição normal do laço terminar. Queremos <strong>interromper</strong> a repetição imediatamente quando alguma situação específica acontecer.
<br>
<br>
Para isso, usamos o comando <code>break</code>.
<br>
<br>
<div align="left">
<pre><code>for i in range(1, 11):
    if i == 6:
        break
    print(i)</code></pre>
</div>
<br>
O laço foi programado para ir até 10. Ele imprime 1, 2, 3, 4 e 5. Mas quando <code>i</code> chega a 6, o <code>if</code> é ativado e o <code>break</code> é executado. 
<br>
<br>
Neste exato momento, o <code>break</code> <strong>encerra o laço em que está inserido</strong> completamente. Ele não significa "pule esta iteração", ele mata o laço na mesma hora.
<br>
<br>
<hr>
<h2>Continue</h2>
Diferente do <code>break</code>, que mata o laço inteiro, o <code>continue</code> serve para <strong>encerrar apenas a iteração atual e seguir para a próxima</strong>.
<br>
<br>
<div align="left">
<pre><code>for i in range(1, 6):
    if i == 3:
        continue
    print(i)</code></pre>
</div>
<br>
O resultado na tela será: 1, 2, 4, 5.
<br>
<br>
Quando <code>i</code> vale 3, o <code>continue</code> faz o programa ignorar o restante daquela iteração (o <code>print(i)</code> não acontece para o 3). Mas o laço em si continua vivo puxando o próximo valor.
<br>
<br>
Para reforçar a ideia:
<br>
<br>
<table border="1" style="width: 100%; text-align: left; border-collapse: collapse;">
<tr><th>Comando</th><th>O que faz</th></tr>
<tr><td><code>break</code></td><td>→ Encerra o laço completamente.</td></tr>
<tr><td><code>continue</code></td><td>→ Encerra apenas a iteração atual e segue para a próxima.</td></tr>
</table>
<br>
<br>
<hr>
<h2>While versus For</h2>
Agora que você conhece os dois laços de repetição, quando usar qual? A escolha deve ser guiada pela estrutura do problema, e não pela ideia de que um é "mais poderoso" que o outro.
<br>
<br>
Use <code>for</code> quando o problema naturalmente descrever: <em>"para cada valor de uma sequência..."</em> ou <em>"processe todos os números de 1 a n."</em>.
<br>
<br>
Use <code>while</code> quando o problema naturalmente descrever: <em>"enquanto esta condição for verdadeira..."</em> ou <em>"continue lendo ou processando enquanto uma condição não for satisfeita."</em>
<br>
<br>
<hr>
<h2>Problemas de Programação Competitiva</h2>
Laços aparecem constantemente porque problemas de competição frequentemente exigem processar vários valores, repetir cálculos, contar ocorrências ou somar dados. Vamos ver isso na prática.
<br>
<br>
<strong>Problema 1: Imprimir números de 1 até N</strong>
<br>
Enunciado: Dado um número N, imprima todos os números de 1 até N.
<br>
<em>O que precisa acontecer várias vezes? A impressão. Precisamos saber previamente quantas vezes vamos repetir? Sim, N vezes, o que nos convida a usar for + range().</em>
<br>
<br>
<div align="left">
<pre><code># Entrada
n = int(input())

# Processamento
for i in range(1, n + 1):
    # Saída
    print(i)</code></pre>
</div>
<br>
<strong>Problema 2: Somar números de 1 até N</strong>
<br>
Enunciado: Qual a soma total de todos os números de 1 a N?
<br>
<em>Estamos contando alguma coisa ou acumulando algum valor? Acumulando. Precisamos de um acumulador!</em>
<br>
<br>
<div align="left">
<pre><code># Entrada
n = int(input())

# Processamento
soma = 0
for i in range(1, n + 1):
    soma += i

# Saída
print(soma)</code></pre>
</div>
<br>
<strong>Problema 3: Contar quantos números pares existem entre 1 e N</strong>
<br>
Enunciado: Conte quantos números do intervalo de 1 a N são divisíveis por 2.
<br>
<em>Qual variável controla a repetição? O range(). O que muda a cada iteração é que verificamos o contador de pares através de uma condição.</em>
<br>
<br>
<div align="left">
<pre><code>n = int(input())
pares = 0

for i in range(1, n + 1):
    if i % 2 == 0:
        pares += 1

print(pares)</code></pre>
</div>
<br>
<strong>Problema 4: Calcular uma soma a partir de vários valores informados</strong>
<br>
Enunciado: O primeiro número N diz quantas idades você lerá. Depois, você lerá as N idades (uma por linha). Calcule a soma delas.
<br>
<em>O que precisa ser repetido? A leitura do input! Vamos fazer uma repetição controlada e usar um acumulador.</em>
<br>
<br>
<div align="left">
<pre><code>n = int(input())
soma_idades = 0

for _ in range(n):
    idade = int(input())
    soma_idades += idade

print(soma_idades)</code></pre>
</div>
<br>
<strong>Problema 5: Interromper o processamento</strong>
<br>
Enunciado: Imprima os números da sequência de 1 a 100, mas pare imediatamente se chegar em um número que seja divisível por 13.
<br>
<em>Precisamos parar antes de terminar a sequência? Sim. Logo, o uso do break é obrigatório.</em>
<br>
<br>
<div align="left">
<pre><code>for i in range(1, 101):
    if i % 13 == 0:
        break
    print(i)</code></pre>
</div>
<br>
<strong>Problema 6: Ignorar determinados elementos</strong>
<br>
Enunciado: Imprima a sequência de 1 a 10, mas pule o número 5.
<br>
<em>Ao invés de parar de vez, apenas pulamos o elemento atual com o continue.</em>
<br>
<br>
<div align="left">
<pre><code>for i in range(1, 11):
    if i == 5:
        continue
    print(i)</code></pre>
</div>
<br>
Decompor problemas te permite não depender da memorização de padrões de código!
<br>
<br>
<hr>
<h2>Erros Comuns</h2>
Separamos aqui alguns dos tropeços mais comuns durante o aprendizado inicial sobre laços.
<br>
<br>
<strong>ERRO 1: Esquecer os dois pontos (<code>:</code>)</strong>
<br>
<div align="left">
<pre><code>while contador &lt;= 5
    print(contador)</code></pre>
</div>
<br>
Isso gera um erro de sintaxe. O Python depende dos dois pontos para saber quando a condição termina e quando o bloco inicia.
<br>
<br>
<strong>ERRO 2: Esquecer a indentação</strong>
<br>
<div align="left">
<pre><code>while contador &lt;= 5:
print(contador)</code></pre>
</div>
<br>
O bloco de repetição precisa obrigatoriamente estar recuado (indentado) à direita para o interpretador compreendê-lo como parte do laço.
<br>
<br>
<strong>ERRO 3: Esquecer de atualizar a variável no <code>while</code></strong>
<br>
<div align="left">
<pre><code>contador = 1
while contador &lt;= 5:
    print(contador)</code></pre>
</div>
<br>
Esquecer da atualização causará um loop infinito, pois o laço continuará verificando uma condição que sempre permanecerá inalterada e verdadeira.
<br>
<br>
<strong>ERRO 4: Interpretar incorretamente o limite do <code>range()</code></strong>
<br>
<div align="left">
<pre><code>for i in range(1, 5):
    print(i)</code></pre>
</div>
<br>
Muitos acham que o 5 será incluído, mas o Python interrompe a sequência no valor anterior (neste caso, o 4).
<br>
<br>
<strong>ERRO 5: Confundir <code>break</code> e <code>continue</code></strong>
<br>
Lembre-se da nossa comparação: o <code>break</code> destrói o laço imediatamente inteiro, enquanto o <code>continue</code> ignora apenas a execução atual e puxa a próxima.
<br>
<br>
<strong>ERRO 6: Esquecer de inicializar um contador ou acumulador</strong>
<br>
<div align="left">
<pre><code>for i in range(5):
    soma += i</code></pre>
</div>
<br>
Sem um valor inicial (como <code>soma = 0</code>), a instrução <code>soma += i</code> tentará somar um número a uma variável que sequer existe ainda.
<br>
<br>
<hr>
<h2>Resumo da Aula</h2>
Hoje você viu que:
<br>
<br>
<ol>
<li><strong>Laços</strong> permitem repetir operações de forma eficiente e estruturada no nosso processamento.</li>
<li>O <strong><code>while</code></strong> repete a ação enquanto uma condição for verdadeira.</li>
<li>Um <strong><code>while</code></strong> precisa de uma evolução que permita que a condição eventualmente deixe de ser verdadeira quando essa for a intenção, para não travar num loop infinito.</li>
<li>O <strong><code>for</code></strong> percorre organizadamente os valores de uma sequência inteira.</li>
<li>O <strong><code>range()</code></strong> é usado frequentemente para gerar sequências de números para iterarmos.</li>
<li>O <strong>limite final do <code>range()</code> não é incluído</strong> na iteração.</li>
<li><strong>Contadores</strong> registram ativamente quantidades (quantas ocorrências ocorreram).</li>
<li><strong>Acumuladores</strong> constroem valores continuamente ao longo das repetições (ex: qual o total ou saldo).</li>
<li><strong><code>break</code></strong> encerra completamente o laço.</li>
<li><strong><code>continue</code></strong> pula apenas a iteração atual.</li>
<li>A <strong>escolha entre <code>for</code> e <code>while</code></strong> depende exclusivamente da estrutura descritiva do problema, não há escolha certa universal.</li>
</ol>
<br>
Antes de escrever qualquer laço de repetição, utilize isso como uma checklist mental e se pergunte:
<br>
<br>
<ul>
<li>O que precisa ser repetido?</li>
<li>Quantas vezes?</li>
<li>Como eu sei quando parar?</li>
<li>Qual variável precisa mudar para essa parada acontecer?</li>
<li>Estou contando alguma coisa, ou acumulando um valor geral?</li>
<li>Preciso interromper antes do final se alguma regra for quebrada?</li>
</ul>
<br>
Diferenciar essas respostas te guiará naturalmente na construção correta da Entrada → Processamento → Saída nas competições!
<br>
<br>
</div>
</div>
