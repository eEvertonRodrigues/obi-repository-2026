<div style="max-width: 550px; margin: 0 auto;">
<div align="center">
<h1>Aula 05 - Vetores e Matrizes</h1>
<div style="border-left: 4px solid #FFD43B; background-color: #FFF8DC; padding: 12px 16px; margin: 15px 0; border-radius: 4px;">
Nesta aula, vamos aprender a armazenar e processar múltiplos valores relacionados usando vetores e matrizes estruturas que aparecem em praticamente todos os problemas de programação competitiva.
</div>
<img src="../../imagens/py_vector.png" alt="Python" width="250">
<br>
<h2>Por Que Precisamos de Vetores?</h2>
Até agora, para guardar informações usamos uma variável por dado:
<br>
<br>
<div align="left">
<pre><code>nota1 = 8
nota2 = 7
nota3 = 9
nota4 = 6
nota5 = 10</code></pre>
</div>
<br>
Isso funciona. Mas faça a si mesmo esta pergunta: <em>E se tivermos 100 notas?</em>
<br>
<br>
Criar 100 variáveis diferentes seria inviável. Mas o problema não é apenas a quantidade. Também queremos poder dizer ao computador: <em>"percorra todas as notas"</em>. Para isso, precisamos de uma única estrutura que reúna os valores e que possa ser percorrida. É aqui que entra o vetor.
<br>
<br>
<hr>
<h2>O Que é um Vetor?</h2>
Um vetor é uma sequência de valores guardados em uma única variável. Quando falamos em vetor neste curso, estamos usando uma <strong>lista Python</strong> (<code>list</code>) para representá-lo. A correspondência é direta:
<br>
<br>
<div align="left">
<pre><code>notas = [8, 7, 9, 6, 10]</code></pre>
</div>
<br>
Agora os cinco valores estão agrupados em uma única variável. Visualmente:
<br>
<br>
<div align="left">
<pre><code>notas
  ↓
[8, 7, 9, 6, 10]</code></pre>
</div>
<br>
<h3>Criando uma Lista Vazia</h3>
Nem sempre sabemos os valores de antemão. Muitas vezes precisamos construir o vetor aos poucos, a partir da entrada. Para isso, criamos uma lista vazia:
<br>
<br>
<div align="left">
<pre><code>vetor = []

print(vetor)
print(len(vetor))</code></pre>
</div>
<br>
Resultado:
<br>
<div align="left">
<pre><code>[]
0</code></pre>
</div>
<br>
<code>[]</code> representa uma lista sem nenhum elemento. Nesse momento, <code>len(vetor)</code> vale 0 e não existe <code>vetor[0]</code>. Também é possível escrever <code>vetor = list()</code>, que tem o mesmo efeito. Para o nível desta aula, <code>[]</code> é a forma mais simples e comum.
<br>
<br>
<hr>
<h2>Métodos Fundamentais de Listas</h2>
Uma lista não serve apenas para armazenar valores. Ela oferece operações para adicionar, remover, procurar e reorganizar elementos — todas através de <strong>métodos</strong>. Lembre-se da distinção da Aula 02:
<br>
<br>
<ul>
<li><code>len(lista)</code> é uma função.</li>
<li><code>lista.append(...)</code> é um método da lista.</li>
</ul>
<br>
<h3>append()</h3>
<strong>Problema que resolve:</strong> quero adicionar um elemento ao final da lista.
<br>
<br>
<div align="left">
<pre><code>vetor = []

vetor.append(10)
vetor.append(20)
vetor.append(30)

print(vetor)</code></pre>
</div>
<br>
Estado da lista depois de cada operação:
<br>
<div align="left">
<pre><code>[]
[10]
[10, 20]
[10, 20, 30]</code></pre>
</div>
<br>
<code>append(x)</code> adiciona exatamente <strong>um elemento</strong> ao final — mesmo que esse elemento seja outra lista. Esse comportamento prepara o terreno para a comparação com <code>extend()</code>:
<br>
<br>
<div align="left">
<pre><code>numeros = [10, 20, 30]
numeros.append([40, 50])
print(numeros)</code></pre>
</div>
<br>
Resultado: <code>[10, 20, 30, [40, 50]]</code>. A lista <code>[40, 50]</code> entrou como um único elemento — não como dois valores separados.
<br>
<br>
<h3>extend()</h3>
<strong>Problema que resolve:</strong> quero adicionar vários elementos de outra coleção, um por um.
<br>
<br>
<div align="left">
<pre><code>numeros = [10, 20, 30]
numeros.extend([40, 50])
print(numeros)</code></pre>
</div>
<br>
Resultado: <code>[10, 20, 30, 40, 50]</code>.
<br>
<br>
A diferença com <code>append()</code> é fundamental:
<br>
<div align="left">
<pre><code>append([40, 50])
→ [10, 20, 30, [40, 50]]   # uma lista como elemento

