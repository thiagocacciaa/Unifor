# UNIFOR
**Nome**: Nome do estudante <br>
**Disciplina**: Raciocínio lógico algorítmo

## Exercício exemplo 1
Implemente e teste um programa que imprima os n primeiros números.

#### Fluxograma
```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número: }}
B --> C[\n\]
C --> D[\num = 1\]
D --> E{num <= n}
E --FALSE--> I([FIM])
E --TRUE--> F{{"Num", num}}
F --> G[num =+ 1]
G --LOOP--> E
```

#### Pseudocódigo
```
1 ALGORITMO print_n_primeiros
2 DECLARE n, num: INTEIRO
3 INICIO
4 ESCREVA “Digite um número: ”
4 LEIA n			// variável de entrada n
4 num ← 1			// variável num inicializada
5 ENQUANTO num <= n FAÇA	// n iterações
7	ESCREVA “Número ”, num
8	num ← num + 1		// num =+ 1 (incremento)
8 FIM_ENQUANTO
9 FIM
```

#### Teste de mesa
| it | n  | num | num <= n | Saída      | num =+ 1 |
| -- | -- | --  | --       | --         | --       |
| 1  | 10 | 1   | True     | Número 1   | 2        |
| 2  | 10 | 2   | True     | Número 2   | 3        |
| 3  | 10 | 3   | True     | Número 3   | 4        |
| 4  | 10 | 4   | True     | Número 4   | 5        |
| 5  | 10 | 5   | True     | Número 5   | 6        |
| 6  | 10 | 6   | True     | Número 6   | 7        |
| 7  | 10 | 7   | True     | Número 7   | 8        |
| 8  | 10 | 8   | True     | Número 8   | 9        |
| 9  | 10 | 9   | True     | Número 9   | 10       |
| 10 | 10 | 11  | True     | Número 10  | 11       |
| 11 | 10 | 11  | False    |            |          |

## Exercício exemplo 2
Implemente e teste um programa que some os n primeiros números.

#### Fluxograma
```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número: }}
B --> C[\n\]
C --> D[\soma = 0\]
D --> E[[i=1 ATÉ n PASSO 1]]
E --FALSE--> G([FIM])
E --TRUE--> F[soma =+ i]
F --LOOP--> E
```

#### Pseudocódigo
```
1  ALGORITMO	soma_n_numeros()
2  DECLARE	n, i, soma: INTEIRO
3  INICIO
4  ESCREVA “Digite a quantidade de números: ”
5  LEIA n		// variável de entrada n
7  soma ← 0		// variável soma inicializada
6  PARA i DE 1 ATÉ n PASSO 1 FAÇA
7	soma ← soma + i	// soma =+ i (incremento)
8  FIM_PARA
9  ESCREVA “A soma é igual a ”, soma
10 FIM
```

#### Teste de mesa
| it | n  | soma | i  | soma =+ i |
| -- | -- | --   | -- | --        |
| 1  | 10 | 0    | 1  | 1         |
| 2  | 10 | 1    | 2  | 3         |
| 3  | 10 | 3    | 3  | 6         |
| 4  | 10 | 6    | 4  | 10        |
| 5  | 10 | 10   | 5  | 15        |
| 6  | 10 | 15   | 6  | 21        |
| 7  | 10 | 21   | 7  | 28        |
| 8  | 10 | 28   | 8  | 36        |
| 9  | 10 | 36   | 9  | 45        |
| 10 | 10 | 45   | 10 | 55        | 

## Lista de exercícios 03

