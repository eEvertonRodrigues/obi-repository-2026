<div style="max-width: 550px; margin: 0 auto;">
<div align="center">
<h1>Aula 01 - Variáveis e Tipos</h1>
<div style="border-left: 4px solid #FFD43B; background-color: #FFF8DC; padding: 12px 16px; margin: 15px 0; border-radius: 4px;">
Nesta aula, você vai entender como Python armazena e gerencia valores durante a execução de um programa. Vamos explorar variáveis, tipos de dados, operações e as regras que governam como esses elementos interagem entre si.
</div>
<img src="../../imagens/py_vector.png" alt="Python" width="250">
<br>
<h2>Retomando a Aula 00</h2>
Na aula anterior, você aprendeu a utilizar <code>input()</code> para receber dados e <code>print()</code> para exibir resultados. Com isso, já é possível construir a estrutura básica de um programa:
<br>
<br>
<div align="left">
<pre><code>Entrada → Processamento → Saída</code></pre>
</div>
<br>
<br>
Para que o processamento seja possível, precisamos de um mecanismo para <strong>armazenar informações</strong> durante a execução do programa — valores que possam ser lidos, transformados e utilizados em diferentes momentos. É aqui que entram as <strong>variáveis</strong>.
<br>
<br>
<hr>
<h2>Variáveis</h2>
<h3>O que é uma variável?</h3>
De maneira intuitiva, uma variável é um <strong>nome que utilizamos para acessar um valor</strong> durante a execução do programa. Sempre que precisarmos daquele valor, basta utilizar o nome.
<br>
<br>
<div align="left">
<pre><code>nome = "João"
idade = 20</code></pre>
</div>
<br>
<br>
Os valores <code>"João"</code> e <code>20</code> escritos diretamente no código são chamados de <strong>literais</strong>. Um literal é simplesmente um valor que aparece explicitamente no programa — como <code>3.14</code>, <code>"Python"</code>, <code>True</code> ou <code>0</code>. Quando atribuímos um literal a uma variável, estamos associando aquele valor a um nome que poderemos utilizar posteriormente.
<br>
<br>
Depois de armazenado, o valor pode ser utilizado várias vezes:
<br>
<br>
<div align="left">
<pre><code>idade = 20
print(idade)
print(idade + 1)</code></pre>
</div>
<br>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>20
21</code></pre>
</div>
<br>
<br>
<h3>Atribuição</h3>
O símbolo <code>=</code> em Python representa uma <strong>atribuição</strong>, e não uma igualdade matemática. Quando escrevemos <code>idade = 20</code>, estamos dizendo ao Python: <em>"associe o valor 20 ao nome idade"</em>.
<br>
<br>
Uma nova atribuição substitui o valor anteriormente associado ao nome:
<br>
<br>
<div align="left">
<pre><code>idade = 20
idade = 21
print(idade)</code></pre>
</div>
<br>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>21</code></pre>
</div>
<br>
<br>
O valor final é <code>21</code> porque a segunda atribuição fez com que o nome <code>idade</code> passasse a representar o novo valor.
<br>
<br>
<h3>Atribuição vs. comparação: <code>=</code> e <code>==</code></h3>
Uma confusão muito comum para quem está começando é entre <code>=</code> e <code>==</code>. São operadores completamente diferentes:
<br>
<br>
<div align="left">
<pre><code>x = 10      # atribuição: associa o valor 10 ao nome x
x == 10     # comparação: verifica se x possui o valor 10</code></pre>
</div>
<br>
<br>
O primeiro é uma <strong>atribuição</strong> — ele altera o estado do programa. O segundo é uma <strong>expressão de comparação</strong> — ele produz <code>True</code> ou <code>False</code> como resultado, sem alterar nada. Estudaremos <code>==</code> com mais profundidade quando abordarmos operadores e estruturas condicionais.
<br>
<br>
<hr>
<h2>Tipagem Dinâmica</h2>
Em Python, os valores possuem tipos e o tipo de cada valor é determinado durante a execução do programa. Não precisamos declarar previamente o tipo de uma variável antes de utilizá-la — o Python cuida disso automaticamente. Esse comportamento é chamado de <strong>tipagem dinâmica</strong>.
<br>
<br>
Podemos verificar o tipo de um valor utilizando a função <code>type()</code>:
<br>
<br>
<div align="left">
<pre><code>idade = 20
print(type(idade))</code></pre>
</div>
<br>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>&lt;class 'int'&gt;</code></pre>
</div>
<br>
<br>
O nome <code>idade</code> está associado ao valor <code>20</code>, que é um número inteiro. Por isso, seu tipo é <code>int</code>.
<br>
<br>
Uma característica importante da tipagem dinâmica é que o mesmo nome pode passar a estar associado a um valor de outro tipo:
<br>
<br>
<div align="left">
<pre><code>valor = 10
print(type(valor))

