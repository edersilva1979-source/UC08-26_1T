# Aula Java Swing com Componentes de Entrada e Seleção

## JCheckBox, JRadioButton, ButtonGroup, JPasswordField, JFormattedTextField e JSpinner

Nesta aula nós vamos ampliar nossos conhecimentos em Java Swing utilizando componentes muito comuns em sistemas Desktop.

Até aqui nós já trabalhamos com formulários, campos de texto, botões e mensagens. Agora vamos aprender a criar telas mais completas, permitindo que o usuário marque opções, escolha alternativas, informe senhas, digite dados com formato definido e selecione valores numéricos.

Nosso objetivo será compreender cada componente individualmente e depois reunir todos eles em um pequeno projeto prático.

## 1. Objetivos da aula

Ao final desta aula nós seremos capazes de:

* utilizar o JCheckBox para opções independentes
* utilizar o JRadioButton para escolhas entre alternativas
* organizar JRadioButton utilizando ButtonGroup
* utilizar o JPasswordField para entrada de senhas
* utilizar o JFormattedTextField para dados com formato definido
* utilizar o JSpinner para seleção de valores
* capturar os valores informados pelo usuário
* validar alguns campos do formulário
* apresentar os dados utilizando JOptionPane
* construir uma tela organizada utilizando o editor visual do NetBeans

## 2. Projeto que nós vamos desenvolver

Nós vamos criar um projeto chamado:

`AulaComponentesSwing`

Dentro dele vamos criar uma tela de cadastro simples chamada:

`FrmCadastroAluno`

A tela terá os seguintes dados:

* Nome
* Senha
* Telefone
* Idade
* Turno
* Cursos de interesse

Para construir esse cadastro nós vamos utilizar os componentes estudados nesta aula.

## 3. Componentes que nós vamos conhecer

### JCheckBox

O JCheckBox representa uma opção que pode estar marcada ou desmarcada.

Nós utilizamos esse componente quando o usuário pode escolher várias opções ao mesmo tempo.

Exemplo:

* Java
* Banco de Dados
* Desenvolvimento Web

Nesse caso o aluno pode selecionar somente uma opção, duas opções ou todas elas.

### JRadioButton

O JRadioButton também representa uma escolha, porém normalmente nós utilizamos esse componente quando queremos que o usuário selecione apenas uma alternativa entre várias.

Exemplo:

* Manhã
* Tarde
* Noite

Porém existe um detalhe importante. Colocar vários JRadioButton na tela não impede que todos sejam selecionados ao mesmo tempo.

Para controlar isso nós utilizamos o ButtonGroup.

### ButtonGroup

O ButtonGroup não aparece visualmente na tela do sistema.

Ele serve para agrupar vários JRadioButton e permitir que somente um deles fique selecionado por vez.

Portanto, nós podemos pensar da seguinte maneira:

JRadioButton representa a opção.

ButtonGroup controla o conjunto de opções.

### JPasswordField

O JPasswordField é utilizado para receber informações que não devem aparecer diretamente na tela.

O exemplo mais comum é a senha.

Quando o usuário digita, os caracteres são ocultados.

### JFormattedTextField

O JFormattedTextField é um campo de texto que pode trabalhar com uma máscara de preenchimento.

Nós podemos utilizá lo em informações como:

* telefone
* data
* CEP
* códigos padronizados

Nesta aula nós vamos utilizar uma máscara para telefone.

### JSpinner

O JSpinner permite selecionar valores utilizando pequenas setas.

Ele é muito útil para valores numéricos ou informações que possuem uma sequência definida.

Exemplos:

* idade
* quantidade
* número de parcelas
* quantidade de produtos

Nesta aula nós vamos utilizar o JSpinner para informar a idade do aluno.

## 4. Criando o projeto no NetBeans

Vamos iniciar nosso projeto do zero.

### Passo 1

Abra o NetBeans.

### Passo 2

Acesse:

`File > New Project`

### Passo 3

Escolha um projeto Java com Ant, conforme o padrão que nós estamos utilizando em aula.

### Passo 4

Defina o nome do projeto como:

`AulaComponentesSwing`

### Passo 5

Finalize a criação do projeto.

## 5. Criando o formulário

Agora nós vamos criar nossa tela.

No projeto, clique com o botão direito sobre o pacote principal.