extend([40, 50])
→ [10, 20, 30, 40, 50]     # cada elemento adicionado separadamente</code></pre>
</div>
<br>
<h3>insert()</h3>
<strong>Problema que resolve:</strong> quero adicionar um elemento em uma posição específica.
<br>
<br>
<div align="left">
<pre><code>numeros = [10, 20, 30]
numeros.insert(1, 99)
print(numeros)</code></pre>
</div>
<br>
Resultado: <code>[10, 99, 20, 30]</code>. O 99 foi colocado na posição 1 e os elementos à frente foram deslocados. <code>insert(0, x)</code> insere no início; <code>insert(len(lista), x)</code> insere no final.
<br>
<br>
<h3>remove()</h3>
<strong>Problema que resolve:</strong> quero remover um elemento pelo seu <em>valor</em>.
<br>
<br>
<div align="left">
<pre><code>numeros = [10, 20, 30, 20]
numeros.remove(20)
print(numeros)</code></pre>
</div>
<br>
Resultado: <code>[10, 30, 20]</code>. <code>remove(x)</code> procura e remove a <strong>primeira ocorrência</strong> do valor <code>x</code>. Se o valor não existir, causa <code>ValueError</code>.
<br>
<br>
<h3>pop()</h3>
<strong>Problema que resolve:</strong> quero remover um elemento pela sua <em>posição</em> e também receber o valor removido.
<br>
<br>
<div align="left">
<pre><code>numeros = [10, 20, 30, 40]

valor = numeros.pop()    # remove o último
print(valor)             # 40
print(numeros)           # [10, 20, 30]

valor2 = numeros.pop(1)  # remove o índice 1
print(valor2)            # 20
print(numeros)           # [10, 30]</code></pre>
</div>
<br>
Comparação essencial:
<br>
<div align="left">
<pre><code>remove(valor)   → "remova este valor"
pop(indice)     → "remova desta posição e me devolva o que estava lá"</code></pre>
</div>
<br>
<code>pop()</code> em lista vazia causa <code>IndexError</code>.
<br>
<br>
<h3>clear()</h3>
<div align="left">
<pre><code>numeros = [10, 20, 30]
numeros.clear()
print(numeros)</code></pre>
</div>
<br>
Resultado: <code>[]</code>. <code>clear()</code> remove todos os elementos da lista existente.
<br>
<br>
<h3>index()</h3>
<strong>Problema que resolve:</strong> quero saber em qual posição está a primeira ocorrência de um valor.
<br>
<br>
<div align="left">
<pre><code>nomes = ["Ana", "Bruno", "Carlos"]
posicao = nomes.index("Bruno")
print(posicao)</code></pre>
</div>
<br>
Resultado: <code>1</code>. Se o valor não existir, causa <code>ValueError</code>. Em listas com repetições, retorna a posição da <strong>primeira</strong> ocorrência.
<br>
<br>
<h3>count()</h3>
<strong>Problema que resolve:</strong> quero saber quantas vezes um valor aparece.
<br>
<br>
<div align="left">
<pre><code>numeros = [10, 20, 10, 30, 10]
print(numeros.count(10))</code></pre>
</div>
<br>
Resultado: <code>3</code>.
<br>
<br>
<div align="left">
<pre><code>index(x) → onde aparece pela primeira vez?
count(x) → quantas vezes aparece?</code></pre>
</div>
<br>
<h3>sort()</h3>
<div align="left">
<pre><code>numeros = [5, 2, 8, 1, 4]
numeros.sort()
print(numeros)</code></pre>
</div>
<br>
Resultado: <code>[1, 2, 4, 5, 8]</code>. <code>sort(reverse=True)</code> ordena em ordem decrescente.
<br>
<br>
A distinção entre <code>sort()</code> e <code>sorted()</code> é obrigatória:
<br>
<br>
<div align="left">
<pre><code>numeros = [5, 2, 8, 1, 4]

ordenado = sorted(numeros)

