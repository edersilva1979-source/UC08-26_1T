# UC08-26_1T

# ☕ Curso de Java com Swing

## Desenvolvimento de Aplicações Desktop com Java

Bem vindos ao nosso curso de **Java com Swing**.

Neste curso nós vamos aprender a desenvolver aplicações desktop
utilizando Java e os principais componentes da biblioteca Swing. Nosso
objetivo é construir interfaces gráficas funcionais e organizadas,
aplicando na prática os conceitos fundamentais da linguagem Java e da
Programação Orientada a Objetos.

O curso foi organizado de forma progressiva. Nós começamos pelos
fundamentos e avançamos para formulários, menus, tabelas, múltiplas
janelas, eventos, validações e pequenos sistemas desktop completos.

> **Importante:** este módulo trabalha com Java Swing **sem banco de
> dados**. Os dados das atividades serão mantidos temporariamente em
> memória utilizando objetos, coleções e `ArrayList`.

------------------------------------------------------------------------

## 🎯 Objetivos do curso

Ao longo das aulas nós vamos aprender a:

-   compreender o funcionamento de uma aplicação desktop
-   criar projetos Java no Apache NetBeans
-   aplicar Programação Orientada a Objetos
-   criar classes, objetos, atributos e métodos
-   utilizar encapsulamento, construtores, getters e setters
-   criar interfaces gráficas com Swing
-   trabalhar com `JFrame` e `JInternalFrame`
-   organizar múltiplas janelas com `JDesktopPane`
-   criar menus utilizando `JMenuBar`
-   utilizar campos, botões e eventos
-   exibir mensagens com `JOptionPane`
-   utilizar `JComboBox`
-   criar e manipular `JTable`
-   utilizar `DefaultTableModel`
-   armazenar objetos temporariamente com `ArrayList`
-   cadastrar, consultar, alterar e excluir dados em memória
-   validar informações digitadas pelo usuário
-   organizar aplicações Java em classes e pacotes
-   desenvolver aplicações desktop completas

------------------------------------------------------------------------

## 🧰 Tecnologias utilizadas

  Tecnologia        Utilização
  ----------------- -----------------------------------------
  Java              Linguagem de programação
  Java Swing        Desenvolvimento das interfaces gráficas
  Apache NetBeans   Ambiente de desenvolvimento
  JDK               Kit de desenvolvimento Java
  Git               Versionamento dos projetos
  GitHub            Armazenamento e documentação

------------------------------------------------------------------------

## 🖥️ O que é Java Swing?

Swing é uma biblioteca do Java utilizada para desenvolver interfaces
gráficas para aplicações desktop.

Em vez de trabalharmos somente pelo terminal, podemos criar janelas com
campos, botões, menus, tabelas e mensagens.

Exemplo:

``` text
┌─────────────────────────────────────┐
│ Cadastro de Aluno                   │
├─────────────────────────────────────┤
│ ID:      [________]                 │
│ Nome:    [______________________]   │
│ Turma:   [______________________]   │
│ E-mail:  [______________________]   │
│                                     │
│ [ Adicionar ] [ Alterar ]           │
│ [ Excluir   ] [ Limpar  ]           │
└─────────────────────────────────────┘
```

Com isso, nós conseguimos construir aplicações semelhantes aos sistemas
desktop utilizados em empresas, escolas, lojas e escritórios.

------------------------------------------------------------------------

## 📚 Conteúdos trabalhados

### 1. Fundamentos de Java

Nós revisamos conceitos importantes da linguagem Java:

``` java
int idade = 20;
String nome = "Maria";
double media = 8.5;
boolean aprovado = true;
```

Também trabalhamos com:

-   variáveis
-   operadores
-   estruturas condicionais
-   estruturas de repetição
-   métodos
-   organização do código

### 2. Programação Orientada a Objetos

Nós utilizamos classes para representar elementos do sistema.

``` java
public class Aluno {

    private int id;
    private String nome;
    private String turma;
    private String email;

}
```

A partir da classe podemos criar objetos:

``` java
Aluno aluno = new Aluno();
```

Durante o curso trabalhamos:

-   classes
-   objetos
-   atributos
-   métodos
-   construtores
-   encapsulamento
-   getters
-   setters

------------------------------------------------------------------------

## 🪟 Principais componentes Swing

### JFrame

Representa uma janela principal da aplicação.

### JLabel

Utilizamos para apresentar textos e identificações dos campos.

### JTextField

Utilizamos para entrada de informações.

``` text
Nome: [________________________]
```

### JButton

Representa um botão da aplicação.

``` text
[ Adicionar ] [ Alterar ] [ Excluir ] [ Limpar ]
```

### JComboBox

Permite selecionar uma opção entre vários valores.

``` text
Turma: [ Turma A ▼ ]
```

