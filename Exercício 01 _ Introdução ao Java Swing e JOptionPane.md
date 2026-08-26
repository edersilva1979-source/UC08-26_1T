# 💻 Exercício 01 | Introdução ao Java Swing

## 🎯 Objetivo do exercício

Neste exercício, nós vamos criar nosso primeiro projeto utilizando **Java Swing no NetBeans**.

O objetivo é praticarmos a criação de uma interface gráfica utilizando alguns dos componentes básicos do Swing e também aprendermos a exibir diferentes tipos de caixas de mensagens com a classe `JOptionPane`.

Ao final do exercício, nossa tela terá:

4 campos de texto

4 botões

4 tipos diferentes de mensagens

---

# 📁 1. Criando o projeto

Vamos iniciar nosso projeto completamente do zero.

No NetBeans:

1. Clique em `File`
2. Clique em `New Project`
3. Escolha:

```text
Java with Ant
Java Application
```

4. Clique em `Next`

No nome do projeto, digite:

```text
Exercicio01_JAVA
```

5. Escolha o local onde deseja salvar o projeto
6. Finalize a criação

---

# 🖥️ 2. Criando a tela

Agora vamos criar nossa primeira interface gráfica.

Dentro do projeto:

1. Clique com o botão direito sobre o pacote do projeto
2. Escolha `New`
3. Escolha `JFrame Form`

Vamos utilizar como nome da tela:

```text
FrmExercicio01
```

Clique em `Finish`.

O NetBeans abrirá o editor gráfico do Java Swing.

---

# 🏗️ 3. Montando a interface

Nossa tela deverá possuir quatro informações referentes ao aluno.

Vamos adicionar quatro `JLabel` com os seguintes textos:

```text
Nome
Endereço
Telefone
Turma
```

Ao lado de cada informação, vamos adicionar um componente `JTextField`.

A organização poderá ficar semelhante a esta:

```text
Nome:       [________________________]

Endereço:   [________________________]

Telefone:   [________________________]

Turma:      [________________________]
```

---

# 📝 4. Nomeando os JTextField

Vamos alterar a propriedade `Variable Name` de cada campo.

Utilize os seguintes nomes:

| Campo | Variable Name |
|---|---|
| Nome | txtNome |
| Endereço | txtEndereco |
| Telefone | txtTelefone |
| Turma | txtTurma |

Essa organização será muito importante quando começarmos a programar nossos componentes.

Por exemplo:

```java
txtNome
```

representará o campo onde digitaremos o nome do aluno.

---

# 🔘 5. Adicionando os botões

Agora vamos colocar quatro componentes `JButton` na parte inferior da tela.

Os botões deverão possuir os seguintes textos:

```text
MENSAGEM
AVISO
ERRO
QUESTÃO
```

Vamos utilizar os seguintes nomes para os componentes:

| Texto do botão | Variable Name |
|---|---|
| MENSAGEM | btnMensagem |
| AVISO | btnAviso |
| ERRO | btnErro |
| QUESTÃO | btnQuestao |

Nossa tela poderá ficar aproximadamente assim:

```text
Nome:       [________________________]

Endereço:   [________________________]

Telefone:   [________________________]

Turma:      [________________________]


[MENSAGEM]   [AVISO]   [ERRO]   [QUESTÃO]
```

---

# 💬 6. Programando o botão MENSAGEM

Vamos começar programando nosso primeiro botão.

Dê dois cliques sobre o botão:

```text
MENSAGEM
```

O NetBeans criará automaticamente o evento `ActionPerformed`.

Dentro desse evento, digite:

```java
JOptionPane.showMessageDialog(
        null,
        "Aluno Cadastrado"
);
```

Precisaremos importar a classe `JOptionPane`.

Na parte superior da classe, deverá existir:

```java
import javax.swing.JOptionPane;
```

Ao clicar no botão, deverá aparecer a mensagem:

```text
Aluno Cadastrado
```

---

# ⚠️ 7. Programando o botão AVISO

Agora dê dois cliques sobre o botão:

```text
AVISO
```

Dentro do evento do botão, coloque:

```java
JOptionPane.showMessageDialog(
        null,
        "Aluno com muitas Faltas",
        "Aviso",
        JOptionPane.WARNING_MESSAGE
);
```

Ao clicar no botão, deverá aparecer uma caixa de aviso com a mensagem:

```text
Aluno com muitas Faltas
```

Aqui estamos utilizando:

```java
JOptionPane.WARNING_MESSAGE
```

Essa opção informa ao Java que queremos apresentar uma mensagem de **aviso**.

---

# ❌ 8. Programando o botão ERRO

Agora vamos programar o botão:

```text
ERRO
```

Dê dois cliques sobre ele e utilize:

```java
JOptionPane.showMessageDialog(
        null,
        "Aluno reprovado por falta",
        "Erro",
        JOptionPane.ERROR_MESSAGE
);
```

Ao clicar nesse botão, deverá aparecer:

```text
Aluno reprovado por falta
```

Estamos utilizando:

```java
JOptionPane.ERROR_MESSAGE
```