print(numeros)   # [5, 2, 8, 1, 4]  (original intacto)
print(ordenado)  # [1, 2, 4, 5, 8]  (nova lista)</code></pre>
</div>
<br>
<div align="left">
<pre><code>numeros.sort()   → altera a própria lista, não retorna nada útil
sorted(numeros)  → cria e retorna uma nova lista ordenada</code></pre>
</div>
<br>
<h3>reverse()</h3>
<div align="left">
<pre><code>numeros = [10, 20, 30, 40]
numeros.reverse()
print(numeros)</code></pre>
</div>
<br>
Resultado: <code>[40, 30, 20, 10]</code>. <code>reverse()</code> inverte a própria lista. Não confunda com a função <code>reversed()</code>, que produz uma sequência para ser percorrida (assunto da Aula 07).
<br>
<br>
<h3>copy()</h3>
<div align="left">
<pre><code>numeros = [10, 20, 30]
copia = numeros.copy()
copia.append(40)

print(numeros)   # [10, 20, 30]
print(copia)     # [10, 20, 30, 40]</code></pre>
</div>
<br>
<code>copy()</code> cria uma nova lista com os mesmos elementos. Alterações na cópia não afetam a original.
<br>
<br>
<h3>Cuidado: métodos que modificam a lista retornam None</h3>
Esse é um erro muito comum. Veja:
<br>
<br>
<div align="left">
<pre><code>numeros = [3, 1, 2]

resultado = numeros.sort()

print(resultado)  # None
print(numeros)    # [1, 2, 3]</code></pre>
</div>
<br>
<div style="border-left: 4px solid #FFD43B; background-color: #FFF8DC; padding: 12px 16px; margin: 15px 0; border-radius: 4px;">
Métodos como <code>append()</code>, <code>sort()</code>, <code>reverse()</code>, <code>remove()</code> e <code>clear()</code> modificam a lista diretamente e <strong>não retornam</strong> a lista modificada. Nunca escreva <code>lista = lista.sort()</code>, pois a variável passará a valer <code>None</code>.
</div>
<br>
<h3>Tabela-Resumo dos Métodos</h3>
<table border="1" style="width:100%; border-collapse:collapse; text-align:left;">
<tr><th>Método</th><th>Para que serve</th></tr>
<tr><td><code>append(x)</code></td><td>Adiciona <code>x</code> ao final</td></tr>
<tr><td><code>extend(lista)</code></td><td>Adiciona vários elementos individualmente</td></tr>
<tr><td><code>insert(i, x)</code></td><td>Insere <code>x</code> na posição <code>i</code></td></tr>
<tr><td><code>remove(x)</code></td><td>Remove a primeira ocorrência de <code>x</code></td></tr>
<tr><td><code>pop()</code></td><td>Remove e retorna o último elemento</td></tr>
<tr><td><code>pop(i)</code></td><td>Remove e retorna o elemento da posição <code>i</code></td></tr>
<tr><td><code>clear()</code></td><td>Remove todos os elementos</td></tr>
<tr><td><code>index(x)</code></td><td>Posição da primeira ocorrência de <code>x</code></td></tr>
<tr><td><code>count(x)</code></td><td>Conta quantas vezes <code>x</code> aparece</td></tr>
<tr><td><code>sort()</code></td><td>Ordena a própria lista</td></tr>
<tr><td><code>reverse()</code></td><td>Inverte a própria lista</td></tr>
<tr><td><code>copy()</code></td><td>Cria uma cópia da lista</td></tr>
</table>
<br>
<hr>
<h2>Índices</h2>
Cada posição do vetor possui um número identificador chamado <strong>índice</strong>. O ponto mais importante: <strong>Python começa a contar a partir do 0</strong>.
<br>
<br>
<div align="left">
<pre><code>índice positivo:

  0   1   2   3   4
  ↓   ↓   ↓   ↓   ↓
[ 8   7   9   6  10 ]</code></pre>
</div>
<br>
<h3>Índices Negativos</h3>
Python também permite acessar elementos contando a partir do final, com índices negativos:
<br>
<br>
<div align="left">
<pre><code>índice negativo:

 -5  -4  -3  -2  -1
  ↓   ↓   ↓   ↓   ↓
[ 8   7   9   6  10 ]</code></pre>
</div>
<br>
<div align="left">
<pre><code>notas[-1]  # 10 (último)
notas[-2]  # 6  (penúltimo)
notas[-3]  # 9
notas[-4]  # 7
notas[-5]  # 8 (primeiro)</code></pre>
</div>
<br>
A relação matemática: o índice <code>-k</code> corresponde ao índice positivo <code>len(lista) - k</code>. Por exemplo, <code>-1</code> corresponde a <code>5 - 1 = 4</code>.
<br>
<br>
<div style="border-left: 4px solid #FFD43B; background-color: #FFF8DC; padding: 12px 16px; margin: 15px 0; border-radius: 4px;">
<strong>A lista NÃO é circular.</strong> Para <code>notas = [8, 7, 9, 6, 10]</code>, os índices negativos válidos são apenas <code>-1</code> a <code>-5</code>. Tentar <code>notas[-6]</code> causa <code>IndexError</code>, exatamente como <code>notas[5]</code> — em ambos os casos, a posição não existe.
<br><br>
Índices negativos apenas mudam o ponto de referência (do final em vez do início). Eles não criam posições novas.
</div>
<br>
<hr>
<h2>Acessando e Alterando Elementos</h2>
<div align="left">
<pre><code>notas = [8, 7, 9, 6, 10]