valor = "Olá"
print(type(valor))</code></pre>
</div>
<br>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>&lt;class 'int'&gt;
&lt;class 'str'&gt;</code></pre>
</div>
<br>
<br>
É comum dizer que <em>"a variável mudou de tipo"</em>, mas uma forma mais precisa de pensar é que <strong>o nome passou a estar associado a um valor de outro tipo</strong>. Em Python, não precisamos declarar que <code>valor</code> será sempre um inteiro ou sempre uma string.
<br>
<br>
<div align="left">
<pre><code>x = 10
x = "dez"
x = 3.14</code></pre>
</div>
<br>
<br>
O mesmo nome pode ser reutilizado para valores de tipos diferentes ao longo da execução.
<br>
<br>
<hr>
<h2>Principais Tipos de Dados</h2>
Ao longo do curso, trabalharemos principalmente com quatro tipos de dados:
<br>
<br>
<div align="left">
<pre><code>idade = 20        # int
altura = 1.75     # float
nome = "João"     # str
aprovado = True   # bool</code></pre>
</div>
<br>
<br>
<strong>int</strong> — representa números inteiros, como <code>10</code>, <code>0</code> e <code>-5</code>. Não possui parte decimal.
<br>
<br>
<strong>float</strong> — representa números de ponto flutuante, como <code>3.14</code>, <code>1.75</code> e <code>-2.5</code>. Possui parte decimal.
<br>
<br>
<strong>str</strong> — representa textos. Pode ser escrito entre aspas simples ou duplas: <code>"Python"</code> ou <code>'Python'</code>.
<br>
<br>
<strong>bool</strong> — representa valores booleanos. Só possui dois valores possíveis: <code>True</code> ou <code>False</code>. Esse tipo será especialmente importante quando estudarmos estruturas condicionais.
<br>
<br>
Um detalhe que pode causar confusão: <code>True</code> e <code>"True"</code> são coisas completamente diferentes.
<br>
<br>
<div align="left">
<pre><code>print(True)
print("True")
print(type(True))
print(type("True"))</code></pre>
</div>
<br>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>True
True
&lt;class 'bool'&gt;
&lt;class 'str'&gt;</code></pre>
</div>
<br>
<br>
Embora a aparência na tela seja parecida, <code>True</code> é um valor booleano (<code>bool</code>), enquanto <code>"True"</code> é um texto (<code>str</code>). A aparência do conteúdo não determina o tipo do valor.
<br>
<br>
Podemos utilizar <code>type()</code> para inspecionar o tipo de qualquer valor:
<br>
<br>
<div align="left">
<pre><code>print(type(idade))
print(type(altura))
print(type(nome))
print(type(aprovado))</code></pre>
</div>
<br>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>&lt;class 'int'&gt;
&lt;class 'float'&gt;
&lt;class 'str'&gt;
&lt;class 'bool'&gt;</code></pre>
</div>
<br>
<br>
<div style="border-left: 4px solid #FFD43B; background-color: #FFF8DC; padding: 12px 16px; margin: 15px 0; border-radius: 4px;">
<code>type()</code> é uma função útil para inspeção e aprendizado. Em competições, raramente você precisará utilizá-la em uma solução final — mas ela é muito valiosa enquanto você está aprendendo e quer verificar com qual tipo está trabalhando.
</div>
<br>
<h3>O valor <code>None</code></h3>
Além dos quatro tipos principais, existe um valor especial em Python chamado <code>None</code>. Ele representa a <strong>ausência de um valor</strong> — a ideia de que, naquele momento, não existe um valor disponível para determinada variável.
<br>
<br>
<div align="left">
<pre><code>resultado = None
print(type(resultado))</code></pre>
</div>
<br>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>&lt;class 'NoneType'&gt;</code></pre>
</div>
<br>
<br>
Você encontrará <code>None</code> em diversas situações ao longo do curso. Por ora, basta saber que ele existe e que representa "nenhum valor".
<br>
<br>
<hr>
<h2>O Tipo Influencia as Operações</h2>
Um dos conceitos mais importantes desta aula é que <strong>o tipo de um valor influencia diretamente as operações que podem ser realizadas sobre ele</strong>.
<br>
<br>
Observe:
<br>
<br>
<div align="left">
<pre><code>print(22 + 11)</code></pre>
</div>
<br>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>33</code></pre>
</div>
<br>
<br>
Agora com strings:
<br>
<br>
<div align="left">
<pre><code>print("22" + "11")</code></pre>
</div>
<br>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>2211</code></pre>
</div>
<br>
<br>
No primeiro caso, <code>22</code> e <code>11</code> são inteiros e o operador <code>+</code> realiza uma <strong>soma numérica</strong>. No segundo, <code>"22"</code> e <code>"11"</code> são strings e o operador <code>+</code> realiza uma <strong>concatenação</strong>, juntando os dois textos.
<br>
<br>
O mesmo operador se comporta de maneiras completamente diferentes dependendo dos tipos envolvidos.
<br>
<br>
<h3>Operações entre tipos incompatíveis</h3>
O que acontece quando tentamos usar tipos incompatíveis na mesma operação?
<br>
<br>
<div align="left">
<pre><code>print("22" + 11)</code></pre>
</div>
<br>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>TypeError: can only concatenate str (not "int") to str</code></pre>
</div>
<br>
<br>
Python não sabe o que fazer: <code>"22"</code> é uma string e <code>11</code> é um inteiro. A operação <code>+</code> não está definida para essa combinação de tipos, e o programa encerra com um erro.
<br>
<br>
<div style="border-left: 4px solid #FFD43B; background-color: #FFF8DC; padding: 12px 16px; margin: 15px 0; border-radius: 4px;">
O tipo não é apenas uma informação descritiva sobre o valor. Ele determina quais operações podem ser realizadas e como elas se comportam. Ignorar os tipos envolvidos é uma das causas mais comuns de erros em programas Python.
</div>
<br>
A solução depende da <em>intenção</em> do programador. Se quiser realizar uma <strong>soma numérica</strong>:
<br>
<br>
<div align="left">
<pre><code>print(int("22") + 11)</code></pre>
</div>
<br>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>33</code></pre>
</div>
<br>
<br>
Se quiser <strong>juntar os valores como texto</strong>:
<br>
<br>
<div align="left">
<pre><code>print("22" + str(11))</code></pre>
</div>
<br>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>2211</code></pre>
</div>
<br>
<br>
<h3>Nem toda operação entre tipos diferentes é inválida</h3>
É importante não generalizar. Algumas operações entre tipos diferentes são perfeitamente válidas em Python:
<br>
<br>
<div align="left">
<pre><code>print("Python" * 3)</code></pre>
</div>
<br>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>PythonPythonPython</code></pre>
</div>
<br>
<br>
Multiplicar uma string por um inteiro é uma operação definida em Python: ela repete o texto pelo número de vezes indicado. Já:
<br>
<br>
<div align="left">
<pre><code>print("Python" - 3)</code></pre>
</div>
<br>
<br>
provocará um <code>TypeError</code>, pois a subtração entre uma string e um inteiro não está definida.
<br>
<br>
Python possui regras específicas para cada operador e para cada combinação de tipos. O correto é entender que <strong>determinadas operações são definidas para determinados tipos</strong> — e não memorizar simplesmente que "tipos diferentes não podem ser usados juntos".
<br>
<br>
<hr>
<h2>Conversão de Tipos</h2>
Quando a conversão é possível e necessária, Python oferece funções para converter valores entre tipos:
<br>
<br>
<div align="left">
<pre><code>print(int("22"))      # 22
print(float("3.14"))  # 3.14
print(str(22))        # "22"</code></pre>
</div>
<br>
<br>
Algumas conversões, porém, podem causar erros:
<br>
<br>
<div align="left">
<pre><code>int("abc")</code></pre>
</div>
<br>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>ValueError: invalid literal for int() with base 10: 'abc'</code></pre>
</div>
<br>
<br>
O texto <code>"abc"</code> não representa um número inteiro válido, e por isso a conversão falha.
<br>
<br>
Outra conversão importante de entender:
<br>
<br>
<div align="left">
<pre><code>print(int(3.9))</code></pre>
</div>
<br>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>3</code></pre>
</div>
<br>
<br>
<code>int()</code> <strong>não arredonda</strong> o número — ele descarta a parte decimal. O resultado de <code>int(3.9)</code> é <code>3</code>, e não <code>4</code>.
<br>
<br>
<h3>Conectando com <code>input()</code></h3>
Retomando o que foi visto na <a href="../00%20-%20Introdução%20a%20Python/Introdução%20a%20Python.md">Aula 00</a>: <code>input()</code> <strong>sempre</strong> retorna uma string, independentemente do que o usuário digitou.
<br>
<br>
<div align="left">
<pre><code>idade = input()</code></pre>
</div>
<br>
<br>
Se o usuário digitar <code>22</code>, o valor recebido será a string <code>"22"</code>, e não o inteiro <code>22</code>. Isso causa problemas quando tentamos utilizá-lo em operações numéricas:
<br>
<br>
<div align="left">
<pre><code>idade = input()
print(idade + 10)</code></pre>
</div>
<br>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>TypeError: can only concatenate str (not "int") to str</code></pre>
</div>
<br>
<br>
A forma correta é converter o valor antes de utilizá-lo:
<br>
<br>
<div align="left">
<pre><code>idade = int(input())
print(idade + 10)</code></pre>
</div>
<br>
<br>
O fluxo pode ser visualizado assim:
<br>
<br>
<div align="left">
<pre><code>input() → str → int() → int → operação</code></pre>
</div>
<br>
<br>
Esse padrão aparecerá constantemente em programação competitiva. Sempre que receber um número pela entrada, converta-o para o tipo adequado antes de utilizá-lo em cálculos.
<br>
<br>
<hr>
<h2>Anotações de Tipo</h2>
Python possui tipagem dinâmica e não exige que o programador declare o tipo das variáveis. Porém, a linguagem permite que você <em>indique</em> qual tipo de valor espera que uma variável contenha, por meio das chamadas <strong>anotações de tipo</strong> (ou <em>type hints</em>):
<br>
<br>
<div align="left">
<pre><code>idade: int = 20
nome: str = "João"
altura: float = 1.75
aprovado: bool = True</code></pre>
</div>
<br>
<br>
As partes <code>: int</code>, <code>: str</code>, <code>: float</code> e <code>: bool</code> são as anotações. Elas servem principalmente para <strong>documentar a intenção do programador</strong> e permitir que editores e ferramentas de análise possam identificar possíveis incompatibilidades.
<br>
<br>
Importante: a anotação <strong>não transforma Python em uma linguagem estaticamente tipada</strong>. O código abaixo ainda pode ser executado:
<br>
<br>
<div align="left">
<pre><code>idade: int = 20
idade = "vinte"</code></pre>
</div>
<br>
<br>
Python não impedirá a atribuição de uma string a <code>idade</code>, mesmo com a anotação indicando que esperávamos um <code>int</code>. A anotação funciona como uma <em>indicação</em> do tipo esperado — ferramentas de análise podem alertar sobre a incompatibilidade, mas o interpretador não gera um erro por conta disso.
<br>
<br>
<div style="border-left: 4px solid #FFD43B; background-color: #FFF8DC; padding: 12px 16px; margin: 15px 0; border-radius: 4px;">
Em programação competitiva, é muito comum optar pela forma mais enxuta:
<br>
<br>
<div align="left">
<pre><code>n = int(input())</code></pre>
</div>
<br>
em vez de:
<br>
<br>
<div align="left">
<pre><code>n: int = int(input())</code></pre>
</div>
<br>
Ambas são válidas. A primeira é preferida quando queremos escrever soluções rapidamente durante uma competição.
</div>
<br>
<hr>
<h2>Constantes por Convenção</h2>
Python não possui constantes verdadeiras — não existe um mecanismo que impeça que uma variável tenha seu valor alterado. Porém, existe uma <strong>convenção</strong> amplamente utilizada: valores que pretendemos tratar como constantes recebem nomes escritos em <strong>letras maiúsculas</strong>.
<br>
<br>
<div align="left">
<pre><code>PI = 3.14159
LIMITE = 100000
MOD = 1000000007</code></pre>
</div>
<br>
<br>
Escrever os nomes dessa maneira comunica ao programador que esses valores <strong>não deveriam ser alterados</strong> durante a execução. Em programação competitiva, valores como <code>MOD</code> aparecem com muita frequência.
<br>
<br>
Porém, é importante entender que isso é apenas uma convenção. Python ainda permite:
<br>
<br>
<div align="left">
<pre><code>PI = 3.14
PI = 4   # Python não impede essa reatribuição</code></pre>
</div>
<br>
<br>
Nenhum erro será gerado. A responsabilidade de respeitar a convenção é do programador.
<br>
<br>
<hr>
<h2>Reatribuição e Operadores de Atribuição</h2>
Uma variável pode receber um novo valor que depende do seu valor atual:
<br>
<br>
<div align="left">
<pre><code>x = 10
x = x + 5
print(x)</code></pre>
</div>
<br>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>15</code></pre>
</div>
<br>
<br>
O Python primeiro calcula o lado direito da atribuição (<code>x + 5</code> = <code>15</code>) e depois associa esse resultado novamente ao nome <code>x</code>.
<br>
<br>
Python oferece também <strong>operadores de atribuição</strong> que combinam uma operação com a atribuição:
<br>
<br>
<div align="left">
<pre><code>x += 5   # equivale a x = x + 5
x -= 2   # equivale a x = x - 2
x *= 3   # equivale a x = x * 3
x /= 2   # equivale a x = x / 2</code></pre>
</div>
<br>
<br>
Esses operadores são especialmente úteis quando precisamos acumular valores ou aplicar transformações repetidas a uma variável. Você os encontrará com frequência ao longo do curso.
<br>
<br>
<hr>
<h2>Cuidado com Nomes de Variáveis</h2>
Python possui diversas funções, tipos e outros nomes que já fazem parte do ambiente da linguagem. Um ponto importante é que esses nomes também podem ser sobrescritos pelo programador — e isso pode causar problemas silenciosos.
<br>
<br>
Considere a função <code>sum()</code>, que soma os valores de uma coleção numérica:
<br>
<br>
<div align="left">
<pre><code>print(sum([1, 2, 3]))</code></pre>
</div>
<br>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>6</code></pre>
</div>
<br>
<br>
Agora observe o que acontece se utilizarmos <code>sum</code> como nome de variável:
<br>
<br>
<div align="left">
<pre><code>sum = 10
print(sum([1, 2, 3]))</code></pre>
</div>
<br>
<br>
Saída:
<br>
<br>
<div align="left">
<pre><code>TypeError: 'int' object is not callable</code></pre>
</div>
<br>
<br>
Depois da atribuição, o nome <code>sum</code> passou a representar o número <code>10</code>, e não mais a função. Podemos visualizar assim:
<br>
<br>
<div align="left">
<pre><code># Antes da atribuição:
sum → função sum()
# Depois:
sum → 10</code></pre>
</div>
<br>
<br>
Quando escrevemos <code>sum([1, 2, 3])</code>, o Python tenta <em>chamar</em> o objeto associado ao nome <code>sum</code>. Como agora <code>sum</code> representa um inteiro, e inteiros não podem ser chamados como funções, ocorre o erro.
<br>
<br>
O mesmo problema pode acontecer com outros nomes importantes:
<br>
<br>
<div align="left">
<pre><code>list = [1, 2, 3]
# Agora list() como função pode não funcionar mais</code></pre>
</div>
<br>
<br>
<div style="border-left: 4px solid #FFD43B; background-color: #FFF8DC; padding: 12px 16px; margin: 15px 0; border-radius: 4px;">
Não é proibido utilizar nomes como <code>sum</code>, <code>list</code>, <code>str</code>, <code>int</code>, <code>float</code>, <code>len</code>, <code>max</code>, <code>min</code>, <code>input</code> ou <code>print</code> para variáveis. Mas fazer isso <strong>sobrescreve o acesso à função ou ao tipo correspondente</strong> naquele contexto. O princípio é simples: alguns nomes já possuem significados importantes em Python e devem ser utilizados com cuidado.
</div>
<br>
<hr>
<h2>Regras e Boas Práticas para Nomes</h2>
Nomes de variáveis em Python seguem algumas regras básicas:
<br>
<br>
— Podem conter <strong>letras</strong>, <strong>números</strong> e <strong>underscore</strong> (<code>_</code>).
<br>
— <strong>Não podem começar com um número</strong>.
<br>
— <strong>Não podem conter espaços</strong>.
<br>
— Python <strong>diferencia maiúsculas de minúsculas</strong>: <code>idade</code> e <code>Idade</code> são nomes completamente diferentes.
<br>
— Por convenção, nomes em <strong>letras maiúsculas</strong> (como <code>MOD</code>, <code>PI</code>, <code>LIMITE</code>) indicam constantes.
<br>
<br>
<div align="left">
<pre><code>idade = 20
Idade = 30
print(idade)   # 20
print(Idade)   # 30</code></pre>
</div>
<br>
<br>
Nomes descritivos facilitam a leitura e manutenção do código:
<br>
<br>
<div align="left">
<pre><code>nome_completo = "João Silva"
quantidade_de_alunos = 30</code></pre>
</div>
<br>
<br>
<div style="border-left: 4px solid #FFD43B; background-color: #FFF8DC; padding: 12px 16px; margin: 15px 0; border-radius: 4px;">
<strong>Observação para programação competitiva:</strong> em competições é comum utilizar nomes curtos como <code>n</code>, <code>m</code>, <code>a</code> e <code>b</code> quando eles correspondem diretamente à notação utilizada pelo problema. O importante é que o nome seja suficientemente claro dentro do contexto da solução.
</div>
<br>
<hr>
<h2>Variáveis e Tipos em uma Solução Real</h2>
Vamos ver como todos esses conceitos se manifestam em um problema simples de programação competitiva.
<br>
<br>
Suponha que a entrada forneça dois números inteiros em uma mesma linha e o programa deva imprimir a soma entre eles:
<br>
<br>
<div align="left">
<pre><code>a, b = map(int, input().split())
soma = a + b
print(soma)</code></pre>
</div>
<br>
<br>
Cada parte desse código envolve os conceitos desta aula:
<br>
<br>
— <code>input()</code> recebe os dados como uma string.
<br>
— <code>split()</code> separa os valores usando o espaço como delimitador.
<br>
— <code>map(int, ...)</code> converte cada valor de string para inteiro.
<br>
— <code>a</code> e <code>b</code> são variáveis que armazenam os números inteiros.
<br>
— <code>soma</code> armazena o resultado da operação <code>a + b</code>.
<br>
— <code>print(soma)</code> exibe o resultado na saída padrão.
<br>
<br>
O fluxo completo pode ser visualizado assim:
<br>
<br>
<div align="left">
<pre><code>Entrada → armazenamento em variáveis → processamento → saída</code></pre>
</div>
<br>
<br>
<div style="border-left: 4px solid #FFD43B; background-color: #FFF8DC; padding: 12px 16px; margin: 15px 0; border-radius: 4px;">
<code>map()</code> e <code>split()</code> serão explorados com mais profundidade em aulas futuras. Por ora, o importante é reconhecer seu papel nessa construção tão comum em programação competitiva.
</div>
<br>
<hr>
<h2>Fechamento</h2>
Ao longo desta aula, você aprendeu que:
<br>
<br>
— <strong>Variáveis</strong> são nomes utilizados para acessar valores durante a execução do programa.
<br>
— O operador <code>=</code> representa uma <strong>atribuição</strong>, não uma igualdade matemática.
<br>
— Python possui <strong>tipagem dinâmica</strong>: não é necessário declarar o tipo de uma variável.
<br>
— Um nome pode passar a representar valores de <strong>tipos diferentes</strong> ao longo da execução.
<br>
— Os principais tipos são <code>int</code>, <code>float</code>, <code>str</code> e <code>bool</code>.
<br>
— O <strong>tipo influencia as operações</strong> que podem ser realizadas sobre um valor.
<br>
— Valores recebidos por <code>input()</code> são <strong>sempre strings</strong> e frequentemente precisam ser convertidos.
<br>
— Podemos usar <strong>anotações de tipo</strong> para indicar o tipo esperado, mas elas não impedem atribuições incompatíveis.
<br>
— Devemos ter <strong>cuidado ao escolher nomes</strong> para variáveis, evitando sobrescrever funções e tipos importantes como <code>sum</code>, <code>list</code>, <code>int</code> e <code>str</code>.
<br>
<br>
<div style="border-left: 4px solid #FFD43B; background-color: #FFF8DC; padding: 12px 16px; margin: 15px 0; border-radius: 4px;">
Agora que você entende como armazenar valores e trabalhar com seus tipos, está pronto para o próximo passo: estudar de forma mais sistemática os <strong>operadores</strong> utilizados para realizar cálculos, comparações e construir expressões em Python.
</div>
<br>
<br>
</div>
</div>