Escolha:

`New > JFrame Form`

Nome da classe:

`FrmCadastroAluno`

Depois de criar o formulário, nós vamos utilizar a aba Design para montar nossa interface.

## 6. Estrutura da tela

Nossa tela poderá ser organizada com os seguintes componentes:

### Dados básicos

* JLabel com o texto Nome
* JTextField chamado txtNome
* JLabel com o texto Senha
* JPasswordField chamado txtSenha
* JLabel com o texto Telefone
* JFormattedTextField chamado txtTelefone
* JLabel com o texto Idade
* JSpinner chamado spnIdade

### Turno

* JLabel com o texto Turno
* JRadioButton chamado rbManha
* JRadioButton chamado rbTarde
* JRadioButton chamado rbNoite
* ButtonGroup chamado grupoTurno

### Cursos de interesse

* JLabel com o texto Cursos de Interesse
* JCheckBox chamado chkJava
* JCheckBox chamado chkBanco
* JCheckBox chamado chkWeb

### Botões

* JButton chamado btnCadastrar
* JButton chamado btnLimpar

## 7. Trabalhando com JCheckBox

Vamos começar pelos Check Boxes.

Na paleta do NetBeans localize o componente Check Box e adicione três componentes ao formulário.

Configure os textos:

`Java`

`Banco de Dados`

`Desenvolvimento Web`

Depois altere os nomes das variáveis para:

`chkJava`

`chkBanco`

`chkWeb`

### Como saber se um JCheckBox está marcado

Nós utilizamos o método:

```java
isSelected()
```

Exemplo:

```java
if (chkJava.isSelected()) {
    JOptionPane.showMessageDialog(this, "Java foi selecionado");
}
```

O método `isSelected()` retorna verdadeiro quando o componente está marcado e falso quando não está marcado.

## 8. Trabalhando com JRadioButton

Agora vamos adicionar três Radio Buttons.

Textos:

`Manhã`

`Tarde`

`Noite`

Nomes das variáveis:

`rbManha`

`rbTarde`

`rbNoite`

Se nós executarmos o formulário neste momento, será possível selecionar mais de um Radio Button.

Isso acontece porque eles ainda não pertencem ao mesmo grupo.

## 9. Criando o ButtonGroup

Na paleta do NetBeans procure o componente Button Group.

Adicione um ButtonGroup ao formulário.

Ele aparecerá na área de componentes não visuais do NetBeans.

Altere o nome da variável para:

`grupoTurno`

Agora nós precisamos colocar os três Radio Buttons dentro desse grupo.

Selecione cada Radio Button e configure sua propriedade `buttonGroup` para:

`grupoTurno`

Faça isso com:

`rbManha`

`rbTarde`

`rbNoite`

Depois dessa configuração somente um turno poderá ser selecionado por vez.

## 10. Identificando o RadioButton selecionado

Podemos verificar cada opção utilizando `isSelected()`.

```java
String turno = "";

if (rbManha.isSelected()) {
    turno = "Manhã";
}

if (rbTarde.isSelected()) {
    turno = "Tarde";
}

if (rbNoite.isSelected()) {
    turno = "Noite";
}
```

Ao final desse código a variável `turno` armazenará a opção escolhida pelo usuário.

## 11. Trabalhando com JPasswordField

Agora vamos adicionar um Password Field ao nosso formulário.

Altere o nome da variável para:

`txtSenha`

Para capturar a senha nós podemos utilizar:

```java
String senha = new String(txtSenha.getPassword());
```

### Por que não utilizamos getText

O JPasswordField possui o método `getPassword()`, que retorna um vetor de caracteres.

Por isso nós podemos converter o resultado para String quando precisarmos trabalhar com o conteúdo digitado.

Exemplo:

```java
char[] senhaDigitada = txtSenha.getPassword();
String senha = new String(senhaDigitada);
```

Em sistemas reais nós devemos ter atenção especial ao tratamento de senhas e nunca armazená las de forma aberta no banco de dados.

Nesta aula nosso objetivo é compreender o funcionamento do componente gráfico.

## 12. Trabalhando com JFormattedTextField

Agora vamos adicionar um Formatted Field ao formulário.

Nome da variável:

`txtTelefone`

Vamos utilizar esse componente para receber um telefone.

### Configurando a máscara pelo NetBeans