print(notas[0])   # 8
print(notas[4])   # 10</code></pre>
</div>
<br>
Assim como podemos alterar o valor de uma variável, podemos alterar uma posição do vetor:
<br>
<br>
<div align="left">
<pre><code>notas[1] = 10
print(notas)</code></pre>
</div>
<br>
<div align="left">
<pre><code>antes:  [8,  7, 9, 6, 10]
depois: [8, 10, 9, 6, 10]</code></pre>
</div>
<br>
<hr>
<h2>len() e Percorrendo um Vetor</h2>
A função <code>len()</code> retorna a quantidade de elementos:
<br>
<br>
<div align="left">
<pre><code>notas = [8, 7, 9, 6, 10]
print(len(notas))  # 5</code></pre>
</div>
<br>
Na aula anterior aprendemos a repetir uma operação. Agora vamos repetir uma operação <em>sobre vários dados</em>. O <code>for</code> se encaixa naturalmente:
<br>
<br>
<div align="left">
<pre><code>for nota in notas:
    print(nota)</code></pre>
</div>
<br>
Use essa forma quando precisar apenas dos <strong>valores</strong>. Quando precisar também da <strong>posição</strong>, combine <code>range()</code> com <code>len()</code>:
<br>
<br>
<div align="left">
<pre><code>for i in range(len(notas)):
    print(i, notas[i])</code></pre>
</div>
<br>
Como há 5 elementos, <code>range(len(notas))</code> equivale a <code>range(5)</code>, fornecendo os índices <code>0, 1, 2, 3, 4</code> — exatamente as posições válidas do vetor.
<br>
<br>
<hr>
<h2>Entrada de um Vetor</h2>
Em competições, o vetor virá da entrada. O padrão típico:
<br>
<br>
<div align="left">
<pre><code>n = int(input())
vetor = list(map(int, input().split()))</code></pre>
</div>
<br>
<code>input().split()</code> divide a linha nos espaços. <code>map(int, ...)</code> converte cada parte para inteiro. <code>list(...)</code> agrupa tudo em um vetor. Para a entrada:
<br>
<div align="left">
<pre><code>5
8 7 9 6 10</code></pre>
</div>
Obtemos: <code>[8, 7, 9, 6, 10]</code>.
<br>
<br>
<hr>
<h2>Padrões de Processamento em Vetores</h2>
Os mesmos padrões estudados com laços se aplicam diretamente a vetores.
<br>
<br>
<h3>Contador</h3>
<div align="left">
<pre><code>numeros = [3, 8, 2, 9, 4, 6, 1]
contador = 0

for numero in numeros:
    if numero % 2 == 0:
        contador += 1

print(contador)</code></pre>
</div>
<br>
<h3>Acumulador</h3>
<div align="left">
<pre><code>soma = 0

for numero in numeros:
    soma += numero

media = soma / len(numeros)
print(soma, media)</code></pre>
</div>
<br>
<h3>Maior e Menor Elemento</h3>
Começamos assumindo que o maior é o primeiro elemento. Se inicializássemos com <code>0</code> e todos os números fossem negativos, o resultado seria incorreto.
<br>
<br>
<div align="left">
<pre><code>maior = numeros[0]

for numero in numeros:
    if numero &gt; maior:
        maior = numero

print(maior)</code></pre>
</div>
<br>
<h3>Busca</h3>
<div align="left">
<pre><code>alvo = 9
encontrou = False

for numero in numeros:
    if numero == alvo:
        encontrou = True
        break

print(encontrou)</code></pre>
</div>
<br>
A variável <code>encontrou</code> funciona como uma bandeira (<em>flag</em>). O <code>break</code> evita continuar buscando depois de encontrar.
<br>
<br>
<h3>Posição de um Elemento</h3>
<div align="left">
<pre><code>alvo = 9

for i in range(len(numeros)):
    if numeros[i] == alvo:
        print(i)
        break</code></pre>
</div>
<br>
<code>numeros[i]</code> é o valor; <code>i</code> é a posição.
<br>
<br>
<hr>
<h2>Vetor de Strings</h2>
Os elementos de um vetor não precisam ser números:
<br>
<br>
<div align="left">
<pre><code>nomes = ["Ana", "Bruno", "Carlos"]

