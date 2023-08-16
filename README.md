# Estrutura de dados II

## Revisao de estrutura de dados I

### O que é Estrutura de dados?

- Qualquer coisa que armazene dados
- Consegue armazenar o mesmo tipo de dados usando diferentes estruturas de dados ( pode ser melhor ou pior )

### Tipo de dado

Única coisa que o computador entende é binário. por isso é necessário uma abstração dos bits, e essa abstração é o tipo de dado. <span style="color: orange">Definição: O tipo de dado é um mecanismo para entender e manipular os bits que ficarão armazenados.</span> Os tipos de dados são:

- números ( inteiros, reais,... )
- Caracter

Idealmente, precisamos so de 2 tipos de dados acima, no entanto, fazemos uma troca por conta da limitação de memória, de espaço por precisão, por isso utilizamos diferentes tipos de dado. Exemplos:
- short int, int, long int
- float, double

<span style="color: orange">Esses tipos de dados usam uma quantidade menor de bits.<span>

TIpos de dados básicos , usando o padrão da linguagem C:

- Inteiro
    - Inteiros
    - Conjunto ( Esse tipo de dado é um tipo que você define quais são os valores aceitáveis para esse tipo de dado, ex.: "enum")
- Real
- Lógico
- Caractere

Os tipos de dados básicos não podem ser quebrados em tipos de dados menores.

A partir dos tipos de dados básicos, é possível criar outros tipos de dados:

- Não agregados
    - Ponteiro ( aponta para um tipo de dados (var, int, float, char))
    - Função
    - União ( como o registro, porém não podem ser usados tipos diferentes de dados )
- Agregados
    - Registro ( igual uniao, porém é possível colocar tipos de dados diferentes, ver exemplo)

Uniao:

```
union professor 
{
    int idade;
    char sexo;
    double salario;
};

union professor abrantes;
abrantes.idade = 49;

//ao usar um dos tipos de dados, a uniao "trava" para apenas o tipo de dado usado, ou seja, o seguinte sera impossivel:

abrantes.sexo = 'm'; //erro
```
Registro:
```
//essa eh a definicao
struct aluno
{
    int idade;
    char sexo;
    double mesalidade;
};

//criando uma variavel com esse tipo de dados
struct aluno nome_do_aluno;
nome_do_aluno.idade = 25;
nome_do_aluno.sexo = 'f';
nome_do_aluno.mensalidade = 200;
```
*As representações acima foram baseadas na linguagem C.*

Esses tipos de dados são usados como unidade.Quando o desejo é armazenar mais de uma unidade, devemos usar as seguintes estruturas de dados:

- Por Contiguidade ( dados armazenados em posições contiguas na memória, o tamanho máximo é definido previamente )
    - Array
    - Matriz
    - Heap
    - Tabela Hash
- Por Encadeamento ( os dados estão posicionados em posições aleatórias na memória, com ponteiros indicando seus endereços de memória )
    - Lista
    - Árvore
    - Grafo
- Hibrida
    - Essa estrutura que é uma mistura de estrutura contígua com estrutura encadeada. Se houver colisão em uma tabela hash(contigua), é usado um tipo de dado por encadeamento quando usamos o ponteiro para alocar o dado em outro endereço de memória.
    
#### Estrutura por Contiguidade
##### Vantagens:

- Tempo de acesso constante
- Eficiencia de espaço
- Localidade de memória

##### Desvantagens
- Não ajusta o tamanho em execução
- Não permite compartilhamento de memória

<span style="color: orange">Deve ser estudado o melhor tipo de dado para implementar uma coisa. Existem muitas possibilidades, porém seu desempenho deve ser ótimo.</span>

### Variável

<span style="color: orange">Estrutura de dados criada para armazenar tipo de dados básicos</span>