Selecione o componente.

Na janela de propriedades localize a propriedade `formatterFactory`.

Abra o editor da propriedade e escolha uma máscara.

Podemos utilizar:

```text
(##) ##### ####
```

O símbolo `#` representa uma posição numérica.

Assim o usuário deverá preencher o telefone seguindo o formato definido.

### Capturando o valor

```java
String telefone = txtTelefone.getText();
```

## 13. Trabalhando com JSpinner

Agora vamos adicionar um Spinner.

Nome da variável:

`spnIdade`

Nós vamos configurar o Spinner para trabalhar com idade.

Podemos definir:

* valor inicial igual a 18
* valor mínimo igual a 10
* valor máximo igual a 100
* incremento igual a 1

No NetBeans isso pode ser configurado pela propriedade `model`.

Também podemos fazer por código:

```java
spnIdade.setModel(new SpinnerNumberModel(18, 10, 100, 1));
```

Para utilizar `SpinnerNumberModel`, precisamos do import:

```java
import javax.swing.SpinnerNumberModel;
```

### Capturando o valor do Spinner

```java
int idade = (int) spnIdade.getValue();
```

## 14. Programando o botão Cadastrar

Agora nós vamos reunir todos os componentes.

Dê dois cliques no botão Cadastrar para criar o evento `ActionPerformed`.

Dentro dele nós vamos capturar as informações do formulário.

```java
private void btnCadastrarActionPerformed(java.awt.event.ActionEvent evt) {

    String nome = txtNome.getText();
    String senha = new String(txtSenha.getPassword());
    String telefone = txtTelefone.getText();
    int idade = (int) spnIdade.getValue();

    String turno = "Não informado";

    if (rbManha.isSelected()) {
        turno = "Manhã";
    }

    if (rbTarde.isSelected()) {
        turno = "Tarde";
    }

    if (rbNoite.isSelected()) {
        turno = "Noite";
    }

    String cursos = "";

    if (chkJava.isSelected()) {
        cursos += "Java\n";
    }

    if (chkBanco.isSelected()) {
        cursos += "Banco de Dados\n";
    }

    if (chkWeb.isSelected()) {
        cursos += "Desenvolvimento Web\n";
    }

    JOptionPane.showMessageDialog(
        this,
        "DADOS DO ALUNO\n\n" +
        "Nome: " + nome + "\n" +
        "Telefone: " + telefone + "\n" +
        "Idade: " + idade + "\n" +
        "Turno: " + turno + "\n\n" +
        "Cursos de Interesse:\n" + cursos
    );
}
```

Observe que nós capturamos a senha, mas não mostramos esse valor na mensagem.

Essa é uma prática importante. Senhas não devem ser exibidas desnecessariamente.

## 15. Importando JOptionPane

Caso o NetBeans não tenha feito a importação automaticamente, adicione no início da classe:

```java
import javax.swing.JOptionPane;
```

## 16. Criando uma validação simples

Agora nós vamos melhorar nosso formulário.

Antes de cadastrar, vamos verificar se o nome foi informado.

```java
if (txtNome.getText().trim().isEmpty()) {
    JOptionPane.showMessageDialog(
        this,
        "Informe o nome do aluno"
    );

    txtNome.requestFocus();
    return;
}
```

Também podemos verificar se um turno foi selecionado.

```java
if (!rbManha.isSelected()
        && !rbTarde.isSelected()
        && !rbNoite.isSelected()) {

    JOptionPane.showMessageDialog(
        this,
        "Selecione um turno"
    );

    return;
}
```

## 17. Validando a senha

Podemos exigir uma senha mínima.

```java
String senha = new String(txtSenha.getPassword());

if (senha.length() < 4) {
    JOptionPane.showMessageDialog(
        this,
        "A senha deve possuir pelo menos 4 caracteres"
    );

    txtSenha.requestFocus();
    return;
}
```

Neste exemplo nós estamos criando apenas uma validação didática.

Em um sistema profissional nós precisaríamos aplicar regras de segurança adequadas e utilizar técnicas apropriadas para armazenamento de senhas.

## 18. Validando os Check Boxes

Também podemos exigir que pelo menos um curso seja selecionado.

```java
if (!chkJava.isSelected()
        && !chkBanco.isSelected()
        && !chkWeb.isSelected()) {

    JOptionPane.showMessageDialog(
        this,
        "Selecione pelo menos um curso de interesse"
    );

    return;
}
```

