# 2 - Como o Python vê o mundo

> Um comando muito utilizado é o `print()`. Ele escreve algo na saída padrão (no caso do Python, o console/tela)
> Formalmente o `print()` è:
> 
>  ```py
>   print(*objects, sep=' ', end='\n', file=sys.stdout)
>  ```
>  Onde:
> - _***objects:**_ lista de valores e/ou variáveis
> - _**sep = ' ':**_ caractere colocado entre cada valor escrito
> - _**end = '\n':**_ caractere usado no final da linha ('\n' pula a linha)
> - _**file = sys.stdout:**_ onde escrever as informações
>  
> Exemplos:  
> | PRINT | RESULTADO |
> | ----- | --------- |
> | print(1, 2, 3) | 1 2 3 |
> | print(1, 2, 3, sep=';') | 1;2;3 |

## Variáveis

O ato de declarar uma variável é: 
- (1) Reservar um espaço na memória RAM (Random Acess Memory).
- (2) Associar esse espaço a um identificador, ou seja, dar um nome a ele.

### Nomeação de variáveis
Assim como em outras linguagens, no Python, todo identificador:
- **Pode:**
  - **Começar com:** uma letra (caractere alfabético).
  - **Pode conter:** caracteres alfanuméricos (letra e números) e o "_" (underline).
  
- **Não pode:**
  - Espaço e caracteres especiais ("@", "-", "+", ".", "," ...).
  - _Palavras reservada_ (que possuem uso definido na linguagem), como: _for, if, int, print_ e entre outros.

O Python é case _sensitive_, ou seja, diferencia variáveis com letras minúsculas e maiúsculas. 
> Também, é aceito acentos em identificadores, mas não é recomendado para programadores.

> _**Escript 2.1:**_ case-sensitive
> ```py
> a = 1
> A = 5
> print('Variável a - Valor:', a)
> print('Variável A - Valor:', A)
> ```

**Tabela 2.1.** Nome de Identificadores
| Identificadores Válidos | Identificadores Inválidos |
| :---: | :---: |
| A | 1A |
| Nota1 | 1Nota |
| Media_Final | Média Final
| Aluno | Aluno-Curso |
| a12b12 | a12/b12 |
| escreva | print |

> **Exercício 2.1.** Explique os erros de sintaxe dos identificadores inválidos na Rabela 2.1.

> **Exercício 2.2.** Marque com um X os identificadores válidos no Python.
> | Coluna 1 | Coluna 2 | Coluna 3 |
> | --- | --- | --- |
> | [ ] media | [ ] x2 | [ ] xYZ |
> | [ ] salario-min | [ ] Km/h | [ ] W_12 |
> | [ ] Nome Carro | [ ] 4x4 | [ ] Alun@s |
> | [ ] SalaQ | [ ] "Média Final" | [ ] A13bq2_1 |

> **Exercício 2.3.** Classifique corretamente o tipo de cada uma das variáveis:
> 1. Salario_Minimo
> 2. Nome_Aluno
> 3. Sexo_Masculino
> 4. idade
> 5. Cidade_Natal
> 6. Hora_Consulta
> 7. Codigo_Curso
> 8. Peso
> 9. Ano_Nascimento

### Tipos de variáveis
A linguagem Python é _Dinâmicamente Tipada_. Significa que toda variável possui seu tipo alterado durante a execução do _script_, sendo o interpretador que decide.
> _**Escript 2.2:**_ tipos
 ```py
 a = 1       # Inteiro
 a = 1.0     # Float
 a = "1"     # String
 a = True    # Booleano
 a = 3+12j   # Número complexo
 ```

> "#" (quadrilha) indica um comentário, tudo que o seguir, até o fim da linha, será ignorado pelo interpretador.  
> "\```" (crase) para comentar mais de uma linha, exemplo: \``` código ```.

**Tabela 2.2.** Tipos de Variáveis
| Tipo | Exemplo |
| --- | :---: |
| Booleano _(Bool)_ | True, False |
| Inteiro _(Int)_ | 1 |
| Ponto Flutuante _(Float)_ | 1.23 |
| Número complexo _(Complex)_ | 3+5x |
| String _(Str)_ | "12" |

### Operadores aritméticos

Para operações aritméticas simoles o Python possui:
| **Operador** | **Descrição** |
| :----------: | ------------- |
| + | Soma |
| - | Subtração |
| * | Multiplicação |
| / | Divisão |
| // | Divisor de inteiros | 
| % | Retorna o resto de uma  divisão de inteiros |
| ** | Exponenciação |

Execute o exemplo:
```py
a = 1.0         # a vale 1
b = a + 1       # soma
c = b - 3.0     # subtração
d = b / 2       # divisão
e = a % b       # resto de divisão (retorna o resto da divisão em inteiro)
f = b ** 2      # exponenciação (em outras linguagens é: b^2)
g = b * 7       # multiplicação
h = g // 3      # Divisão que retorna a parte inteira

print(a, b, c, d, e, f, g, h)
```

No _script_ 2.4, é exemplificado o uso das operações de divisão e resto para saber quantas notas de cada tipo são necessárias para um caixa dar troco, que, no caso, são R$ 135,00 reais. No exemplo há muitas parte que se repetem, peguemos a referente as notas de R$ 100,00:

- Na linha 3, é calculado a divisão entre o troco por 100 e pego a parte inteira dessa divisão, sendo ela, a quantidade de R$ 100,00 para serem entregues.
- Na linha 4, verifica-se o quanto sobrou para dar de troco, no caso, 35.

> **_Script 2.4:_** maquinatroco
```py
 troco = 135
 
notas100 = troco // 100
troco = troco % 100
print("Entregar ", notas100, "notas de R$ 100,00")

notas50 = troco // 50
troco = troco % 50
print("Entregar ", notas50, "notas de R$ 50,00")

notas20 = troco // 20
troco = troco % 20
print("Entregar ", notas20, "notas de R$ 20,00")

notas10 = troco // 10
troco = troco % 10
print("Entregar ", notas10, "notas de R$ 10,00")
 
notas5 = troco // 5
troco = troco % 5
print("Entregar ", notas5, "notas de R$ 5,00")

notas2 = troco // 2
troco = troco % 2
print("Entregar ", notas2, "notas de R$ 2,00")
```

> **Exercício 2.4:** Analise e execute o código, decubra quanto de cada notas será necessário para o troco.

### Operadores lógicos
Os operadores lógicos comparam variáveis e retornam um _valor lógico_ (tipo booleano), ou seja, True ou False.

**Tabela 2.4:** Operadores Lógicos
| **Operador** | **Descrição** |
| :----------: | ------------- |
| == | Igual |
| != | Diferente |
| < | Menor |
| > | Maior | 
| <= | Menor igual |
| >= | Maior igual |
| not | Negação |
| and | Operador E |
| or | Operador OU |

Expressões lógicas podem ser conectadas pelos operadores _and_ (as expressões devem ser verdadeiras para retornar True) e _or_ (pelo menos uma expressão deve ser verdadeira para retornar True). O operador _not_ nega o resultado de uma expressão, retornando um valor contrário, se comparar True retorna False, se comparar False retorna True.

> **_Script 2.5:_** operadoreslogicos.py
```py
A = 10
B = 15
C = 10

print("O valor da variável A é igual ao valor de B - ", A == B)
print("O valor da variável A é igual ao valor de C - ", A == C)
print("O valor da variável A é maior que o valor de C - ", A > C)
print("O valor da variável A não é igual ao valor de C - ", A != C)
print("O valor da variável A não é igual ao valor de C - ", not A == B)
print("O valor da variável A é igual ao valor de C e menor que B - ", A == C and A > B)
print("O valor da variável A é igual ao valor de C ou menor que B - ", A == C or A > B)
print("O valor da variável A + 5 é igual ou maior que B - ", A+5 >= B)
```

### Múltiplas atribuições
O python permite atribuir multiplos valores numa única linha.

```py
a, b = 2, 1
# a recebe 2
# b recebe 1

a, b = b, a   # Troca de valores
```

### Atribuições condicionais
Outra forma de atribuir valores a variáveis em Python é a atribuição condicional.

```py
# Atribui 1 para a variável a
a = 1

# Se a for maior que 0, atribui o valor 2 para a variável b. Senão, atribui 0
b = 2 if a > 0 else 0

# Atribui uma mensagem diferente para m conforme o valor de a
m = "Baixo" if a < 5 else "Alto"
```

## Entrada de dados

Programas normalmente possuem as etapas de _entrada_, _processamento_ e _saída de dados_. Um uso comum para entrada de dados em Python é usando a função `input`, que recebe um texto do teclado (num tipo de dado chamado _string_). 

Porém o tipo _string_ não é o ideal para certos processamentos, como operações aritméticas, para isso são usados métodos _tradutores_:
```py
idade = int(input("Qual sua idade? "))
print(idade)    # ex: 18

salario = float(input("Qual o seu salário? "))
print(salario)  # 1500.0

idade_string = str(idade)
print(idade_string) # "18"

numero_complexo = complex(idade + 1j)
print(numero_complexo)  # 18+1j

valor_bool = bool(numero_complexo)
print(valor_bool)   # True
```

## Strings
O tipo _string_ no Python é uma instância (um objeto) de uma classe chamada _string_. De forma simples, uma classe é uma estrutura computacional que possui dados e funções (atributos e métodos).

### Concatenação
Concatenação é juntar um ou mais strings ("juntar" texto), comumente usando o operador "+".

```py
artigo = 'A '
substantivo = 'floresta '
verbo = 'é '
adjetivo = 'harmoniosa'

frase = artigo + substantivo + verbo + adjetivo
print(frase)
```

### Substrings
_Substrings_ são "pedaços" de um texto maior, uma _string_. No python elas são representadas pelo operador [ ], com ele é possível acessar caracteres em conjunto de caracteres a partir de parâmetros de referência dentro do vetor.

O formato é `Parte = Todo[inicio : fim]`, onde _Todo_ é a _string_ original, _Parte_ o trecho selecionado de _Todo_, _inicio_ e _fim_ delimitam os trechos a serem extraídos. Tanto _inicio_ e _fim_ são valores numéricos e podem estar armazenados em variáveis, delimitam a parte da _string_ a ser extraída.

Quando os valores _inicio_ e _fim_ forem vazios, será atribuído a _inicio_ o valor zero e a _fim_ o maior ìndice da _string_. Quando esses parâmetros forem negativos a referência ou a ordem são determinados pelo tamanho da cadeia de caracteres 