for nome in nomes:
    print(nome)</code></pre>
</div>
<br>
<code>nomes[0]</code> acessa <code>"Ana"</code>. Os mesmos padrões de percurso, busca e acesso se aplicam.
<br>
<br>
<hr>
<h2>Vetor de Vetores Vazios</h2>
Antes de avançar para matrizes, é importante perceber que uma lista pode guardar outras listas:
<br>
<br>
<div align="left">
<pre><code>vetor = [[], [], []]</code></pre>
</div>
<br>
<div align="left">
<pre><code>vetor
  ↓
[ [], [], [] ]
   ↑   ↑   ↑
   0   1   2</code></pre>
</div>
<br>
<code>vetor[0]</code> é uma lista vazia. Podemos adicionar elementos a ela:
<br>
<br>
<div align="left">
<pre><code>vetor[0].append(10)
vetor[1].append(20)
vetor[2].append(30)

print(vetor)  # [[10], [20], [30]]</code></pre>
</div>
<br>
Podemos criar o mesmo resultado dinamicamente com <code>append()</code>:
<br>
<br>
<div align="left">
<pre><code>vetor = []

for _ in range(3):
    vetor.append([])

print(vetor)  # [[], [], []]</code></pre>
</div>
<br>
Essa é a base estrutural de uma matriz: uma lista cujos elementos são outras listas.
<br>
<br>
<hr>
<h2>Introdução às Matrizes</h2>
Se temos uma lista contendo listas, podemos usar cada lista interna como uma linha. Quando essas linhas possuem elementos, temos naturalmente uma matriz.
<br>
<br>
Imagine uma tabela:
<br>
<br>
<div align="left">
<pre><code>1 2 3
4 5 6
7 8 9</code></pre>
</div>
<br>
Em Python, representamos isso como uma <strong>lista de listas</strong>:
<br>
<br>
<div align="left">
<pre><code>matriz = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]</code></pre>
</div>
<br>
A matriz geral é uma lista. Cada elemento que está lá dentro é outra lista, representando uma <strong>linha</strong>. A transição que fizemos antes — uma lista de listas vazias — é exatamente a mesma estrutura, só que agora preenchida.
<br>
<br>
<h3>Linhas e Colunas</h3>
A matriz acima é 3×3: 3 linhas, 3 colunas. Mas matrizes não precisam ser quadradas:
<br>
<br>
<div align="left">
<pre><code>matriz = [
    [1, 2, 3, 4],
    [5, 6, 7, 8]
]</code></pre>
</div>
<br>
Essa possui 2 linhas e 4 colunas.
<br>
<br>
<ul>
<li><code>len(matriz)</code> → quantidade de <strong>linhas</strong></li>
<li><code>len(matriz[0])</code> → quantidade de <strong>colunas</strong> (tamanho da primeira linha)</li>
</ul>
<br>
Nunca use <code>len(matriz)</code> para as duas dimensões — isso só seria correto para matrizes quadradas.
<br>
<br>
<h3>Acessando Elementos: matriz[linha][coluna]</h3>
<div align="left">
<pre><code>          coluna
         0  1  2

linha 0  1  2  3
linha 1  4  5  6
linha 2  7  8  9</code></pre>
</div>
<br>
<ul>
<li><code>matriz[0]</code> → primeira linha inteira: <code>[1, 2, 3]</code></li>
<li><code>matriz[0][0]</code> → primeiro elemento da primeira linha: <code>1</code></li>
<li><code>matriz[1][2]</code> → segunda linha, terceira coluna: <code>6</code></li>
</ul>
<br>
A fórmula <code>matriz[linha][coluna]</code> deve ser memorizada. Os índices começam em 0 para linhas e colunas.
<br>
<br>
<h3>Alterando Elementos</h3>
<div align="left">
<pre><code>matriz[1][2] = 99</code></pre>
</div>
<br>
<div align="left">
<pre><code>antes:   1 2 3 / 4 5  6 / 7 8 9
depois:  1 2 3 / 4 5 99 / 7 8 9</code></pre>
</div>
<br>
<hr>
<h2>Percorrendo uma Matriz</h2>
No vetor, um laço percorre os elementos. Na matriz, dois laços aninhados percorrem linhas e colunas — exatamente o padrão que estudamos na aula anterior.
<br>
<br>
<div align="left">
<pre><code>for i in range(len(matriz)):
    for j in range(len(matriz[0])):
        print(matriz[i][j])</code></pre>