## 19. Programando o botão Limpar

Agora vamos programar o botão Limpar.

```java
private void btnLimparActionPerformed(java.awt.event.ActionEvent evt) {

    txtNome.setText("");
    txtSenha.setText("");
    txtTelefone.setText("");

    spnIdade.setValue(18);

    grupoTurno.clearSelection();

    chkJava.setSelected(false);
    chkBanco.setSelected(false);
    chkWeb.setSelected(false);

    txtNome.requestFocus();
}
```

Observe o comando:

```java
grupoTurno.clearSelection();
```

Ele remove a seleção dos Radio Buttons pertencentes ao ButtonGroup.

## 20. Código completo da lógica do cadastro

Uma possível versão do botão Cadastrar pode ficar assim:

```java
private void btnCadastrarActionPerformed(java.awt.event.ActionEvent evt) {

    String nome = txtNome.getText().trim();
    String senha = new String(txtSenha.getPassword());

    if (nome.isEmpty()) {
        JOptionPane.showMessageDialog(
            this,
            "Informe o nome do aluno"
        );

        txtNome.requestFocus();
        return;
    }

    if (senha.length() < 4) {
        JOptionPane.showMessageDialog(
            this,
            "A senha deve possuir pelo menos 4 caracteres"
        );

        txtSenha.requestFocus();
        return;
    }

    if (!rbManha.isSelected()
            && !rbTarde.isSelected()
            && !rbNoite.isSelected()) {

        JOptionPane.showMessageDialog(
            this,
            "Selecione um turno"
        );

        return;
    }

    if (!chkJava.isSelected()
            && !chkBanco.isSelected()
            && !chkWeb.isSelected()) {

        JOptionPane.showMessageDialog(
            this,
            "Selecione pelo menos um curso de interesse"
        );

        return;
    }

    String telefone = txtTelefone.getText();
    int idade = (int) spnIdade.getValue();

    String turno = "";

    if (rbManha.isSelected()) {
        turno = "Manhã";
    }

    if (rbTarde.isSelected()) {
        turno = "Tarde";
    }

    if (rbNoite.isSelected()) {
        turno = "Noite";
    }

    String cursos = "";

    if (chkJava.isSelected()) {
        cursos += "Java\n";
    }

    if (chkBanco.isSelected()) {
        cursos += "Banco de Dados\n";
    }

    if (chkWeb.isSelected()) {
        cursos += "Desenvolvimento Web\n";
    }

    JOptionPane.showMessageDialog(
        this,
        "CADASTRO REALIZADO\n\n" +
        "Nome: " + nome + "\n" +
        "Telefone: " + telefone + "\n" +
        "Idade: " + idade + "\n" +
        "Turno: " + turno + "\n\n" +
        "Cursos de Interesse:\n" + cursos
    );
}
```

## 21. Comparando os componentes

### JCheckBox

Nós utilizamos quando várias opções podem ser selecionadas.

Exemplo:

Cursos de interesse.

### JRadioButton

Nós utilizamos quando o usuário precisa selecionar uma opção entre várias alternativas.

Exemplo:

Turno do curso.

### ButtonGroup

Nós utilizamos para fazer os Radio Buttons funcionarem como um único grupo de escolha.

### JPasswordField

Nós utilizamos quando precisamos ocultar o conteúdo digitado.

Exemplo:

Senha.

### JFormattedTextField

Nós utilizamos quando o campo precisa seguir um formato específico.

Exemplo:

Telefone.

### JSpinner

Nós utilizamos para selecionar valores dentro de uma sequência.

Exemplo:

Idade.

## 22. Atividade prática guiada

Agora nós vamos construir uma segunda versão do formulário.

Crie um cadastro de funcionário contendo:

* Nome
* Senha de acesso
* Data de nascimento
* Quantidade de dependentes
* Setor
* Benefícios

### Componentes obrigatórios

Utilize:

* JTextField para Nome
* JPasswordField para Senha
* JFormattedTextField para Data de Nascimento
* JSpinner para Quantidade de Dependentes
* três JRadioButton para Setor
* um ButtonGroup para controlar os setores
* três JCheckBox para Benefícios
* JButton para Cadastrar
* JButton para Limpar