Essa opção representa uma mensagem de erro.

---

# ❓ 9. Programando o botão QUESTÃO

Agora vamos utilizar um tipo diferente de `JOptionPane`.

Dê dois cliques sobre o botão:

```text
QUESTÃO
```

Digite:

```java
JOptionPane.showConfirmDialog(
        null,
        "Aluno pode ser Aprovado?"
);
```

Ao executar, o Java apresentará uma caixa de confirmação com a pergunta:

```text
Aluno pode ser Aprovado?
```

Ela apresentará opções para que o usuário possa responder.

---

# 🔎 10. Melhorando a caixa de confirmação

Podemos deixar nossa caixa de confirmação mais organizada.

Utilize:

```java
JOptionPane.showConfirmDialog(
        null,
        "Aluno pode ser Aprovado?",
        "Confirmação",
        JOptionPane.YES_NO_OPTION
);
```

Agora teremos as opções:

```text
Yes
No
```

O objetivo neste primeiro exercício é apenas visualizar e utilizar a caixa de confirmação.

Mais adiante nós aprenderemos como identificar qual opção foi escolhida pelo usuário.

---

# 🧠 11. O que estamos aprendendo

Neste exercício estamos trabalhando alguns conceitos importantes do desenvolvimento com Java Swing.

### JFrame

É a janela principal da nossa aplicação.

### JLabel

Utilizamos para apresentar informações na tela.

Exemplo:

```text
Nome:
Telefone:
```

### JTextField

Utilizamos para permitir que o usuário digite informações.

Exemplo:

```java
txtNome
txtTelefone
```

### JButton

Representa um botão que poderá executar alguma ação.

Exemplo:

```java
btnMensagem
btnAviso
```

### JOptionPane

Permite apresentar caixas de mensagens para o usuário.

---

# 📚 12. Tipos de JOptionPane utilizados

Neste exercício utilizaremos três situações diferentes.

### Mensagem comum

```java
JOptionPane.showMessageDialog(
        null,
        "Aluno Cadastrado"
);
```

### Aviso

```java
JOptionPane.showMessageDialog(
        null,
        "Aluno com muitas Faltas",
        "Aviso",
        JOptionPane.WARNING_MESSAGE
);
```

### Erro

```java
JOptionPane.showMessageDialog(
        null,
        "Aluno reprovado por falta",
        "Erro",
        JOptionPane.ERROR_MESSAGE
);
```

### Confirmação

```java
JOptionPane.showConfirmDialog(
        null,
        "Aluno pode ser Aprovado?",
        "Confirmação",
        JOptionPane.YES_NO_OPTION
);
```

---

# ✅ 13. Resultado esperado

Ao finalizar o exercício, nosso projeto deverá possuir:

✅ Projeto chamado `Exercicio01_JAVA`

✅ Uma tela criada com `JFrame Form`

✅ Quatro `JTextField`

✅ Campo Nome

✅ Campo Endereço

✅ Campo Telefone

✅ Campo Turma

✅ Quatro `JButton`

✅ Botão MENSAGEM

✅ Botão AVISO

✅ Botão ERRO

✅ Botão QUESTÃO

✅ Utilização de `JOptionPane.showMessageDialog`

✅ Utilização de `JOptionPane.showConfirmDialog`

---

# 🧪 14. Testando nossa aplicação

Execute o projeto e realize os seguintes testes.

### Teste 1

Preencha:

```text
Nome: João da Silva
Endereço: Rua das Flores
Telefone: 999999999
Turma: DS01
```

Clique em:

```text
MENSAGEM
```

Resultado esperado:

```text
Aluno Cadastrado
```

### Teste 2

Clique em:

```text
AVISO
```

Resultado esperado:

```text
Aluno com muitas Faltas
```

### Teste 3

Clique em:

```text
ERRO
```

Resultado esperado:

```text
Aluno reprovado por falta
```

### Teste 4

Clique em:

```text
QUESTÃO
```

Resultado esperado:

```text
Aluno pode ser Aprovado?
```

A caixa deverá permitir que o usuário escolha entre as opções apresentadas.

---

# 🚀 Desafio

Depois de concluir o exercício principal, tente melhorar visualmente sua tela.

Você poderá alterar:

1. Título da janela
2. Fonte dos componentes
3. Tamanho dos botões
4. Posicionamento dos componentes
5. Cor de fundo
6. Tamanho da janela

Também tente adicionar um título na parte superior:

```text
CADASTRO DE ALUNOS
```

O mais importante é que todos os quatro botões continuem funcionando corretamente.

---

# 🎓 Conclusão

Com este exercício nós começamos a trabalhar com eventos no Java Swing.

Até agora nossos componentes estavam apenas sendo exibidos na tela. A partir do momento em que programamos os botões, nossa interface começou a responder às ações do usuário.

Esse conceito será fundamental durante todo o desenvolvimento de aplicações Desktop em Java.

Nos próximos exercícios poderemos utilizar os valores digitados nos `JTextField`, realizar validações, limpar os campos e criar operações de cadastro mais completas.