</div>
<br>
O laço externo (<code>i</code>) avança pelas linhas. O laço interno (<code>j</code>) percorre todas as colunas daquela linha. O laço interno completa antes de o externo avançar:
<br>
<br>
<div align="left">
<pre><code>i = 0 (linha 0)
    j = 0, 1, 2

i = 1 (linha 1)
    j = 0, 1, 2
...</code></pre>
</div>
<br>
Quando não precisar das posições, use o <code>for</code> diretamente:
<br>
<br>
<div align="left">
<pre><code>for linha in matriz:
    for elemento in linha:
        print(elemento)</code></pre>
</div>
<br>
<hr>
<h2>Leitura de Matriz</h2>
O padrão típico de competição, agora conectado ao <code>append()</code> que aprendemos:
<br>
<br>
<div align="left">
<pre><code>n, m = map(int, input().split())

matriz = []

for _ in range(n):
    linha = list(map(int, input().split()))
    matriz.append(linha)</code></pre>
</div>
<br>
A lógica: criamos a matriz vazia, lemos cada linha da entrada, e adicionamos com <code>append()</code>. Para a entrada:
<br>
<div align="left">
<pre><code>2 3
1 2 3
4 5 6</code></pre>
</div>
A matriz construída será <code>[[1, 2, 3], [4, 5, 6]]</code>.
<br>
<br>
<hr>
<h2>Padrões de Processamento em Matrizes</h2>
Os mesmos padrões de vetores se aplicam. A única diferença é que agora dois laços alcançam todos os elementos.
<br>
<br>
<h3>Soma de Todos os Elementos</h3>
<div align="left">
<pre><code>soma = 0

for i in range(len(matriz)):
    for j in range(len(matriz[0])):
        soma += matriz[i][j]

print(soma)</code></pre>
</div>
<br>
<h3>Soma por Linha</h3>
O ponto pedagógico vital: o acumulador precisa ser reiniciado para cada nova linha.
<br>
<br>
<div align="left">
<pre><code>for i in range(len(matriz)):
    soma_linha = 0
    for j in range(len(matriz[0])):
        soma_linha += matriz[i][j]
    print(soma_linha)</code></pre>
</div>
<br>
<div align="left">
<pre><code>linha 0 → soma começa em 0 → acumula
linha 1 → soma começa novamente em 0 → acumula</code></pre>
</div>
<br>
<h3>Maior Elemento e Posição</h3>
No vetor, guardávamos uma posição. Na matriz, guardamos duas.
<br>
<br>
<div align="left">
<pre><code>maior = matriz[0][0]
linha_m = 0
coluna_m = 0

for i in range(len(matriz)):
    for j in range(len(matriz[0])):
        if matriz[i][j] &gt; maior:
            maior = matriz[i][j]
            linha_m = i
            coluna_m = j

print(maior, linha_m, coluna_m)</code></pre>
</div>
<br>
<hr>
<h2>Diagonais</h2>
<h3>Diagonal Principal</h3>
Em uma matriz quadrada, a diagonal principal vai do topo-esquerdo à base-direita:
<br>
<br>
<div align="left">
<pre><code>1 2 3
4 5 6
7 8 9

Diagonal principal: 1, 5, 9</code></pre>
</div>
<br>
Na diagonal principal, <strong>linha == coluna</strong>: <code>matriz[0][0]</code>, <code>matriz[1][1]</code>, <code>matriz[2][2]</code>. Por isso, basta um laço:
<br>
<br>
<div align="left">
<pre><code>soma = 0
for i in range(len(matriz)):
    soma += matriz[i][i]</code></pre>
</div>
<br>
<h3>Diagonal Secundária</h3>
A diagonal secundária vai do topo-direito à base-esquerda (3, 5, 7 no exemplo).
<br>
<br>
Enquanto <code>i</code> vai de 0 a 2, a coluna vai de 2 a 0. Para uma matriz de tamanho <code>n</code>, a coluna é sempre <code>n - 1 - i</code>:
<br>
<br>
<div align="left">
<pre><code>n = len(matriz)
soma = 0

for i in range(n):
    soma += matriz[i][n - 1 - i]</code></pre>
</div>
<br>
<hr>
<h2>Transposta</h2>
Na transposta, linhas viram colunas e colunas viram linhas:
<br>
<br>
<div align="left">
<pre><code>Original:      Transposta:
1 2 3          1 4
4 5 6          2 5
               3 6</code></pre>
</div>
<br>
O laço externo passa pelas <strong>colunas</strong> da original, pois cada coluna se tornará uma nova linha:
<br>
<br>
<div align="left">
<pre><code>linhas = len(matriz)
colunas = len(matriz[0])

transposta = []