### JTable

Utilizamos para apresentar informações em formato de tabela.

``` text
┌────┬───────────────┬──────────┬────────────────────┐
│ ID │ Nome          │ Turma    │ E-mail             │
├────┼───────────────┼──────────┼────────────────────┤
│ 1  │ Ana Silva     │ Turma A  │ ana@email.com      │
│ 2  │ Carlos Souza  │ Turma B  │ carlos@email.com   │
└────┴───────────────┴──────────┴────────────────────┘
```

### JOptionPane

Utilizamos para apresentar mensagens ao usuário.

``` java
JOptionPane.showMessageDialog(
    null,
    "Cadastro realizado com sucesso!"
);
```

Também podemos solicitar uma confirmação:

``` java
int resposta = JOptionPane.showConfirmDialog(
    null,
    "Deseja realmente excluir?"
);
```

------------------------------------------------------------------------

## 📂 JMenuBar

Nós também aprendemos a construir menus para organizar as
funcionalidades da aplicação.

``` text
Arquivo     Editar     Exibir     Ajuda
```

Exemplo:

``` text
Arquivo
    Novo
    Editar
    Sair

Editar
    Desfazer
    Refazer

Exibir
    Zoom
    Régua

Ajuda
    Sobre o Sistema
```

------------------------------------------------------------------------

## 🖥️ JDesktopPane e JInternalFrame

Para sistemas com várias telas podemos trabalhar com a seguinte
organização:

``` text
JFrame
    │
    └── JDesktopPane
            │
            ├── JInternalFrame Aluno
            ├── JInternalFrame Cliente
            └── JInternalFrame Produto
```

O `JDesktopPane` funciona como uma área de trabalho para nossas janelas
internas.

------------------------------------------------------------------------

## 📦 Trabalhando com ArrayList

Como este módulo não utiliza banco de dados, nós podemos guardar
temporariamente os objetos utilizando `ArrayList`.

``` java
ArrayList<Aluno> alunos = new ArrayList<>();
```

Para adicionar um objeto:

``` java
Aluno aluno = new Aluno();

aluno.setNome("Maria");
aluno.setTurma("Turma A");
aluno.setEmail("maria@email.com");

alunos.add(aluno);
```

Podemos visualizar o processo:

``` text
Formulário
    │
    ▼
Objeto Aluno
    │
    ▼
ArrayList
    │
    ▼
JTable
```

Os dados permanecem disponíveis enquanto o programa estiver em execução.
Ao encerrar a aplicação, os dados mantidos somente em memória serão
perdidos.

------------------------------------------------------------------------

## 📊 Trabalhando com JTable

Nós utilizamos `DefaultTableModel` para manipular os registros
apresentados na tabela.

``` java
DefaultTableModel modelo =
    (DefaultTableModel) tabelaAluno.getModel();

modelo.addRow(new Object[]{
    aluno.getId(),
    aluno.getNome(),
    aluno.getTurma(),
    aluno.getEmail()
});
```

Assim conseguimos atualizar a tabela dinamicamente.

------------------------------------------------------------------------

## 🔘 Eventos

Uma aplicação gráfica precisa responder às ações realizadas pelo
usuário.

``` text
Usuário
   │
   ▼
Clica no botão
   │
   ▼
Evento
   │
   ▼
Código Java
   │
   ▼
Resultado
```

Durante o curso, nossos botões poderão:

-   adicionar registros
-   alterar informações
-   excluir registros
-   limpar campos
-   pesquisar informações
-   abrir telas
-   fechar janelas
-   apresentar mensagens

------------------------------------------------------------------------

## 📝 CRUD em memória

Nós vamos trabalhar com as quatro operações fundamentais de um cadastro:

  Operação   Significado
  ---------- -------------
  Create     Cadastrar
  Read       Consultar
  Update     Alterar
  Delete     Excluir

Neste módulo, essas operações serão realizadas utilizando objetos e
coleções em memória.

------------------------------------------------------------------------

## 🧪 Exemplo de projeto

Um dos projetos utilizados durante as aulas é um sistema de cadastro de
alunos.

### Classe Aluno

Atributos:

``` text
ID
Nome
Turma
E-mail
```

### Interface

``` text
┌───────────────────────────────────────────┐
│ Cadastro de Alunos                        │
├───────────────────────────────────────────┤
│ ID:      [________]                       │
│ Nome:    [________________________]       │
│ Turma:   [________________________]       │
│ E-mail:  [________________________]       │
│                                           │
│ [Adicionar] [Alterar] [Excluir] [Limpar]  │
│                                           │
│ ┌─────────────────────────────────────┐   │
│ │ ID │ Nome │ Turma │ E-mail         │   │
│ └─────────────────────────────────────┘   │
└───────────────────────────────────────────┘
```

