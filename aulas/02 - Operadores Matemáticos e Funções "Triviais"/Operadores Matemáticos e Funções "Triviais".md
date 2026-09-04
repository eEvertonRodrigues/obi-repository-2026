<div style="max-width: 550px; margin: 0 auto;">
<div align="center">
<h1>Aula 02 - Operadores Matemáticos e Funções "Triviais"</h1>
<div style="border-left: 4px solid #FFD43B; background-color: #FFF8DC; padding: 12px 16px; margin: 15px 0; border-radius: 4px;">
Nesta aula, vamos dar o próximo passo na construção de algoritmos. Já sabemos guardar e receber valores. Agora vamos aprender a manipulá-los, combiná-los e transformá-los usando operadores e funções que aparecem em quase todos os problemas de programação competitiva.
</div>
<img src="../../imagens/py_vector.png" alt="Python" width="250">
<br>
<h2>O Próximo Passo: Expressões</h2>
Na Aula 01, o nosso foco principal foi em como <strong>armazenar</strong> informações. Vimos que podemos guardar dados em variáveis:
<br>
<br>
<div align="left">
<pre><code>a = 10
b = 3</code></pre>
</div>
<br>
Mas variáveis não são apenas caixas onde guardamos valores para sempre. O verdadeiro poder da programação está em <strong>usar os valores armazenados para construir novos valores</strong>.
<br>
<br>
É aqui que entram as <strong>expressões</strong>. Uma expressão é qualquer combinação de valores, variáveis e operadores que o Python consiga calcular para produzir um resultado.
<br>
<br>
<div align="left">
<pre><code>resultado = a + b
print(resultado)</code></pre>
</div>
<br>
A ideia central desta aula, e de grande parte da programação competitiva, pode ser resumida nesse fluxo:
<br>
<br>
<div align="left">
<pre><code>Valor → Expressão → Resultado</code></pre>
</div>
<br>
A partir de agora, o nosso objetivo é olhar para a entrada de um problema e pensar: <em>"Quais operações eu preciso aplicar sobre esses valores para chegar no resultado esperado?"</em>
<br>
<br>
<hr>
<h2>Operadores Aritméticos</h2>
Para transformar valores numéricos, Python nos oferece um conjunto de <strong>operadores aritméticos</strong>. Em vez de decorar uma lista de símbolos, vamos tentar entender quais perguntas cada operador nos ajuda a responder.
<br>
<br>
Vamos usar os mesmos valores do exemplo anterior:
<br>
<br>
<div align="left">
<pre><code>a = 10
b = 3</code></pre>
</div>
<br>
<h3>As Operações Básicas</h3>
As operações mais diretas são a adição (<code>+</code>), subtração (<code>-</code>) e multiplicação (<code>*</code>).
<br>
<br>
<div align="left">
<pre><code>print(a + b)
print(a - b)
print(a * b)</code></pre>
</div>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>13
7
30</code></pre>
</div>
<br>
Como vimos na Aula 01, o comportamento desses operadores depende do tipo do dado. A soma matemática só acontece se os valores forem números. Se fossem textos (<code>"10" + "3"</code>), o Python juntaria os pedaços (<code>"103"</code>).
<br>
<br>
<h3>Três Formas de Dividir</h3>
Em muitos problemas, precisaremos dividir grupos, distribuir itens ou encontrar partes que sobraram. O Python oferece três operadores que trabalham juntos para responder perguntas sobre divisão.
<br>
<br>
<div align="left">
<pre><code>print(10 / 3)
print(10 // 3)
print(10 % 3)</code></pre>
</div>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>3.3333333333333335
3
1</code></pre>
</div>
<br>
O que aconteceu aqui?
<br>
<br>
<ul>
<li><strong><code>/</code> (Divisão Normal):</strong> Responde à pergunta <em>"Qual é o resultado exato da divisão?"</em>. Esse operador <strong>sempre</strong> produz um número com casas decimais (<code>float</code>), mesmo que a divisão seja exata (ex: <code>10 / 2</code> produz <code>5.0</code>).</li>
<li><strong><code>//</code> (Divisão Inteira):</strong> Responde à pergunta <em>"Quantas vezes o divisor cabe completamente no número?"</em>. O 3 cabe exatamente 3 vezes dentro do 10. Ele faz um arredondamento para baixo (<em>floor division</em>).</li>
<li><strong><code>%</code> (Módulo ou Resto):</strong> Responde à pergunta <em>"O que sobrou?"</em>. Se o 3 cabe 3 vezes dentro do 10, nós usamos 9 no total. Sobra exatamente 1.</li>
</ul>
<br>
Esses operadores são fundamentais. O módulo (<code>%</code>), em especial, aparece com enorme frequência em programação competitiva. Uma aplicação clássica é verificar a <strong>paridade</strong> de um número. Se dividirmos algo por 2 e não sobrar nada, o número é par:
<br>
<br>
<div align="left">
<pre><code>numero = 42
resto = numero % 2
print(resto) # 0, logo 42 é par</code></pre>
</div>
<br>
<div style="border-left: 4px solid #FFD43B; background-color: #FFF8DC; padding: 12px 16px; margin: 15px 0; border-radius: 4px;">
<strong>Cuidado com o <code>//</code> em números negativos:</strong> Dizer que o <code>//</code> apenas "corta a parte decimal" é um erro comum. Ele arredonda <strong>para baixo</strong>.
<br><br>
Se fizermos <code>-10 / 3</code>, o resultado exato é aproximadamente <code>-3.33</code>. Arredondando isso para o inteiro mais baixo (ou seja, mais negativo), o Python nos dá <code>-4</code>.
<br><br>
Portanto, <code>-10 // 3</code> produz <code>-4</code>.
</div>
<br>
<h3>Potência e Radiciação</h3>
Para calcular potências, utilizamos o operador <code>**</code>.
<br>
<br>
<div align="left">
<pre><code>print(2 ** 2)
print(2 ** 3)
print(2 ** 4)</code></pre>
</div>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>4
8
16</code></pre>
</div>
<br>
Um truque matemático muito útil é que a radiciação pode ser expressa utilizando expoentes fracionários. Pela regra matemática, a raiz de índice <em>n</em> de um número <em>x</em> elevado a <em>b</em> equivale a <code>x ** (b / n)</code>.
<br>
<br>
Por isso, a raiz quadrada de 9 pode ser calculada como <code>9 ** (1/2)</code> (ou <code>0.5</code>). O número 9 está elevado a 1, e o índice <em>n</em> da raiz quadrada é 2:
<br>
<br>
<div align="left">
<pre><code>print(9 ** (1/2))
print(9 ** 0.5)</code></pre>
</div>
<br>
<br>
<hr>
<h2>Precedência: Quem resolve primeiro?</h2>
Quando juntamos vários operadores em uma mesma expressão, o Python precisa decidir quem ele resolve primeiro. A regra é muito parecida com a matemática que aprendemos na escola.
<br>
<br>
O que você acha que o código abaixo imprime?
<br>
<br>
<div align="left">
<pre><code>print(2 + 3 * 4)</code></pre>
</div>
<br>
Se o Python lesse simplesmente da esquerda para a direita, ele somaria 2 e 3 (resultando 5) e multiplicaria por 4 (resultando 20). Mas a multiplicação tem <strong>precedência</strong> sobre a adição. O cálculo real é 3 vezes 4 (12), mais 2, resultando em <strong>14</strong>.
<br>
<br>
Para forçar a adição a acontecer primeiro, usamos <strong>parênteses</strong>:
<br>
<br>
<div align="left">
<pre><code>print((2 + 3) * 4) # Agora sim resulta em 20</code></pre>
</div>
<br>
A ordem prática do que o Python resolve primeiro até o que resolve por último é:
<br>
<br>
<div align="left">
<pre><code>1. ()
2. **
3. +x, -x (Sinais de número positivo/negativo)
4. *, /, //, %
5. +, -</code></pre>
</div>
<br>
<div style="border-left: 4px solid #FFD43B; background-color: #FFF8DC; padding: 12px 16px; margin: 15px 0; border-radius: 4px;">
Mesmo conhecendo essa ordem, a regra de ouro em competições é: <strong>se os parênteses ajudam a deixar a sua intenção mais clara, use-os.</strong>
</div>
<br>
<hr>
<h2>Atalhos: Operadores de Atribuição</h2>
Na Aula 01, vimos que é muito comum atualizar o valor de uma variável baseando-se no valor que ela já tem. 
<br>
<br>
<div align="left">
<pre><code>x = 10
x = x + 1</code></pre>
</div>
<br>
Em vez de repetir o nome da variável, podemos usar operadores combinados. O <code>x += 1</code> faz exatamente a mesma coisa que <code>x = x + 1</code>.
<br>
<br>
Isso funciona para os outros operadores aritméticos também, incluindo os novos que acabamos de aprender:
<br>
<br>
<div align="left">
<pre><code>x = 10
x += 2   # x vira 12
x /= 3   # x vira 4.0
x %= 3   # x vira 1.0 (o resto de 4.0 dividido por 3)
x **= 3  # x vira 1.0 (1.0 elevado a 3)</code></pre>
</div>
<br>
<hr>
<h2>A Pegadinha do <code>++</code></h2>
Se você já programou em linguagens como C, C++ ou Java, deve estar acostumado a fazer incrementos usando <code>x++</code>.
<br>
<br>
Essa é uma das armadilhas mais comuns para quem está migrando para Python. <strong>O Python NÃO possui os operadores <code>++</code> ou <code>--</code>.</strong>
<br>
<br>
Tentar usar <code>x++</code> vai causar um erro de sintaxe. A forma oficial e recomendada de fazer um incremento de 1 unidade em Python é:
<br>
<br>
<div align="left">
<pre><code>C/C++/Java → x++
Python     → x += 1</code></pre>
</div>
<br>
<hr>
<h2>O que são Funções e Métodos?</h2>
Já conseguimos combinar valores usando operadores. Mas muitas operações úteis e frequentes não são representadas por símbolos como <code>+</code> ou <code>/</code>.
<br>
<br>
Para essas situações, Python nos entrega diversas <strong>funções</strong> prontas.
<br>
<br>
Mas o que é uma função? Conceitualmente, uma função é um bloco de código já escrito por alguém, que recebe um ou mais valores (os "argumentos"), realiza um trabalho interno e <strong>devolve um resultado</strong>.
<br>
<br>
<div align="left">
<pre><code>-15
 ↓
abs()
 ↓
15</code></pre>
</div>
<br>
Assim como operadores, nós podemos pegar esse valor retornado pela função e armazená-lo numa variável:
<br>
<br>
<div align="left">
<pre><code>resultado = abs(-15)</code></pre>
</div>
<br>
Para que não fiquemos confusos ao longo do curso, existem três formatos comuns de comandos que encontraremos:
<br>
<br>
<ul>
<li><strong>Operador:</strong> Usa um símbolo (ex: <code>a + b</code>).</li>
<li><strong>Função:</strong> Chamamos pelo nome, passando valores dentro dos parênteses (ex: <code>abs(-15)</code> ou <code>len(texto)</code>).</li>
<li><strong>Método:</strong> É uma função que "pertence" a um dado específico e é chamada usando um ponto a partir dele (ex: <code>texto.replace("a", "b")</code>).</li>
</ul>
<br>
<hr>
<h2>A Caixa de Ferramentas Numéricas</h2>
Vamos conhecer algumas das funções integradas mais úteis para resolver problemas numéricos. 
<br>
<br>
<h3><code>abs()</code></h3>
<strong>Pergunta que resolve:</strong> <em>"Qual é a distância entre esses dois números, ignorando se um é maior ou menor que o outro?"</em>
<br>
<br>
O <code>abs()</code> retorna o valor absoluto, ignorando sinais negativos.
<br>
<br>
<div align="left">
<pre><code>a = 10
b = 17

distancia = abs(a - b)  # abs(-7) vira 7
print(distancia)</code></pre>
</div>
<br>
<h3><code>min()</code> e <code>max()</code></h3>
<strong>Pergunta que resolve:</strong> <em>"Dentre todos esses valores, qual é o extremo menor/maior?"</em>
<br>
<br>
<div align="left">
<pre><code>menor = min(10, 5, 8)
maior = max(10, 5, 8)

print(menor, maior) # Imprime: 5 10</code></pre>
</div>
<br>
<h3><code>sum()</code></h3>
<strong>Pergunta que resolve:</strong> <em>"Qual é o total acumulado desta coleção?"</em>
<br>
<br>
<div align="left">
<pre><code>valores = [1, 2, 3, 4]
total = sum(valores)
print(total) # Imprime: 10</code></pre>
</div>
<br>
<h3><code>pow()</code></h3>
É uma função que faz exatamente a mesma coisa que o operador de potência <code>**</code>.
<br>
<br>
<div align="left">
<pre><code>print(pow(2, 3)) # Imprime: 8</code></pre>
</div>
<br>
Para a grande maioria das operações simples, <code>pow(2, 3)</code> e <code>2 ** 3</code> são equivalentes. No futuro, você verá que <code>pow()</code> possui funcionalidades adicionais para aritmética modular, mas por enquanto, ambas servem o mesmo propósito.
<br>
<br>
<h3><code>round()</code></h3>
Faz o arredondamento de um número de ponto flutuante para o inteiro mais próximo.
<br>
<br>
<div align="left">
<pre><code>print(round(3.14)) # Imprime: 3
print(round(3.85)) # Imprime: 4</code></pre>
</div>
<br>
<hr>
<h2>Tamanho e Coleções</h2>
Além de cálculos puramente matemáticos, com frequência precisamos descobrir propriedades dos dados que recebemos. 
<br>
<br>
A função <code>len()</code> (abreviação de <em>length</em>) responde a uma pergunta simples: <strong>Quantos elementos existem aqui?</strong>
<br>
<br>
Se passarmos um texto, ela nos diz quantas letras existem. Se passarmos uma lista, ela nos diz quantos itens estão lá dentro.
<br>
<br>
<div align="left">
<pre><code>tamanho_texto = len("Python")
tamanho_lista = len([10, 20, 30, 40])

print(tamanho_texto)
print(tamanho_lista)</code></pre>
</div>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>6
4</code></pre>
</div>
<br>
<div style="border-left: 4px solid #FFD43B; background-color: #FFF8DC; padding: 12px 16px; margin: 15px 0; border-radius: 4px;">
<strong>Tamanho vs Índices:</strong> Uma string como <code>"Python"</code> possui tamanho 6. Porém, os espaços que essas letras ocupam são contados a partir do zero. As posições são: 0, 1, 2, 3, 4, e 5. Veremos como acessar essas posições no futuro.
</div>
<br>
<hr>
<h2>Métodos de Strings</h2>
Agora que já sabemos transformar valores, precisamos saber transformar textos (strings). Em programação competitiva, muitas vezes a entrada chega cheia de espaços indesejados ou letras que precisam ser substituídas.
<br>
<br>
Strings possuem seus próprios <strong>métodos</strong> acionados através de um ponto <code>.</code>
<br>
<br>
Imagine que recebemos um texto bagunçado:
<br>
<br>
<div align="left">
<pre><code>texto = "  Python é INCRÍVEL  "</code></pre>
</div>
<br>
Podemos usar métodos encadeados ou repetidos para limpar esse texto:
<br>
<br>
<div align="left">
<pre><code># .strip() remove espaços sobrando nas laterais
texto = texto.strip() 

# .lower() converte tudo para minúsculas
texto = texto.lower() 

print(texto)</code></pre>
</div>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>python é incrível</code></pre>
</div>
<br>
Outros métodos comuns incluem o <code>.upper()</code> (tudo maiúsculo) e o <code>.split()</code> (que já usamos para separar a entrada nos espaços).
<br>
<br>
<h3>A Imutabilidade e o <code>replace()</code></h3>
Um método incrivelmente útil é o <code>.replace("a", "b")</code>, que substitui um pedaço do texto por outro. 
<br>
<br>
Mas há um detalhe que surpreende muitos iniciantes. O que você acha que este código imprime?
<br>
<br>
<div align="left">
<pre><code>texto = "banana"
texto.replace("a", "o")
print(texto)</code></pre>
</div>
<br>
Se você disse "bonono", se enganou! A saída é <code>banana</code>.
<br>
<br>
Por que isso acontece? Em Python, as strings são <strong>imutáveis</strong>. Isso quer dizer que é impossível alterar uma string depois de criada. O que o <code>replace()</code> (e os outros métodos como <code>lower()</code>) faz não é "editar" o texto original. Na verdade, ele <strong>produz uma nova string inteiramente nova</strong>.
<br>
<br>
Se quisermos guardar essa nova versão, temos que reatribuir a variável (ou salvar em outra):
<br>
<br>
<div align="left">
<pre><code>texto = "banana"
texto = texto.replace("a", "o") # Agora sim estamos salvando a nova string
print(texto) # Imprime: bonono</code></pre>
</div>
<br>
<hr>
<h2>Organizando as Coleções</h2>
Para fechar a nossa caixa de ferramentas, vamos ver de forma muito introdutória como organizar os dados que recebemos.
<br>
<br>
Se você tiver uma coleção (como uma lista de números) e precisar que eles fiquem em ordem, a função <code>sorted()</code> é o que você procura: ela recebe a coleção e <strong>devolve uma versão ordenada</strong>.
<br>
<br>
<div align="left">
<pre><code>numeros = [4, 1, 7, 2]
ordenados = sorted(numeros)

print(ordenados) # Imprime: [1, 2, 4, 7]</code></pre>
</div>
<br>
Para colocar do maior para o menor, usamos o argumento <code>reverse=True</code>:
<br>
<br>
<div align="left">
<pre><code>print(sorted(numeros, reverse=True)) # Imprime: [7, 4, 2, 1]</code></pre>
</div>
<br>
E se o seu objetivo for <strong>apenas inverter a ordem original</strong>, independentemente dos valores, usamos a função <code>reversed()</code>. Como ela retorna algo chamado "iterador" (que não é bem uma lista), colocamos um <code>list()</code> em volta para conseguir ver o resultado final:
<br>
<br>
<div align="left">
<pre><code>numeros = [4, 1, 7, 2]
invertidos = list(reversed(numeros))
print(invertidos) # Imprime a ordem ao contrário: [2, 7, 1, 4]</code></pre>
</div>
<br>
<hr>
<h2>Não Confunda!</h2>
Nossa caixa de ferramentas cresceu rápido. É normal misturar algumas coisas no início. Aqui está um resumo rápido para não errar:
<br>
<br>
<ul>
<li><strong><code>/</code> vs <code>//</code>:</strong> A barra simples sempre gera um resultado decimal (<code>10 / 2 = 5.0</code>). A barra dupla faz divisão inteira arredondada para baixo (<code>10 // 3 = 3</code>).</li>
<li><strong><code>//</code> vs <code>%</code>:</strong> O primeiro responde "quantas vezes cabe inteiro" (<code>10 // 3 = 3</code>). O segundo responde "o que sobrou no final?" (<code>10 % 3 = 1</code>).</li>
<li><strong><code>**</code> vs <code>*</code>:</strong> Multiplicação é <code>*</code>. Potência exige <strong>dois</strong> asteriscos <code>**</code>.</li>
<li><strong><code>len()</code> vs <code>length()</code>:</strong> Em Python, para descobrir o tamanho de algo, use apenas <code>len(x)</code>.</li>
<li><strong><code>sorted(lista)</code> vs <code>lista.sort()</code>:</strong> A função <code>sorted</code> não altera a lista original, ela gera uma nova. O método <code>.sort()</code> mexe na própria lista.</li>
<li><strong><code>reversed()</code> vs ordenação decrescente:</strong> Inverter não é ordenar. O <code>reversed</code> apenas olha a mesma coleção de trás para frente.</li>
<li><strong><code>x++</code> vs <code>x += 1</code>:</strong> Nunca use <code>++</code> em Python.</li>
</ul>
<br>
<hr>
<h2>Problemas Integradores</h2>
Agora que já sabemos receber valores, usar expressões, chamar funções e combinar tudo isso, vamos ver como essas ferramentas resolvem problemas pequenos.
<br>
<br>
Toda a base que construímos obedece o mesmo padrão: <strong>Entrada → Processamento → Saída</strong>.
<br>
<br>
<strong>Problema 1: Conversão de Temperatura</strong>
<br>
O problema dá uma temperatura em Celsius na entrada e pede para que você imprima ela em Fahrenheit pela fórmula: <code>F = C * 9 / 5 + 32</code>.
<br>
<br>
<em>Raciocínio: Recebemos <code>C</code>. Precisamos aplicar exatamente essa fórmula matemática na nossa expressão de processamento.</em>
<br>
<br>
<div align="left">
<pre><code># Entrada
c = float(input())

# Processamento
f = c * 9 / 5 + 32

# Saída
print(f)</code></pre>
</div>
<br>
A precedência da linguagem garantiu que as divisões e multiplicações acontecessem antes da soma final.
<br>
<br>
<strong>Problema 2: Distância Absoluta</strong>
<br>
O programa informa a sua posição atual na reta numérica e a posição onde fica o tesouro. Você precisa imprimir quantos passos dará entre um ponto e outro.
<br>
<br>
<em>Raciocínio: Nós vamos subtrair uma posição da outra. Mas se a posição do tesouro for menor, daria um número negativo de passos. Como distância é sempre positiva, a função <code>abs()</code> é perfeita aqui.</em>
<br>
<br>
<div align="left">
<pre><code># Entrada
a, b = map(int, input().split())

# Processamento
distancia = abs(a - b)

# Saída
print(distancia)</code></pre>
</div>
<br>
<strong>Problema 3: Notas Descartadas</strong>
<br>
Você lê três notas do competidor na mesma linha. A regra diz que a pior (menor) nota é descartada e a sua nota oficial será a soma das duas melhores.
<br>
<br>
<em>Raciocínio: Para encontrar as duas maiores, podemos ordenar a lista de forma decrescente (do maior para o menor). Dessa forma, as duas maiores estarão bem no início da coleção.</em>
<br>
<br>
<div align="left">
<pre><code># Entrada
pontos = list(map(int, input().split()))

# Processamento
pontos_ordenados = sorted(pontos, reverse=True)
soma = pontos_ordenados[0] + pontos_ordenados[1]

# Saída
print(soma)</code></pre>
</div>
<br>
<hr>
<h2>Fechamento</h2>
Na Aula 01, nós aprendemos a receber dados, armazená-los em variáveis e exibi-los. Hoje, nós fechamos o ciclo: aprendemos a <strong>transformar</strong> esses dados.
<br>
<br>
Você pode organizar mentalmente as novas ferramentas assim:
<br>
<br>
<ul>
<li><strong>Para fazer cálculos matemáticos:</strong> <code>+</code>, <code>-</code>, <code>*</code>, <code>/</code>, <code>//</code>, <code>%</code> e <code>**</code></li>
<li><strong>Para analisar valores numéricos rapidamente:</strong> <code>abs()</code>, <code>min()</code>, <code>max()</code>, <code>sum()</code>, <code>pow()</code> e <code>round()</code></li>
<li><strong>Para lidar com textos e coleções:</strong> <code>len()</code>, <code>.strip()</code>, <code>.lower()</code>, <code>.replace()</code> e a família <code>sorted()</code>/<code>reversed()</code>.</li>
</ul>
<br>
Você agora já não é apenas alguém que lê valores e os exibe. Você já é capaz de criar pequenas lógicas que convertem a entrada exatamente no que os problemas de programação competitiva vão te pedir. Na próxima aula, vamos aprender a como fazer o nosso programa tomar decisões baseadas nesses resultados!
<br>
<br>
</div>
</div>
