# UNIFOR
**Nome**: Nome do estudante <br>
**Disciplina**: Raciocínio lógico algorítmico

## Lista de exercícios 01

### Exercício 01 (1 ponto)
Represente, em fluxograma e pseudocódigo, um algoritmo para determinar se um número inteiro e positivo é par ou impar.

#### Fluxograma (0,25 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número:}}
B --> C[\numero\]
C --> D{numero >= 0}
D --FALSE--> E[O número não é positivo!]
D --TRUE--> F[resto = numero % 2]
E --> Z([FIM])
F --> G{resto == 0}
G --FALSE--> H{{O número é impar!}}
G --TRUE--> I{{O número é par!}}
H --> Z
I --> Z
```

#### Pseudocódigo (0,5 ponto)
```
1  ALGORTIMO verifica_par_impar   //titulo do algoritimo
2  DECLARE numero, resto: INTEIRO   //declara os seguintes elementos como variavel INTEIRO
3  ESCREVA "Digite um número: "    //escreve uma frase pedindo entrada do valor de numero
4  INICIO   //inicio do algoritimo
4  LEIA numero    //faz a leitura da entrada
5  SE numero >= 0 ENTAO                  // verifica se o inteiro é positivo
6    resto = numero % 2                 // calcula o resto da divisão por 2
7    SE resto == 0 ENTAO                // verifica se o resto é igual a zero
8      ESCREVA "O número é par!"     // escreve a seguinte mensagem
9    SENAO     //incio SENAO
10     ESCREVA "O número é impar!"     // escreve a seguinte mensagem
11   FIM_SE      //fim da ferramenta SE
11  SENAO                                // caso inteiro for negativo (condição linha 5)
12    ESCREVA "O número deve ser postivo!"     //escreve a frase
13  FIM_SE      //fim da ferramenta SE
13 FIM     //fim do algoritimo
```


#### Teste de mesa (0,25 ponto)
| numero | numero >= 0 | resto | resto == 0 | Saída |
| -- | -- | -- | -- | -- | 
| -1 | F |   |   | "O número deve ser postivo!" |
| 0  | V | 0 | V | "O número é par!" |
| 13 | V | 1 | F | "O número é impar!" |
| 30 | V | 0 | V | "O número é par!" |

## Exercício 02 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular o novo salário de um funcionário. 
Sabe-se que os funcionários que recebem atualmente salário de até R$ 500 terão aumento de 20%; os demais terão aumento de 10%.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
    A([INICIO]) --> B{{Digite o salário atual:}}
    B --> C[\salario\]
    C --> D{Salario <= 500?}
    D --TRUE--> E{Novo_salario = Salario * 1.20}
    D --FALSE--> F{Novo_salario = Salario * 1.10}
    E --> G{{Exibir Novo_salario}}
    F --> G{{Exibir Novo_salario}}
    G --> H([FIM])

```

#### Pseudocódigo (1.0 ponto)

```
ALGORITMO CalcularNovoSalario
1. DECLARE salario, novo_salario: REAL  //titulo do algoritimo
2. INICIO    //inicio do algoritimo
3.   ESCREVA "Digite o salário atual: "    //entrada do valor de salario
4.   LEIA salario    //leitura do valor de salario
5.   SE salario <= 500 ENTÃO    //inicio ferramenta SE 
6.     novo_salario <- salario * 1.20   //atribui uma equacao ao elemento "novo_salario"
7.   SENÃO   //incio da ferraenta SENAO
8.     novo_salario <- salario * 1.10   //atribui uma equacao ao elemento "novo_salario"
9.   FIM_SE    //fim da ferramenta SE
10.  ESCREVA "O novo salário é: ", novo_salario    //exibe valor do elemento
11. FIM_ALGORITMO  //fim do algoritimo

```

#### Teste de mesa (1.0 ponto)

| it |	salario |	salario <= 500 |	novo_salario |
| -- | -- | -- | -- |
| 1	 |    400	  |  VERDADEIRO	   |      480      |
| 2	 |    800	  |     FALSO	     |      880      |
| 3  |    500   |  VERDADEIRO    |      600      |
## Exercício 03 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular a média aritmética entre duas notas de um aluno e mostrar sua situação, que pode ser aprovado ou reprovado.