------------------------------------------------------------------------

## 📁 Organização do projeto

Uma estrutura simples pode ser:

``` text
src
│
├── model
│   └── Aluno.java
│
├── view
│   ├── FrmPrincipal.java
│   └── FrmAluno.java
│
└── main
    └── Principal.java
```

Essa organização facilita a manutenção e a compreensão do projeto.

------------------------------------------------------------------------

## 🧭 Evolução durante o curso

``` text
Java
  │
  ▼
Programação Orientada a Objetos
  │
  ▼
Classes e Objetos
  │
  ▼
Java Swing
  │
  ▼
JFrame
  │
  ▼
Componentes
  │
  ▼
Eventos
  │
  ▼
JTable
  │
  ▼
ArrayList
  │
  ▼
CRUD em Memória
  │
  ▼
Aplicação Desktop
```

------------------------------------------------------------------------

## 🏆 Competências desenvolvidas

Ao concluir este curso, nós teremos conhecimentos para:

-   criar aplicações desktop em Java
-   desenvolver interfaces utilizando Swing
-   organizar formulários
-   trabalhar com eventos
-   utilizar componentes gráficos
-   manipular tabelas
-   trabalhar com objetos e coleções
-   implementar cadastros
-   implementar consultas
-   alterar e excluir registros
-   criar menus
-   trabalhar com múltiplas janelas
-   validar informações
-   organizar projetos Java

------------------------------------------------------------------------

## 🚫 Por que ainda não utilizamos banco de dados?

Este curso representa nosso módulo de **Java Swing sem banco de dados**.

Por isso, não utilizaremos neste momento:

``` text
PostgreSQL
MySQL
JDBC
Connection
PreparedStatement
ResultSet
```

Primeiro nós vamos compreender como construir a aplicação, manipular
objetos, criar as interfaces e implementar as operações do sistema.

Depois poderemos evoluir para persistência de dados:

``` text
Java Swing
     │
     ▼
Classes e Objetos
     │
     ▼
CRUD em Memória
     │
     ▼
JDBC
     │
     ▼
PostgreSQL
     │
     ▼
CRUD com Banco de Dados
```

------------------------------------------------------------------------

## 🎯 Projeto final

Ao final do módulo, nosso objetivo é desenvolver uma aplicação Java
Swing reunindo os principais conhecimentos estudados.

O projeto deverá utilizar:

-   classes e objetos
-   encapsulamento
-   `JFrame`
-   `JInternalFrame`
-   `JMenuBar`
-   `JDesktopPane`
-   `JTextField`
-   `JButton`
-   `JComboBox`
-   `JTable`
-   `JOptionPane`
-   eventos
-   `ArrayList`
-   validações
-   cadastro
-   consulta
-   alteração
-   exclusão

Tudo isso sem utilizar banco de dados.

------------------------------------------------------------------------

## 📌 Requisitos

Para acompanhar as aulas recomendamos:

``` text
JDK
Apache NetBeans
Git
Conta no GitHub
```

------------------------------------------------------------------------

## 💻 Executando o projeto no NetBeans

Depois de abrir o projeto:

1.  Localize o projeto no painel `Projects`.
2.  Clique com o botão direito sobre o projeto.
3.  Selecione `Run`.
4.  Também podemos utilizar o botão de execução do NetBeans.
5.  Verifique se a classe principal está configurada corretamente.

Atalho:

``` text
F6
```

------------------------------------------------------------------------

## 📖 Como utilizar este repositório

Este repositório foi organizado para acompanhar nossas aulas de Java
Swing.

A recomendação é estudar cada conteúdo na sequência apresentada,
executar os exemplos e depois realizar os exercícios e desafios
propostos.

Nosso objetivo não é apenas copiar códigos.

Nós precisamos compreender o que cada classe, método, componente e
evento está fazendo. Quando entendemos o processo, conseguimos aplicar o
mesmo conhecimento na criação de outros sistemas.

------------------------------------------------------------------------

## 🚀 Próximos passos

Depois de dominarmos Java Swing sem banco de dados, estaremos preparados
para estudar:

-   SQL
-   PostgreSQL
-   JDBC
-   `Connection`
-   `PreparedStatement`
-   `ResultSet`
-   CRUD com banco de dados
-   relacionamentos entre tabelas
-   DAO
-   MVC

A interface gráfica aprendida neste curso continuará sendo utilizada. A
diferença é que os dados deixarão de existir somente na memória e
passarão a ser armazenados permanentemente.

------------------------------------------------------------------------

## ☕ Bons estudos e bom desenvolvimento!

> Programar não é apenas escrever código. Nós precisamos entender o
> problema, organizar uma solução, testar o resultado e aprender com
> cada etapa do desenvolvimento.