for j in range(colunas):
    nova_linha = []
    for i in range(linhas):
        nova_linha.append(matriz[i][j])
    transposta.append(nova_linha)</code></pre>
</div>
<br>
<hr>
<h2>Armadilha Crítica na Criação de Matrizes</h2>
A forma abaixo parece criar uma matriz, mas é problemática:
<br>
<br>
<div align="left">
<pre><code>matriz = [[0] * 3] * 3

matriz[0][0] = 99
print(matriz)</code></pre>
</div>
<br>
O resultado surpreendente:
<br>
<div align="left">
<pre><code>[[99, 0, 0], [99, 0, 0], [99, 0, 0]]</code></pre>
</div>
<br>
Por quê? O operador <code>* 3</code> repete a <strong>mesma lista interna</strong> três vezes. É como escrever:
<br>
<br>
<div align="left">
<pre><code>linha = [0, 0, 0]
matriz = [linha, linha, linha]  # todas apontam para o mesmo objeto!</code></pre>
</div>
<br>
Alterar <code>matriz[0][0]</code> altera essa lista compartilhada — e todas as "linhas" são afetadas. A forma correta cria listas internas independentes:
<br>
<br>
<div align="left">
<pre><code>matriz = [[0 for _ in range(colunas)] for _ in range(linhas)]</code></pre>
</div>
<br>
<hr>
<h2>Problemas Integradores</h2>
<strong>Problema 1: Contar pares no vetor</strong>
<br>
<em>Percorrer o vetor, usar if para verificar condição, contar.</em>
<br>
<div align="left">
<pre><code>contador = 0
for numero in vetor:
    if numero % 2 == 0:
        contador += 1
print(contador)</code></pre>
</div>
<br>
<strong>Problema 2: Soma e média do vetor</strong>
<br>
<em>Acumular valores, dividir por len().</em>
<br>
<div align="left">
<pre><code>soma = 0
for numero in vetor:
    soma += numero
media = soma / len(vetor)
print(soma, media)</code></pre>
</div>
<br>
<strong>Problema 3: Maior elemento e posição no vetor</strong>
<br>
<em>Percorrer com índice, guardar a posição do maior.</em>
<br>
<div align="left">
<pre><code>maior = vetor[0]
posicao = 0
for i in range(len(vetor)):
    if vetor[i] &gt; maior:
        maior = vetor[i]
        posicao = i
print(maior, posicao)</code></pre>
</div>
<br>
<strong>Problema 4: Busca de valor X no vetor</strong>
<br>
<em>Flag + break para interromper ao encontrar.</em>
<br>
<div align="left">
<pre><code>alvo = int(input())
encontrou = False
for numero in vetor:
    if numero == alvo:
        encontrou = True
        break
print(encontrou)</code></pre>
</div>
<br>
<strong>Problema 5: Soma de todos os elementos da matriz</strong>
<br>
<em>Dois laços aninhados + acumulador.</em>
<br>
<div align="left">
<pre><code>soma = 0
for i in range(len(matriz)):
    for j in range(len(matriz[0])):
        soma += matriz[i][j]
print(soma)</code></pre>
</div>
<br>
<strong>Problema 6: Soma de cada linha da matriz</strong>
<br>
<em>Acumulador reiniciado a cada linha.</em>
<br>
<div align="left">
<pre><code>for i in range(len(matriz)):
    soma_linha = 0
    for j in range(len(matriz[0])):
        soma_linha += matriz[i][j]
    print(soma_linha)</code></pre>
</div>
<br>
<strong>Problema 7: Maior elemento da matriz e posição</strong>
<br>
<em>Extensão direta do maior em vetor — agora com i e j.</em>
<br>
<div align="left">
<pre><code>maior = matriz[0][0]
li, co = 0, 0
for i in range(len(matriz)):
    for j in range(len(matriz[0])):
        if matriz[i][j] &gt; maior:
            maior = matriz[i][j]
            li, co = i, j
print(maior, li, co)</code></pre>
</div>
<br>
<strong>Problema 8: Somas das diagonais</strong>
<br>
<em>Um único laço com os dois índices espelhados.</em>
<br>
<div align="left">
<pre><code>n = len(matriz)
sp, ss = 0, 0
for i in range(n):
    sp += matriz[i][i]
    ss += matriz[i][n - 1 - i]
print(sp, ss)</code></pre>
</div>
<br>
<strong>Problema 9: Transposta da matriz</strong>
<br>
<em>Laço externo pelas colunas, interno pelas linhas.</em>
<br>
<div align="left">
<pre><code>linhas = len(matriz)
colunas = len(matriz[0])
transposta = []
for j in range(colunas):
    nova_linha = []
    for i in range(linhas):
        nova_linha.append(matriz[i][j])
    transposta.append(nova_linha)</code></pre>