#### Fluxograma (1 ponto)

```mermaid
flowchart TD
    A([INICIO]) --> B{{Digite a primeira nota:}}
    B --> C[\nota1\]
    C --> D{{Digite a segunda nota:}}
    D --> E[\nota2\]
    E --> F{Calcular a média = nota1 + nota2 / 2}
    F --> G{Se média >= 6}
    G --TRUE--> H{{Aluno aprovado!}}
    G --FALSE--> I{{Aluno reprovado!}}
    H --> J([FIM])
    I --> J([FIM])

```

#### Pseudocódigo (1 ponto)

```
ALGORITMO CalcularMediaEStatus    //titulo do algoritimo
1. INÍCIO     //inicio do algoritimo
2.     ESCREVA "Digite a primeira nota: "    //entrada de nota1
3.     LEIA nota1      //leitura de nota1
4.     ESCREVA "Digite a segunda nota: "   //entrada de nota2
5.     LEIA nota2       //leitura de nota2
6.     media <- (nota1 + nota2) / 2     //atribui uma equacao coo valor de "media"
7.     SE media >= 6 ENTÃO    //incio ferramenta SE
8.         ESCREVA "Aluno aprovado!"    //escreve frase
9.     SENÃO    //inicio SENAO
10.        ESCREVA "Aluno reprovado!"   //escreve frase
11.    FIM_SE     //fim ferramenta SE
12. FIM_ALGORITMO     //fi do algoritimo

```

#### Teste de mesa (1 ponto)

| it |	nota1 |	nota2 |	media | situacao  |
| -- | -- | -- | -- | -- |
| 1	 |   7.5	|  8.0	| 7.75	| Aprovado  |
| 2	 |   6.0	|  5.5	| 5.75	| Reprovado |
| 3	 |   4.0	|  6.0	| 5.0	  | Reprovado |

## Exercício 04 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo que, a partir da idade do candidato(a), determinar se pode ou não tirar a CNH. 
Caso não atender a restrição de idade, calcular quantos anos faltam para o candidato estar apto.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
    A([INICIO]) --> B{{Digite a idade do candidato: }}
    B --> C[\idade\]
    C --> D{idade >= 18?}
    D --TRUE--> E{{Candidato pode tirar a CNH}}
    D --FALSE--> F{anos faltantes = 18 - idade}
    F --> G{{"Faltam 18 - idade, anos para tirar a CNH"}}
    G --> H([FIM])
    E --> H

```

#### Pseudocódigo (1.0 ponto)

```
1  ALGORITMO VerificarCNH    //titulo do algoritimo
2      DECLARE idade, anos_faltantes: INTEIRO    //declara elementos como INTEIRO
3      INICIO    //incio algoritimo
4      ESCREVA "Digite a idade do candidato: "   //entrada do valor de "idade"
5      LEIA idade     //leitura do valor de "idade"
6      
7      SE idade >= 18 ENTÃO   //inicio ferramenta SE
8          ESCREVA "Candidato pode tirar a CNH"    //escreve frase
9      SENÃO    //inicio SENAO
10         anos_faltantes <- 18 - idade   //atribui equacao como valor do elemento
11         ESCREVA "Faltam ", anos_faltantes, " anos para tirar a CNH"     //exibe valor do elemento 
12     FIM_SE   //fim ferraenta SE
13     
14     ESCREVA "FIM"    //escreve frase
15 FIM_ALGORITMO   //fim do algoritimo

```

#### Teste de mesa (1.0 ponto)

| it |	idade | anos_faltantes |	Mensagem                       |
| -- | -- | -- | -- |
| 1	 |   20	  |      -         |	Candidato pode tirar a CNH     |
| 2	 |   16	  |      2	       |  Faltam 2 anos para tirar a CNH |
| 3	 |   18	  |      -         |	Candidato pode tirar a CNH     |