### Exercício 01 (2.5 pontos)
Atualize o algoritmo para determinar se um número inteiro e positivo é par ou ímpar, usando uma laço condicional para aceitar apenas números maiores ou iguais a zero. 

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número:}}
B --> C[\numero\]
C --> D{numero < 0}
D --TRUE--> E[O número não é positivo!]
E --> Z([FIM])
D --FALSE--> F[resto = numero % 2]
F --> G{resto == 0}
G --FALSE--> H{{O número é ímpar!}}
G --TRUE--> I{{O número é par!}}
H --> Z
I --> Z
```

#### Pseudocódigo (1.0 ponto)

```
1 Algoritmo ExibeMultiplosDeTres
2  DECLARE numero, resto: INTEIRO
3  INICIO
4  ESCREVA "Digite um número: "
5  LEIA numero
6  SE numero < 0 ENTÃO
7    ESCREVA "O número não é positivo!"
8  SENÃO
9    resto ← numero % 2
10   SE resto == 0 ENTÃO
11     ESCREVA "O número é par!"
12   SENÃO
13     ESCREVA "O número é ímpar!"
14   FIM_SE
15 FIM_SE
16 ESCREVA "FIM"
17 FIM_ALGORITMO
```

#### Teste de mesa (0.5 ponto)

| it | numero | resto | Mensagem                       |
|----|--------|-------|--------------------------------|
| 1  | -5     | -1    | O número não é positivo!       |
| 2  | -4     | 0     | O número não é positivo!       |
| 3  | -3     | -1    | O número não é positivo!       |
| 4  | -2     | 0     | O número não é positivo!       |
| 5  | -1     | -1    | O número não é positivo!       |
| 6  | 0      | 0     | O número é par!                |
| 7  | 1      | 1     | O número é ímpar!              |
| 8  | 2      | 0     | O número é par!                |
| 9  | 3      | 1     | O número é ímpar!              |
| 10 | 4      | 0     | O número é par!                |
| 11 | 5      | 1     | O número é ímpar!              |

### Exercício 02 (2.5 pontos)
Faça um algoritmo que exiba na tela uma contagem de 0 até 30, exibindo apenas os múltiplos de 3.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Contagem de Múltiplos de 3}}
B --> C{{Inicializar contador i = 0}}
C --> D{i <= 30}
D --TRUE--> E{ i é múltiplo de 3?}
E --TRUE--> F{Exibir i}
F --> G{Incrementar i}
G --> C
E --FALSE--> G
D --FALSE--> Z([FIM])
```

#### Pseudocódigo (1.0 ponto)

```
1  Algoritmo ExibeMultiplosDeTres
2  DECLARE i: INTEIRO
3  INICIO
4  ESCREVA "Contagem de Múltiplos de 3"
5  i ← 0
6  ENQUANTO i <= 30 FAÇA
7    SE i % 3 == 0 ENTÃO
8      ESCREVA i
9    FIM_SE
10   i ← i + 1
11 FIM_ENQUANTO
12 ESCREVA "FIM"
13 FIM_ALGORITMO
```

#### Teste de mesa (0.5 ponto)

| it | numero | resto | Mensagem           |
|----|--------|-------|--------------------|
| 1  | 0      | 0     | 0                  |
| 2  | 1      | 1     | (não exibido)      |
| 3  | 2      | 2     | (não exibido)      |
| 4  | 3      | 0     | 3                  |
| 5  | 4      | 1     | (não exibido)      |
| 6  | 5      | 2     | (não exibido)      |
| 7  | 6      | 0     | 6                  |
| 8  | 7      | 1     | (não exibido)      |
| 9  | 8      | 2     | (não exibido)      |
| 10 | 9      | 0     | 9                  |
| 11 | 10     | 1     | (não exibido)      |
| 12 | 11     | 2     | (não exibido)      |
| 13 | 12     | 0     | 12                 |
| 14 | 13     | 1     | (não exibido)      |
| 15 | 14     | 2     | (não exibido)      |
| 16 | 15     | 0     | 15                 |
| 17 | 16     | 1     | (não exibido)      |
| 18 | 17     | 2     | (não exibido)      |
| 19 | 18     | 0     | 18                 |
| 20 | 19     | 1     | (não exibido)      |
| 21 | 20     | 2     | (não exibido)      |
| 22 | 21     | 0     | 21                 |
| 23 | 22     | 1     | (não exibido)      |
| 24 | 23     | 2     | (não exibido)      |
| 25 | 24     | 0     | 24                 |
| 26 | 25     | 1     | (não exibido)      |
| 27 | 26     | 2     | (não exibido)      |
| 28 | 27     | 0     | 27                 |
| 29 | 28     | 1     | (não exibido)      |
| 30 | 29     | 2     | (não exibido)      |
| 31 | 30     | 0     | 30                 |


