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

<h4>Estrutura geral de uma classe</h4>

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
<h4>Explicação dos componentes</h4>

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

<h4>Passos para Executar uma Classe Java</h4>

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

<h4>Exemplos de execução</h4>

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

<h4>Argumentos de Linha de Comando</h4>

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