</div>
<br>
<hr>
<h2>Erros Comuns</h2>
<h3>Em Vetores</h3>
<ul>
<li><strong>Índice começa em 0:</strong> o primeiro elemento é <code>vetor[0]</code>, não <code>vetor[1]</code>.</li>
<li><strong>Índice inexistente:</strong> acessar <code>vetor[len(vetor)]</code> causa <code>IndexError</code>.</li>
<li><strong>Confundir valor com posição:</strong> <code>i</code> é a posição; o valor é <code>vetor[i]</code>.</li>
<li><strong>Não inicializar contador/acumulador:</strong> declare sempre <code>soma = 0</code> antes do laço.</li>
<li><strong>Inicializar maior com 0:</strong> use <code>vetor[0]</code>; se todos os valores forem negativos, 0 seria incorreto.</li>
<li><strong>Imaginar que a lista é circular:</strong> <code>lista[-6]</code> numa lista de 5 elementos causa erro.</li>
<li><strong>Confundir <code>append()</code> com <code>extend()</code>:</strong> <code>append([1,2])</code> adiciona uma lista como um único elemento; <code>extend([1,2])</code> adiciona dois elementos.</li>
<li><strong>Confundir <code>remove()</code> com <code>pop()</code>:</strong> <code>remove()</code> recebe valor; <code>pop()</code> recebe índice.</li>
<li><strong>Atribuir resultado de <code>sort()</code>:</strong> <code>lista = lista.sort()</code> faz a variável virar <code>None</code>.</li>
</ul>
<br>
<h3>Em Matrizes</h3>
<ul>
<li><strong>Inverter linha e coluna:</strong> a sintaxe é sempre <code>matriz[linha][coluna]</code>.</li>
<li><strong>Usar um único laço:</strong> para visitar todos os elementos, são necessários dois laços.</li>
<li><strong>Usar <code>len(matriz)</code> como colunas:</strong> use <code>len(matriz[0])</code> para colunas.</li>
<li><strong>Esquecer de reiniciar o acumulador por linha.</strong></li>
<li><strong>Inicializar maior com 0:</strong> use <code>matriz[0][0]</code>.</li>
<li><strong>Criar matriz com <code>[[0]*m]*n</code>:</strong> as linhas compartilham a mesma lista interna.</li>
</ul>
<br>
<hr>
<h2>Resumo da Aula</h2>
<ul>
<li><strong>Vetor</strong> → sequência de valores em uma única variável (<code>list</code>).</li>
<li><strong>Índice</strong> → posição de um elemento, começando em 0. Índices negativos contam do final.</li>
<li><strong><code>append()</code> / <code>extend()</code></strong> → um elemento vs. vários elementos adicionados.</li>
<li><strong><code>remove(x)</code></strong> → remove pelo valor. <strong><code>pop(i)</code></strong> → remove e retorna pela posição.</li>
<li><strong><code>sort()</code></strong> → modifica a lista. <strong><code>sorted()</code></strong> → retorna nova lista.</li>
<li><strong>Percorrer</strong> → <code>for x in lista</code> (valor) ou <code>for i in range(len(lista))</code> (valor + posição).</li>
<li><strong>Matriz</strong> → lista de listas; cada lista interna é uma linha.</li>
<li><strong><code>matriz[i][j]</code></strong> → elemento da linha <code>i</code>, coluna <code>j</code>.</li>
<li><strong>Laços aninhados</strong> → ferramenta natural para percorrer matrizes.</li>
<li><strong>Diagonal principal</strong> → <code>matriz[i][i]</code>.</li>
<li><strong>Diagonal secundária</strong> → <code>matriz[i][n-1-i]</code>.</li>
<li><strong>Transposta</strong> → linhas e colunas trocadas.</li>
<li><strong>Armadilha <code>[[0]*m]*n</code></strong> → cria linhas compartilhadas; use list comprehension.</li>
</ul>
<br>
<div style="border-left: 4px solid #FFD43B; background-color: #FFF8DC; padding: 12px 16px; margin: 15px 0; border-radius: 4px;">
<strong>Checklist antes de resolver um problema:</strong>
<br><br>
- O que preciso armazenar?<br>
- Quantos valores existem?<br>
- Preciso da posição ou apenas do valor?<br>
- Estou contando ou acumulando?<br>
- Preciso encontrar maior/menor?<br>
- Preciso buscar algum elemento?<br>
- Se for matriz, preciso percorrer linhas e colunas?<br>
- O resultado por linha exige reinicialização do acumulador?
</div>
<br>
<br>
</div>
</div>