### Exercício 03 (2.5 pontos)
Dada uma sequência de números inteiros, calcular a sua soma. 
Por exemplo, para a sequência {12, 17, 4, -6, 8, 0}, o seu programa deve escrever o número 35.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Inicializar soma = 0}}
B --> C{{Inicializar index i = 0}}
C --> D{i < tamanho da sequência?}
D --TRUE--> E{Adicionar número na soma}
E --> F{Incrementar i}
F --> G{Verificar se i < tamanho da sequência}
G --> D
D --FALSE--> H{Exibir soma}
H --> Z([FIM])

```

#### Pseudocódigo (1.0 ponto)

```
1  Algoritmo CalcularSoma
2  DECLARE sequencia: LISTA DE INTEIROS
3  DECLARE soma, i: INTEIRO
4  INICIO
5    sequencia ← {12, 17, 4, -6, 8, 0}
6    soma ← 0
7    i ← 0
8    ENQUANTO i < TAMANHO(sequencia) FAÇA
9      soma ← soma + sequencia[i]
10     i ← i + 1
11   FIM_ENQUANTO
12   ESCREVA soma
13 FIM_ALGORITMO

```

#### Teste de mesa (0.5 ponto)

| it | sequencia             | soma |
|----|-----------------------|------|
| 1  | {12, 17, 4, -6, 8, 0} | 35   |
| 2  | {1, 2, 3, 4, 5}       | 15   |
| 3  | {-10, -5, 0, 5, 10}   | 0    |
| 4  | {100, -50, 25, 75}    | 150  |
| 5  | {7, 14, 21, 28, 35}   | 105  |


### Exercício 04 (2.5 pontos)
Escreva um programa que leia a nota de diversos alunos, até que seja digitada uma nota negativa. 
Nesse momento, ele mostra a média aritmética de todas as notas lidas e quantas notas foram lidas. 
Ex. Foram lidas 14 notas. A média aritmética é 6.75!

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Leitura de Notas}}
B --> C{{Inicializar soma = 0}}
C --> D{{Inicializar contador de notas = 0}}
D --> E{Leitura da próxima nota}
E --> F{Nota negativa?}
F --TRUE--> G{Calcular média e exibir resultados}
G --> Z([FIM])
F --FALSE--> H{Adicionar nota à soma e incrementar contador}
H --> D
```

#### Pseudocódigo (1.0 ponto)

```
1  Algoritmo CalcularMediaNotas
2  DECLARE nota, soma, contador: INTEIRO
3  INICIO
4    soma ← 0
5    contador ← 0
6    ESCREVA "Digite as notas dos alunos (digite uma nota negativa para encerrar):"
7    LEIA nota
8    ENQUANTO nota >= 0 FAÇA
9      soma ← soma + nota
10     contador ← contador + 1
11     LEIA nota
12   FIM_ENQUANTO
13   SE contador > 0 ENTÃO
14     media ← soma / contador
15     ESCREVA "Foram lidas ", contador, " notas. A média aritmética é ", media, "!"
16   SENÃO
17     ESCREVA "Nenhuma nota foi lida!"
18   FIM_SE
19 FIM_ALGORITMO
```

#### Teste de mesa (0.5 ponto)

| it | nota | soma | contador | média | Mensagem                                            |
|----|------|------|----------|-------|-----------------------------------------------------|
| 1  | 12   | 12   | 1        | -     | (não exibido - soma e contador inicializados)      |
| 2  | 17   | 29   | 2        | -     | (não exibido - soma e contador atualizados)        |
| 3  | 4    | 33   | 3        | -     | (não exibido - soma e contador atualizados)        |
| 4  | -6   | 33   | 3        | -     | (não exibido - nota negativa)                      |
| 5  | -    | 33   | 3        | -     | Foram lidas 3 notas. A média aritmética é 11.0!    |
