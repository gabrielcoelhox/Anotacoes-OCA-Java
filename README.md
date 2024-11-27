# <p align="center"> <a id="id99"> 📝 Oracle Certified Associate Java 8 📝</p>
<p align="center"> 💻 Atualizado em 26 de Novembro de 2024 💻</p>
<p align="center">
  <a href="https://github.com/gabrielcoelhox/Anotacoes-OCA-Java/commits/main">
    <img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/gabrielcoelhox/Anotacoes-OCA-Java">
  </a>
</p>

Repositório destinado a anotações de estudo para a prova de certificação **[Java SE 8 Programmer I - 1Z0-808](https://education.oracle.com/java-se-8-programmer-i/pexam_1Z0-808)**.

## :pushpin: Sumário

1. [Introdução](#id1)

2. [Java Basics](#id2)
    - 2.1. Estrutura básica de uma classe Java;
    - 2.2. Executando uma classe Java;
    - 2.3. Importando pacotes Java e usando `import`;
    - 2.4. Diferença entre variáveis locais, de instância e estáticas.
3. [Tipos de Dados e Operadores](#id3)
    - 3.1. Declarar e inicializar variáveis;
    - 3.2. Trabalhando com tipos primitivos;
    - 3.3. Conversão e casting entre tipos;
    - 3.4. Operadores (aritméticos, de comparação, lógicos, ternário).
4. [Controle de Fluxo](#id4)
    - 4.1. Estruturas de decisão: `if-else`, `switch`;
    - 4.2. Laços de repetição: `for`, `while`, `do-while`;
    - 4.3. Manipulação de `break` e `continue`.
5. [Classes, Métodos e Encapsulamento](#id5)
    - 5.1. Criar e usar métodos;
    - 5.2. Overloading e sobrecarga de métodos;
    - 5.3. Entendendo e implementando construtores;
    - 5.4. Aplicando encapsulamento.
6. [Programação Orientada a Objetos (POO)](#id6)
    - 6.1. Trabalhando com herança e polimorfismo;
    - 6.2. Definir e usar classes abstratas e interfaces;
    - 6.3. Entendendo o uso de `this` e `super`;
    - 6.4. Sobrescrever métodos `(@Override)`.
7. [Coleções e Arrays](#id7)
    - 7.1. Manipulando arrays unidimensionais e multidimensionais;
    - 7.2. Utilizar as classes do pacote `java.util`, como `ArrayList`.
8. [Exceções](#id8)
    - 8.1. Diferença entre Checked e Unchecked exceptions;
    - 8.2. Usando `try-catch` e `finally`.
9.  [Trabalhando com Strings](#id9)
    - 9.1. Manipulando `String` e `StringBuilder`;
    - 9.2. Métodos comuns (substring, length, indexOf, etc.).


## <a id="id1">:page_facing_up: 1. Introdução </a>
[INÍCIO](#id99)

A certificação Oracle Certified Associate (OCA) Java SE 8 Programmer é uma qualificação básica para programadores Java e reconhece o domínio dos fundamentos da linguagem Java e conceitos de programação orientada a objetos. Ela é ideal para quem quer consolidar sua base na linguagem e abrir portas no mercado de trabalho.

## <a id="id2"> 2. Java Basics</a>
[INÍCIO](#id99)

A estrutura básica de uma classe Java é o ponto de partida para criar programas em Java. Todas as aplicações Java são construídas usando classes, que contêm campos (variáveis) e métodos (funções). Entender essa estrutura é essencial para qualquer desenvolvedor.

<details>
<summary><h3><b>2.1 Estrutura básica de uma classe Java</b></h3></summary>

<h4>🔹Estrutura geral de uma classe</h4>

``` java
// Pacote (opcional)
package com.example;

// Importações (opcional)
import java.util.Scanner;

// Declaração da Classe
public class MinhaClasse {

    // Campos ou Atributos (variáveis de instância ou estáticas)
    private String nome;
    private static int contador;

    // Construtor
    public MinhaClasse(String nome) {
        this.nome = nome;
    }

    // Métodos (comportamentos)
    public void imprimirNome() {
        System.out.println("Nome: " + nome);
    }

    public static void mostrarContador() {
        System.out.println("Contador: " + contador);
    }

    // Método principal (ponto de entrada do programa)
    public static void main(String[] args) {
        MinhaClasse obj = new MinhaClasse("Java");
        obj.imprimirNome();
        contador++;
        mostrarContador();
    }
}
```
<h4>🔹Explicação dos componentes</h4>

1.  Pacotes (`package`)
    - Define o namespace da classe.
    - Ajuda a organizar o código, principalmente em projetos grandes.
    - Exemplo: `package com.example;`.

2.  Importações (`import`)
    - Permitem o uso de classes externas no código.
    - Exemplo: `import java.util.Scanner;`.

3.  Declaração da classe
    - Definida com a palavra-chave `class`.
    - O modificador `public` significa que a classe é acessível por outros pacotes.
    - O nome da classe deve corresponder ao nome do arquivo (sensível a maiúsculas/minúsculas).

4.  Campos/Atributos
    - São variáveis que representam o estado da classe ou de seus objetos.
    - Podem ser:
        - __De instância:__ Associados a objetos individuais (`private String nome;`).
        - __Estáticos:__ Associados à classe e compartilhados por todos os objetos (`static int contador;`).

5. Construtor
    - Um método especial chamado quando o objeto é criado.
    - Não tem tipo de retorno e seu nome __deve__ ser igual ao da classe.
    - Exemplo: `public MinhaClasse(String nome) { this.nome = nome; }`.

6. Métodos
    - Definem comportamentos ou ações.
    - Podem ser:
        - __De instância:__ Operam em atributos do objeto (`public void imprimirNome()`).
        - __Estáticos:__ Operam na classe e não dependem de instância (`public static void mostrarContador()`).

7. Método main
    - Ponto de entrada do programa.
    - Deve ser declarado como:
    ``` java public static void main(String[] args) ```
    - Aqui começa a execução do programa.
</details>
<details>
<summary><h3><b>2.2 Executar uma classe Java</b></h3></summary>

<h4>🔹Passos para Executar uma Classe Java</h4>

1. <b>Método `main`</b>
- O método `main` é o ponto de entrada de um programa Java.
- Deve ter a assinatura exata:
``` java
public static void main(String[] args)
```

- Significado:
    - `public`: Acessível pela JVM.
    - `static`: Pode ser chamado sem criar uma instância da clsse.
    - `void`: Não retorna nenhum valor.
    - `String[] args`: Aceita argumentos de linha de comando.

<h4>🔹Exemplos de execução</h4>

Arquivo: `com/exemplo/ExemploComPacote.java`

```java
package com.exemplo;

public class ExemploComPacote {
    public static void main(String[] args) {
        System.out.println("Executando com pacotes!");
    }
}
```

Comandos:
```bash
javac com/exemplo/ExemploComPacote.java
java com.exemplo.ExemploComPacote
```

<h4>🔹Argumentos de Linha de Comando</h4>

É possível passar argumentos para o programa no momento da execução. Por exemplo: Arquivo: `Argumentos.java`

```java
public class Argumentos {
    public static void main(String[] args) {
        for (String arg : args) {
            System.out.println("Argumento: " + arg);
        }
    }
}
```

Comandos:
```bash
javac Argumentos.java
java Argumentos Java é incrível
```

Saída:
```makefile
Argumento: Java
Argumento: é
Argumento: incrível
```
</details>
<details>
<summary><h3><b>2.3 Importar pacotes Java e usar import</b></h3></summary>

O uso de pacotes e importações em Java permite organizar e reutilizar código. Os pacotes agrupam classes relacionadas, e a palavra-chave `import` facilita o acesso a essas classes em diferentes partes de um programa.

<h4>🔹<b>O que é um pacote?</b></h4>

Um pacote em Java é como uma "pasta" que organiza classes e interfaces. Ele ajuda a evitar conflitos de nomes e facilita a manutenção do código.

Por exemplo:
- O pacote `java.util` contém classes úteis, como `ArrayList` e `HashMap`.
- O pacote `java.io` contém classes para operações de entrada e saída.

Exemplo:
```java
package com.exemplo;
```

<h4>🔹<b>O que é import?</b></h4>

A palavra-chave `import` é usada para acessar classes ou interfaces de outros pacotes sem precisar usar o nome completo do pacote toda vez.

<h4>🔹<b>Importação Explícita</b></h4>
Especifica uma única classe para importação:

```java
import java.util.ArrayList;
```

<h4>🔹<b>Importação com *</b></h4>
Importa todas as classes

```java
import java.util.*;
```

<h4>🔹<b>Importação Implícita</b></h4>
Alguns pacotes são automaticamente acessíveis, sem necessidade de `import`:

1. `java.lang`
Contém classes fundamentais como `String`, `Math`, `Object`, etc.

```java
public class Exemplo {
    public static void main(String[] args) {
        System.out.println(Math.sqrt(16)); // Sem import
    }
}
```

2. Classes no mesmo pacote
Classes definidas no mesmo pacote não requerem `import`.

<h4>🔹<b>Usando o Nome Completo da Classe (FQN)</b></h4>

Se você não quiser usar `import`, pode referenciar uma classe pelo seu nome completo (Fully Qualified Name - FQN):

```java
public class Exemplo {
    public static void main(String[] args) {
        java.util.ArrayList<String> lista = new java.util.ArrayList<>();
    }
}
```

<h4>🔹<b>Quando e Por Que Usar import?</b></h4>

- Facilita a leitura do código ao evitar FQNs repetitivos.
- Ajuda a identificar quais bibliotecas externas estão sendo usadas.
- Evita conflitos de nomes (duas classes com o mesmo nome em pacotes diferentes).

Exemplo de conflito:
```java
import java.util.Date;
import java.sql.Date;

public class Conflito {
    public static void main(String[] args) {
        Date data1 = new Date(); // java.util.Date
        java.sql.Date data2 = new java.sql.Date(System.currentTimeMillis());
    }
}
```
</details>
<details>
<summary><h3><b>2.4 Diferença entre variáveis locais, de instância e estáticas</b></h3></summary>

As variáveis em Java podem ser classificadas com base no seu escopo e propósito: locais, de instância e estáticas. Cada tipo de variável tem características e usos específicos.

<h4>🔹<b>Variáveis Locais</b></h4>

- Definição: Declaradas dentro de um método, construtor ou bloco de código. Só existem durante a execução do método/bloco onde foram definidas.
- Escopo: Restrito ao método, construtor ou bloco onde foram declaradas.
- Inicialização: Devem ser inicializadas explicitamente antes de serem usadas.
- Acesso: Não podem ter modificadores de acesso (como `public` ou `private`).

Exemplo:
```java
public class Exemplo {
    public void metodo() {
        int local = 10; // Variável local
        System.out.println("Valor da variável local: " + local);
    }
}
```
Características:
- Criadas na pilha de execução.
- Não têm valores padrão.
- Não podem ser usadas fora do método/bloco onde foram declaradas.

<h4>🔹<b>Variáveis de Instância</b></h4>

- Definição: Declaradas dentro de uma classe, mas fora de métodos, construtores ou blocos. Estão associadas a instâncias (objetos) da classe.
- Escopo: Acessíveis por toda a classe. Cada objeto da classe tem sua própria cópia da variável.
- Inicialização: Podem ser inicializadas diretamente ou no construtor. Se não forem, recebem valores padrão:
    - `0` para tipos numéricos.
    - `false` para `boolean`.
    - `null` para objetos.

Exemplo:
```java
public class Pessoa {
    private String nome; // Variável de instância

    public Pessoa(String nome) {
        this.nome = nome; // Inicializando a variável de instância
    }

    public void mostrarNome() {
        System.out.println("Nome: " + nome);
    }
}
```

Características:
- Criadas na memória heap.
- São únicas para cada objeto.
- Podem ter modificadores de acesso (`private`, `public`, etc.).

<h4>🔹<b>Variáveis Estáticas(ou de Classe)</b></h4>

- Definição: Declaradas dentro de uma classe com a palavra-chave static. Associadas à classe e não a objetos individuais.
- Escopo: Acessíveis por toda a classe e compartilhadas entre todas as instâncias.
- Inicialização: Inicializadas na primeira vez que a classe é carregada na memória.
- Acesso: Podem ser acessadas diretamente pelo nome da classe, sem a necessidade de criar um objeto.

Exemplo:
```java
public class Contador {
    public static int contador = 0; // Variável estática

    public Contador() {
        contador++; // Incrementa o valor estático
    }

    public static void mostrarContador() {
        System.out.println("Contador: " + contador);
    }
}
```

Características:
- Criadas na área de memória estática.
- Compartilhadas por todas as instâncias da classe.
- Podem ser usadas para criar constantes (`static final`).

<h4>🔹<b>Resumo</b></h4>

| Característica      | Variáveis Locais            | Variáveis de Instância      | Variáveis Estáticas         |
|---------------------|-----------------------------|-----------------------------|-----------------------------|
| **Definição**       | Dentro de métodos ou blocos.| Dentro da classe.           | Dentro da classe com `static`. |
| **Escopo**          | Restrito ao método/bloco.   | Pertence a cada objeto.     | Compartilhada por todos os objetos. |
| **Memória**         | Pilha de execução.          | Memória heap.               | Área de memória estática.   |
| **Inicialização**   | Deve ser explícita.         | Valores padrão (ou explícita). | Inicializada na carga da classe. |
| **Acesso**          | Não pode ter modificadores. | Pode ter modificadores.     | Pode ser acessada pela classe diretamente. |
| **Uso**             | Para cálculos temporários.  | Para atributos de objetos.  | Para atributos compartilhados ou constantes. |
</details>

## <a id="id3"> 3. Tipos de Dados e Operadores</a>

<h4>🔹<b>Tipos de Dados</b></h4>

1. Primitivos:
    - Numéricos inteiros: `byte`, `short`, `int`, `long`.
    - Numéricos decimais: `float`, `double`.
    - Caractere: `char`.
    - Lógico: `boolean` (true/false).

2. Referência: Para objetos, arrays e o valor `null`.

<h4>🔹<b>Operadores</b></h4>

1. Aritméticos: Realizam cálculos matemáticos (`+`, `-`, `*`, `/`, `%`).
2. Relacionais: Comparam valores (`==`, `!=`, `>`, `<`, `>=`, `<=`).
3. Lógicos: Avaliam condições (`&&`, `||`, `!`).
4. Atribuição: Usados para atribuir valores (`=v`, `+=`, `-=`, etc.).
5. Incremento/Decremento: Alteram valores em 1 (`++`, `--`).

<details>
<summary><h3><b>3.1 Declarar e inicializar variáveis;</b></h3></summary>

Variáveis são usadas para armazenar dados em memória. Em Java, declarar e inicializar variáveis segue regras específicas.

<h4>🔹<b>Declaração de Variáveis</b></h4>
Declarar uma variável significa reservar espaço na memória e especificar seu tipo. A sintaxe básica é:

```java
tipo nomeDaVariavel;
```

Exemplo:
```java
int idade;  // Declara uma variável chamada "idade" do tipo inteiro.
```

<h4>🔹<b>Inicialização de Variáveis</b></h4>
Inicializar uma variável significa atribuir um valor a ela. Isso pode ser feito na declaração ou posteriormente.

Exemplos:
```
java
int idade = 25;  // Declara e inicializa.
int ano;         // Declara.
ano = 2024;      // Inicializa depois.
```

- Variáveis locais (dentro de métodos) precisam ser inicializadas antes do uso.
- Variáveis de instância e estáticas recebem valores padrão:
  - `0` para tipos numéricos.
  - `false` para `boolean`.
  - `null` para referências.

<h4>🔹<b>Declaração e Inicialização Múltipla</b></h4>
Várias variáveis do mesmo tipo podem ser declaradas ou inicializadas na mesma linha:

```
java
int a, b, c;           // Declaração.
int x = 1, y = 2, z = 3; // Declaração e inicialização.
```

<h4>🔹<b>Regras para Nomes de Variáveis</b></h4>

1. Devem começar com uma letra, `_`, ou `$`.
2. Não podem usar palavras reservadas (`int`, `class`, etc.).
3. Sensíveis a maiúsculas e minúsculas (`idade` ≠ `Idade`).


<h4>🔹<b>Exemplo Completo</b></h4>

```
java
public class Exemplo {
    public static void main(String[] args) {
        int idade = 30;               // Declara e inicializa.
        double salario;               // Declara.
        salario = 4500.75;            // Inicializa depois.

        System.out.println("Idade: " + idade);
        System.out.println("Salário: " + salario);
    }
}
```

Saída:

```
makefile
Idade: 30
Salário: 4500.75
```

Declarar e inicializar variáveis corretamente é fundamental para evitar erros e gerenciar dados no programa.
</details>