# ☕ Exercício Básico em Java com Scanner

## 🎯 Objetivo da atividade

Nesta atividade, nós vamos criar um programa simples em Java utilizando o `Scanner` para capturar informações digitadas pelo usuário.

O programa deverá solicitar:

1. 👤 Nome
2. 👤 Sobrenome
3. 🎂 Idade
4. 🏙️ Cidade

Depois de receber essas informações, o programa deverá apresentar os dados de forma organizada utilizando `System.out.println()`.

## 📚 Conteúdos praticados

Com este exercício, nós vamos praticar:

1. Criação de um projeto Java no NetBeans
2. Criação da classe principal
3. Importação da classe `Scanner`
4. Criação de variáveis
5. Entrada de dados pelo teclado
6. Utilização do método `nextLine()`
7. Utilização do método `nextInt()`
8. Saída de dados com `System.out.println()`
9. Concatenação de textos e variáveis
10. Organização visual da saída do programa

## 🖥️ Parte 1. Criando o projeto no NetBeans

Abra o NetBeans e crie um novo projeto Java.

Sugestão de nome para o projeto:

```text
ExercicioApresentacao
```

Crie uma classe chamada:

```text
Apresentacao
```

## 📦 Parte 2. Importando o Scanner

Para utilizar o teclado como entrada de dados, nós precisamos importar a classe `Scanner`.

Digite no início do programa:

```java
import java.util.Scanner;
```

## ⌨️ Parte 3. Criando o Scanner

Dentro do método `main`, nós vamos criar um objeto chamado `entrada`.

```java
Scanner entrada = new Scanner(System.in);
```

Esse objeto será utilizado para capturar tudo o que o usuário digitar.

## 👤 Parte 4. Capturando o nome

Primeiro, vamos solicitar o nome.

```java
System.out.print("Digite seu nome: ");
String nome = entrada.nextLine();
```

## 👤 Parte 5. Capturando o sobrenome

Agora vamos solicitar o sobrenome.

```java
System.out.print("Digite seu sobrenome: ");
String sobrenome = entrada.nextLine();
```

## 🎂 Parte 6. Capturando a idade

Para a idade, vamos utilizar uma variável do tipo `int`.

```java
System.out.print("Digite sua idade: ");
int idade = entrada.nextInt();
```

Depois da leitura da idade, utilizaremos:

```java
entrada.nextLine();
```

Isso ajuda a limpar a quebra de linha que ficou armazenada após o `nextInt()`.

## 🏙️ Parte 7. Capturando a cidade

Agora vamos solicitar a cidade.

```java
System.out.print("Digite sua cidade: ");
String cidade = entrada.nextLine();
```

## 🧾 Parte 8. Apresentando os resultados

Depois de receber todas as informações, nós vamos montar uma apresentação organizada.

Exemplo:

```java
System.out.println();
System.out.println("======================================");
System.out.println("        👤 APRESENTAÇÃO PESSOAL");
System.out.println("======================================");
System.out.println("👤 Nome completo: " + nome + " " + sobrenome);
System.out.println("🎂 Idade: " + idade + " anos");
System.out.println("🏙️ Cidade: " + cidade);
System.out.println("======================================");
System.out.println("😊 Seja bem vindo ao nosso programa!");
System.out.println("======================================");
```

## 💻 Código completo

```java
import java.util.Scanner;

public class Apresentacao {

    public static void main(String[] args) {

        Scanner entrada = new Scanner(System.in);

        System.out.println("======================================");
        System.out.println("     ☕ CADASTRO DE APRESENTAÇÃO");
        System.out.println("======================================");

        System.out.print("👤 Digite seu nome: ");
        String nome = entrada.nextLine();

        System.out.print("👤 Digite seu sobrenome: ");
        String sobrenome = entrada.nextLine();

        System.out.print("🎂 Digite sua idade: ");
        int idade = entrada.nextInt();

        entrada.nextLine();

        System.out.print("🏙️ Digite sua cidade: ");
        String cidade = entrada.nextLine();

        System.out.println();
        System.out.println("======================================");
        System.out.println("        👤 APRESENTAÇÃO PESSOAL");
        System.out.println("======================================");
        System.out.println("👤 Nome completo: " + nome + " " + sobrenome);
        System.out.println("🎂 Idade: " + idade + " anos");
        System.out.println("🏙️ Cidade: " + cidade);
        System.out.println("======================================");
        System.out.println("😊 Seja bem vindo ao nosso programa!");
        System.out.println("======================================");

        entrada.close();
    }
}
```

## 🧪 Exemplo de execução

O usuário poderá digitar:

```text
👤 Digite seu nome: Carlos
👤 Digite seu sobrenome: Silva
🎂 Digite sua idade: 25
🏙️ Digite sua cidade: Porto Alegre
```

O programa deverá apresentar:

```text
======================================
        👤 APRESENTAÇÃO PESSOAL
======================================
👤 Nome completo: Carlos Silva
🎂 Idade: 25 anos
🏙️ Cidade: Porto Alegre
======================================
😊 Seja bem vindo ao nosso programa!
======================================
```

## ✅ Requisitos do exercício

O programa deverá obrigatoriamente:

1. Utilizar a classe `Scanner`
2. Solicitar nome
3. Solicitar sobrenome
4. Solicitar idade
5. Solicitar cidade
6. Armazenar cada informação em uma variável
7. Apresentar os dados utilizando `System.out.println()`
8. Exibir o nome e o sobrenome juntos
9. Mostrar a idade acompanhada da palavra `anos`
10. Organizar a apresentação final de forma visualmente agradável

## 🚀 Desafio adicional

Depois de concluir o exercício principal, acrescente mais três informações:

1. 💼 Profissão
2. 🎨 Hobby
3. 💻 Linguagem de programação favorita

Exemplo de apresentação:

```text
======================================
        👤 APRESENTAÇÃO PESSOAL
======================================
👤 Nome completo: Carlos Silva
🎂 Idade: 25 anos
🏙️ Cidade: Porto Alegre
💼 Profissão: Desenvolvedor
🎨 Hobby: Fotografia
💻 Linguagem favorita: Java
======================================
🚀 Cadastro concluído com sucesso!
======================================
```

## 🧠 Questões para reflexão

Depois de concluir o programa, responda:

1. Para que serve a classe `Scanner`?
2. Qual a diferença entre `nextLine()` e `nextInt()`?
3. Por que utilizamos variáveis para armazenar os dados?
4. Para que serve o `System.out.println()`?
5. Qual a diferença entre `System.out.print()` e `System.out.println()`?
6. Por que utilizamos `entrada.nextLine()` depois do `nextInt()`?
7. Para que serve o comando `entrada.close()`?

## 🏁 Conclusão

Com esta atividade, nós criamos um dos nossos primeiros programas interativos em Java.

Nós utilizamos entrada de dados pelo teclado, variáveis, tipos de dados, concatenação e saída formatada.

Esses conceitos serão utilizados diversas vezes durante nossos próximos projetos em Java. ☕🚀