### Sugestão para os setores

* Administrativo
* Comercial
* Tecnologia

### Sugestão para os benefícios

* Vale Transporte
* Vale Alimentação
* Plano de Saúde

## 23. Desafio

Depois de concluir a atividade, nós vamos adicionar algumas regras.

### Regra 1

O nome não pode ficar vazio.

### Regra 2

A senha deve possuir pelo menos 6 caracteres.
   int quantidade = txtSenha.getPassword().length;

### Regra 3

Um setor deve ser selecionado.

### Regra 4

A quantidade de dependentes deve ficar entre 0 e 10.

### Regra 5

Ao clicar em Cadastrar, todos os dados devem ser apresentados em um JOptionPane.

A senha não deverá aparecer na mensagem.

## 24. Desafio extra

Vamos acrescentar mais um JCheckBox chamado:

`Funcionário Ativo`

Nome da variável:

`chkAtivo`

Se estiver marcado, a mensagem deverá apresentar:

`Situação: Ativo`

Caso contrário:

`Situação: Inativo`

Uma possível lógica seria:

```java
String situacao;

if (chkAtivo.isSelected()) {
    situacao = "Ativo";
} else {
    situacao = "Inativo";
}
```

## 25. Erros comuns

### Radio Buttons permitindo várias seleções

Provavelmente nós esquecemos de colocar os componentes dentro do mesmo ButtonGroup.

### Spinner retornando Object

O método `getValue()` retorna um objeto.

Quando estamos utilizando números inteiros, podemos converter:

```java
int idade = (int) spnIdade.getValue();
```

### Senha aparecendo como vetor

O método `getPassword()` retorna um vetor de caracteres.

Podemos utilizar:

```java
String senha = new String(txtSenha.getPassword());
```

### Máscara não funcionando

Devemos conferir a propriedade `formatterFactory` do JFormattedTextField.

### Check Box não sendo identificado

Devemos utilizar:

```java
chkJava.isSelected()
```

## 26. Perguntas para revisão

1. Qual é a diferença entre JCheckBox e JRadioButton?

2. Para que serve o ButtonGroup?

3. O ButtonGroup aparece na tela do sistema?

4. Qual método utilizamos para descobrir se um JCheckBox está marcado?

5. Qual método utilizamos para capturar a senha de um JPasswordField?

6. Para que serve o JFormattedTextField?

7. Qual componente podemos utilizar para selecionar idade ou quantidade?

8. Como podemos limpar a seleção de um ButtonGroup?

9. Qual método utilizamos para obter o valor de um JSpinner?

10. Por que não devemos exibir senhas em mensagens do sistema?

## 27. Exercício individual

Crie um novo projeto chamado:

`ExercicioComponentesSwing`

Crie um JFrame chamado:

`FrmCadastroUsuario`

O formulário deverá possuir:

* Nome
* Senha
* Telefone
* Idade
* Perfil de acesso
* Recursos permitidos

### Perfil de acesso

Utilize três JRadioButton:

* Administrador
* Professor
* Aluno

Os três deverão pertencer ao mesmo ButtonGroup.

### Recursos permitidos

Utilize três JCheckBox:

* Cadastro
* Consulta
* Relatórios

### Idade

Utilize JSpinner com valores entre 16 e 100.

### Telefone

Utilize JFormattedTextField.

### Botões

Crie:

* Cadastrar
* Limpar

O botão Cadastrar deverá validar os campos e apresentar os dados utilizando JOptionPane.

O botão Limpar deverá retornar o formulário ao estado inicial.

## 28. Encerramento da aula

Nesta aula nós conhecemos componentes que deixam nossos formulários Java Swing muito mais completos.

Nós aprendemos que cada componente possui uma finalidade específica.

O JCheckBox permite múltiplas escolhas.

O JRadioButton permite selecionar alternativas.

O ButtonGroup organiza essas alternativas para permitir somente uma escolha.

O JPasswordField protege visualmente a informação digitada.

O JFormattedTextField controla o formato da entrada.

O JSpinner facilita a seleção de valores.

Mais importante do que decorar o nome dos componentes é entender quando cada um deles deve ser utilizado.

Quando nós começamos a escolher o componente adequado para cada tipo de informação, nossas interfaces ficam mais organizadas e também mais simples para o usuário utilizar.


