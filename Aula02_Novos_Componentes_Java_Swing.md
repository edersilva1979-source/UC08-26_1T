# Aula 2: Novos Componentes Java Swing no NetBeans

## JComboBox, JList, JTextArea, JEditorPane e JTabbedPane

Nesta aula nós vamos continuar evoluindo nossos conhecimentos em Java Swing utilizando o NetBeans.

Na aula anterior, nós conhecemos componentes como `JCheckBox`, `JRadioButton`, `ButtonGroup`, `JPasswordField`, `JFormattedTextField` e `JSpinner`.

Agora nós vamos utilizar esses conhecimentos junto com novos componentes para construir uma interface mais completa.

Ainda não vamos trabalhar com banco de dados.

Nosso objetivo será compreender como cada componente funciona, quando utilizar e como capturar as informações preenchidas pelo usuário.

---

# 1. Objetivos da aula

Ao final desta aula, nós deveremos ser capazes de:

* Utilizar o `JComboBox`
* Utilizar o `JList`
* Utilizar o `JTextArea`
* Utilizar o `JEditorPane`
* Utilizar o `JTabbedPane`
* Capturar valores selecionados pelo usuário
* Trabalhar com múltiplas seleções
* Organizar uma tela utilizando abas
* Exibir textos maiores dentro da aplicação
* Integrar componentes estudados anteriormente
* Criar uma interface Java Swing mais completa

---

# 2. Projeto da aula

Nesta aula nós vamos criar um projeto chamado:

```text
Aula02_ComponentesSwing
```

Dentro desse projeto nós vamos criar uma tela chamada:

```text
FrmCadastroCurso
```

A ideia será desenvolver um pequeno formulário para cadastro de participantes de cursos.

Nós não vamos salvar os dados em banco de dados.

Por enquanto, vamos preencher a tela, capturar as informações e apresentar os dados utilizando `JOptionPane`.

---

# 3. Criando o projeto no NetBeans

Vamos iniciar criando um novo projeto.

No NetBeans:

1. Vamos acessar `File`
2. Vamos escolher `New Project`
3. Vamos selecionar `Java Application`
4. Vamos definir o nome:

```text
Aula02_ComponentesSwing
```

Depois de criar o projeto, vamos criar um novo formulário Swing.

Vamos clicar com o botão direito sobre o pacote do projeto e escolher:

```text
New
JFrame Form
```

Vamos utilizar o nome:

```text
FrmCadastroCurso
```

---

# 4. Conhecendo o JComboBox

O `JComboBox` permite apresentar várias opções dentro de uma lista suspensa.

Nós utilizamos esse componente quando queremos permitir que o usuário escolha uma opção entre várias possibilidades.

Alguns exemplos:

* Cidade
* Estado
* Curso
* Categoria
* Turno
* Forma de pagamento
* Departamento

Visualmente, o componente apresenta uma caixa com uma seta.

Quando nós clicamos nessa seta, as opções ficam disponíveis.

---

# 5. Adicionando um JComboBox

Vamos adicionar um `JComboBox` ao nosso formulário.

Na paleta do NetBeans, vamos localizar:

```text
Combo Box
```

Vamos arrastar o componente para a tela.

Podemos alterar o nome da variável para:

```java
cmbCurso
```

Agora vamos adicionar algumas opções.

Na propriedade `model`, podemos cadastrar:

```text
Selecione
Java
Python
JavaScript
Banco de Dados
Git e GitHub
```

Mesmo que nesta aula ainda não trabalhemos com banco de dados, podemos utilizar esse texto apenas como uma opção de curso.

---

# 6. Capturando o valor do JComboBox

Para descobrir qual item foi selecionado, nós podemos utilizar:

```java
String curso = cmbCurso.getSelectedItem().toString();
```

Depois podemos apresentar o resultado:

```java
JOptionPane.showMessageDialog(
        this,
        "Curso selecionado: " + curso
);
```

---

# 7. Validando o JComboBox

É comum nós adicionarmos uma primeira opção chamada `Selecione`.

Nesse caso podemos verificar se o usuário realmente escolheu alguma opção.

```java
if (cmbCurso.getSelectedIndex() == 0) {

    JOptionPane.showMessageDialog(
            this,
            "Selecione um curso."
    );

}
```

O método:

```java
getSelectedIndex()
```

retorna a posição do item selecionado.

A primeira posição é:

```text
0
```

---

# 8. Conhecendo o JList

No Java Swing, o componente utilizado para representar uma lista é o `JList`.

Muitas vezes nós ouvimos o nome ListBox em outras tecnologias.

No Swing, o componente equivalente é o:

```java
JList
```

A principal diferença para o `JComboBox` é que o `JList` normalmente mantém vários itens visíveis na tela.

Ele também pode permitir que o usuário selecione mais de uma opção.

---

# 9. Criando uma lista de interesses

Vamos utilizar um `JList` para permitir que o participante informe suas áreas de interesse.

Vamos adicionar os seguintes itens:

```text
Programação
Desenvolvimento Web
Aplicativos Desktop
Redes
Segurança
Inteligência Artificial
```

Vamos nomear o componente como:

```java
lstInteresses
```

---

# 10. Capturando uma opção do JList

Se nós configurarmos o `JList` para aceitar apenas uma seleção, podemos utilizar:

```java
String interesse = lstInteresses.getSelectedValue();
```

Depois:

```java
JOptionPane.showMessageDialog(
        this,
        "Interesse selecionado: " + interesse
);
```

---

# 11. Trabalhando com várias seleções

O `JList` também permite selecionar vários itens.

Nesse caso podemos utilizar:

```java
List<String> interesses =
        lstInteresses.getSelectedValuesList();
```

Será necessário importar:

```java
import java.util.List;
```

Depois podemos apresentar:

```java
JOptionPane.showMessageDialog(
        this,
        "Interesses: " + interesses
);
```

---

# 12. Conhecendo o JTextArea

Até agora nós utilizamos principalmente o `JTextField`.

O `JTextField` funciona muito bem para textos pequenos.

Por exemplo:

* Nome
* Cidade
* Telefone
* E mail

Quando precisamos permitir que o usuário escreva textos maiores, podemos utilizar o:

```java
JTextArea
```

Ele permite escrever várias linhas.

---

# 13. Exemplos de uso do JTextArea

Nós podemos utilizar um `JTextArea` para:

* Observações
* Comentários
* Descrição
* Endereço completo
* Histórico
* Informações adicionais
* Mensagens

No nosso projeto vamos criar um campo chamado:

```java
txtObservacoes
```

---

# 14. Capturando o conteúdo do JTextArea

Para capturar o texto digitado, utilizamos:

```java
String observacoes =
        txtObservacoes.getText();
```

Depois podemos apresentar:

```java
JOptionPane.showMessageDialog(
        this,
        observacoes
);
```

---

# 15. Quebra automática de linha no JTextArea

Uma configuração muito útil é permitir que o texto seja automaticamente ajustado dentro do componente.

Podemos utilizar:

```java
txtObservacoes.setLineWrap(true);
txtObservacoes.setWrapStyleWord(true);
```

O primeiro comando permite a quebra automática de linha.

O segundo evita que uma palavra seja cortada no meio quando ocorrer a quebra.

---

# 16. Conhecendo o JEditorPane

O `JEditorPane` é um componente utilizado para apresentar ou editar conteúdos com maior flexibilidade.

Ele pode trabalhar com diferentes tipos de conteúdo.

Um dos usos mais interessantes para nós é apresentar texto formatado utilizando HTML.

Podemos utilizar esse componente para:

* Instruções
* Informações do sistema
* Termos de uso
* Ajuda
* Textos explicativos
* Conteúdo HTML simples

---

# 17. Criando um JEditorPane

Vamos adicionar um `JEditorPane` ao formulário.

Vamos chamar:

```java
edtInformacoes
```

Podemos configurar o tipo de conteúdo:

```java
edtInformacoes.setContentType("text/html");
```

Agora podemos escrever:

```java
edtInformacoes.setText(
        "<html>"
        + "<h2>Curso Java Swing</h2>"
        + "<p>Bem vindo ao nosso formulário de inscrição.</p>"
        + "<p>Preencha os dados corretamente.</p>"
        + "</html>"
);
```

---

# 18. Impedindo edição no JEditorPane

Em muitos casos nós vamos utilizar o `JEditorPane` apenas para mostrar informações.

Nesse caso podemos impedir que o usuário altere o conteúdo.

```java
edtInformacoes.setEditable(false);
```

Assim ele funcionará como uma área de leitura.

---

# 19. Conhecendo o JTabbedPane

Agora nós vamos conhecer um componente muito importante para organização de interfaces.

O `JTabbedPane` permite criar abas dentro da mesma janela.

Nós encontramos esse tipo de organização em muitos programas.

Por exemplo:

```text
Cadastro
Consulta
Configurações
Relatórios
Ajuda
```

Cada aba pode conter vários componentes diferentes.

---

# 20. Criando abas no NetBeans

Na paleta do NetBeans vamos localizar:

```text
Tabbed Pane
```

Vamos arrastar para o formulário.

Podemos chamar o componente de:

```java
tabPrincipal
```

Vamos criar três abas:

```text
Cadastro
Preferências
Informações
```

---

# 21. Aba Cadastro

Na primeira aba vamos colocar:

* Nome
* Telefone
* Data de nascimento
* Senha
* Curso
* Turno

Podemos utilizar componentes já estudados.

Exemplo:

```text
Nome
JTextField

Telefone
JFormattedTextField

Data de nascimento
JFormattedTextField

Senha
JPasswordField

Curso
JComboBox

Turno
JRadioButton
```

Para o turno podemos criar:

```text
Manhã
Tarde
Noite
```

E colocar os três `JRadioButton` dentro de um `ButtonGroup`.

---

# 22. Aba Preferências

Na segunda aba podemos utilizar:

```text
JList
JCheckBox
JSpinner
JTextArea
```

Podemos criar:

### Áreas de interesse

```java
lstInteresses
```

### Recursos que deseja estudar

```text
Git
Java Swing
APIs
Testes
```

Podemos utilizar `JCheckBox`.

### Quantidade de horas disponíveis por semana

Podemos utilizar:

```java
JSpinner
```

### Observações

Podemos utilizar:

```java
JTextArea
```

---

# 23. Aba Informações

Na terceira aba podemos utilizar:

```java
JEditorPane
```

Vamos apresentar informações sobre o curso.

Exemplo:

```java
edtInformacoes.setContentType("text/html");

edtInformacoes.setText(
        "<html>"
        + "<h1>Informações do Curso</h1>"
        + "<p>Este curso apresenta os fundamentos do desenvolvimento Desktop com Java Swing.</p>"
        + "<p>Nós vamos aprender a construir interfaces gráficas progressivamente.</p>"
        + "</html>"
);

edtInformacoes.setEditable(false);
```

---

# 24. Projeto prático da aula

Agora nós vamos juntar vários componentes dentro do mesmo formulário.

Nosso formulário terá:

## Aba Cadastro

```text
Nome
Telefone
Data de nascimento
Senha
Curso
Turno
```

## Aba Preferências

```text
Interesses
Conteúdos desejados
Horas disponíveis
Observações
```

## Aba Informações

```text
Descrição do curso
Instruções
```

---

# 25. Nomes sugeridos para os componentes

Podemos organizar os componentes da seguinte forma:

```text
txtNome

fmtTelefone

fmtNascimento

pwdSenha

cmbCurso

rbManha

rbTarde

rbNoite

grpTurno

lstInteresses

chkGit

chkSwing

chkApi

chkTestes

spnHoras

txtObservacoes

edtInformacoes

tabPrincipal

btnCadastrar

btnLimpar

btnSair
```

---

# 26. Capturando o nome

```java
String nome =
        txtNome.getText();
```

---

# 27. Capturando o telefone

```java
String telefone =
        fmtTelefone.getText();
```

---

# 28. Capturando a senha

Como o `JPasswordField` retorna um vetor de caracteres, podemos utilizar:

```java
String senha =
        new String(
                pwdSenha.getPassword()
        );
```

---

# 29. Capturando o curso

```java
String curso =
        cmbCurso
        .getSelectedItem()
        .toString();
```

---

# 30. Capturando o turno

Podemos iniciar uma variável:

```java
String turno = "";
```

Depois:

```java
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

---

# 31. Capturando os interesses

```java
List<String> interesses =
        lstInteresses
        .getSelectedValuesList();
```

---

# 32. Capturando os CheckBox

Podemos criar uma variável:

```java
String conteudos = "";
```

Depois:

```java
if (chkGit.isSelected()) {

    conteudos += "Git\n";

}

if (chkSwing.isSelected()) {

    conteudos += "Java Swing\n";

}

if (chkApi.isSelected()) {

    conteudos += "APIs\n";

}

if (chkTestes.isSelected()) {

    conteudos += "Testes\n";

}
```

---

# 33. Capturando o Spinner

```java
int horas =
        Integer.parseInt(
                spnHoras
                .getValue()
                .toString()
        );
```

---

# 34. Capturando as observações

```java
String observacoes =
        txtObservacoes.getText();
```

---

# 35. Criando o botão Cadastrar

Agora nós vamos programar o botão:

```java
btnCadastrar
```

Podemos utilizar o seguinte exemplo:

```java
private void btnCadastrarActionPerformed(
        java.awt.event.ActionEvent evt
) {

    String nome =
            txtNome.getText();

    String telefone =
            fmtTelefone.getText();

    String senha =
            new String(
                    pwdSenha.getPassword()
            );

    String curso =
            cmbCurso
            .getSelectedItem()
            .toString();

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

    List<String> interesses =
            lstInteresses
            .getSelectedValuesList();

    String conteudos = "";

    if (chkGit.isSelected()) {
        conteudos += "Git\n";
    }

    if (chkSwing.isSelected()) {
        conteudos += "Java Swing\n";
    }

    if (chkApi.isSelected()) {
        conteudos += "APIs\n";
    }

    if (chkTestes.isSelected()) {
        conteudos += "Testes\n";
    }

    int horas =
            Integer.parseInt(
                    spnHoras
                    .getValue()
                    .toString()
            );

    String observacoes =
            txtObservacoes.getText();

    JOptionPane.showMessageDialog(
            this,
            "DADOS DO PARTICIPANTE\n\n"
            + "Nome: " + nome
            + "\nTelefone: " + telefone
            + "\nCurso: " + curso
            + "\nTurno: " + turno
            + "\nInteresses: " + interesses
            + "\n\nConteúdos:\n"
            + conteudos
            + "\nHoras disponíveis: "
            + horas
            + "\n\nObservações:\n"
            + observacoes
    );

}
```

Não esqueçamos de importar:

```java
import java.util.List;
import javax.swing.JOptionPane;
```

---

# 36. Criando algumas validações

Antes de apresentar os dados, podemos verificar se os principais campos foram preenchidos.

Exemplo:

```java
if (txtNome.getText().trim().isEmpty()) {

    JOptionPane.showMessageDialog(
            this,
            "Informe o nome."
    );

    txtNome.requestFocus();

    return;
}
```

---

# 37. Validando o curso

```java
if (cmbCurso.getSelectedIndex() == 0) {

    JOptionPane.showMessageDialog(
            this,
            "Selecione um curso."
    );

    return;
}
```

---

# 38. Validando o turno

```java
if (
        !rbManha.isSelected()
        && !rbTarde.isSelected()
        && !rbNoite.isSelected()
) {

    JOptionPane.showMessageDialog(
            this,
            "Selecione um turno."
    );

    return;
}
```

---

# 39. Validando o JList

Podemos verificar se nenhum interesse foi selecionado.

```java
if (lstInteresses.isSelectionEmpty()) {

    JOptionPane.showMessageDialog(
            this,
            "Selecione pelo menos uma área de interesse."
    );

    return;
}
```

---

# 40. Criando o botão Limpar

Agora nós vamos criar um botão para limpar o formulário.

```java
private void btnLimparActionPerformed(
        java.awt.event.ActionEvent evt
) {

    txtNome.setText("");

    fmtTelefone.setText("");

    fmtNascimento.setText("");

    pwdSenha.setText("");

    cmbCurso.setSelectedIndex(0);

    grpTurno.clearSelection();

    lstInteresses.clearSelection();

    chkGit.setSelected(false);

    chkSwing.setSelected(false);

    chkApi.setSelected(false);

    chkTestes.setSelected(false);

    spnHoras.setValue(1);

    txtObservacoes.setText("");

    tabPrincipal.setSelectedIndex(0);

    txtNome.requestFocus();

}
```

Observe que também utilizamos:

```java
tabPrincipal.setSelectedIndex(0);
```

Isso faz com que o sistema volte automaticamente para a primeira aba.

---

# 41. Criando o botão Sair

Podemos criar:

```java
private void btnSairActionPerformed(
        java.awt.event.ActionEvent evt
) {

    int resposta =
            JOptionPane.showConfirmDialog(
                    this,
                    "Deseja realmente sair?",
                    "Confirmação",
                    JOptionPane.YES_NO_OPTION
            );

    if (
            resposta
            == JOptionPane.YES_OPTION
    ) {

        System.exit(0);

    }

}
```

---

# 42. Entendendo melhor o JTabbedPane

O `JTabbedPane` possui vários métodos úteis.

## Descobrir qual aba está selecionada

```java
int aba =
        tabPrincipal.getSelectedIndex();
```

## Selecionar uma determinada aba

Primeira aba:

```java
tabPrincipal.setSelectedIndex(0);
```

Segunda aba:

```java
tabPrincipal.setSelectedIndex(1);
```

Terceira aba:

```java
tabPrincipal.setSelectedIndex(2);
```

---

# 43. Mudando de aba após uma validação

Imagine que o usuário está na aba Preferências, mas esqueceu de preencher o nome.

Nós podemos fazer o sistema voltar para a aba Cadastro.

```java
if (txtNome.getText().trim().isEmpty()) {

    tabPrincipal.setSelectedIndex(0);

    JOptionPane.showMessageDialog(
            this,
            "Informe o nome."
    );

    txtNome.requestFocus();

    return;
}
```

Isso melhora bastante a experiência de uso.

---

# 44. Comparando os componentes

| Componente | Utilização |
| --- | --- |
| `JComboBox` | Escolher uma opção em uma lista suspensa |
| `JList` | Mostrar várias opções visíveis |
| `JTextArea` | Escrever textos maiores |
| `JEditorPane` | Mostrar ou editar conteúdos formatados |
| `JTabbedPane` | Organizar a interface em abas |
| `JCheckBox` | Selecionar opções independentes |
| `JRadioButton` | Escolher uma opção entre várias |
| `ButtonGroup` | Agrupar Radio Buttons |
| `JPasswordField` | Digitar senha |
| `JFormattedTextField` | Trabalhar com campos formatados |
| `JSpinner` | Selecionar valores incrementais |

---

# 45. Atividade prática guiada

Agora nós vamos construir uma tela completa de inscrição para um curso.

## Estrutura da tela

### Aba 1: Dados pessoais

Adicionar:

```text
Nome
Telefone
Data de nascimento
Senha
Curso
Turno
```

### Aba 2: Preferências

Adicionar:

```text
Lista de interesses
CheckBox de conteúdos
Spinner para horas disponíveis
Área de observações
```

### Aba 3: Informações

Adicionar:

```text
JEditorPane
```

O `JEditorPane` deverá apresentar uma descrição do curso e instruções para preenchimento.

---

# 46. Exercício 1

Vamos criar um formulário chamado:

```text
FrmCadastroEvento
```

O formulário deverá possuir um `JTabbedPane` com três abas.

## Aba Participante

Criar:

```text
Nome
Telefone
Senha
Cidade
Faixa etária
```

Utilizar:

```text
JTextField
JFormattedTextField
JPasswordField
JComboBox
JSpinner
```

---

# 47. Exercício 2

Na aba Preferências, criar:

```text
JList
```

com os temas:

```text
Java
Web
Banco de Dados
Redes
Segurança
Inteligência Artificial
```

Permitir que o participante escolha mais de um tema.

Criar também quatro `JCheckBox`:

```text
Desejo receber certificado
Desejo receber material
Desejo participar dos exercícios
Desejo receber novidades
```

---

# 48. Exercício 3

Na aba Informações, criar um `JEditorPane`.

O conteúdo deverá apresentar:

```text
Nome do evento
Horário
Local
Carga horária
Regras de participação
```

Utilizar HTML básico para organizar o conteúdo.

---

# 49. Exercício 4

Criar um botão chamado:

```text
Finalizar inscrição
```

Ao clicar nesse botão, nós devemos apresentar utilizando `JOptionPane`:

```text
Nome
Telefone
Cidade
Idade
Temas selecionados
Opções marcadas
```

---

# 50. Desafio

Agora vamos ampliar o exercício.

Criar uma quarta aba chamada:

```text
Resumo
```

Nessa aba, adicionar um `JTextArea`.

Quando o usuário clicar no botão:

```text
Gerar Resumo
```

os dados preenchidos deverão aparecer dentro do `JTextArea`.

Exemplo:

```text
RESUMO DA INSCRIÇÃO

Nome: Maria da Silva

Curso: Java

Turno: Noite

Interesses:
Programação
Desenvolvimento Web

Horas disponíveis:
8 horas

Observações:
Desejo aprender desenvolvimento de sistemas.
```

---

# 51. Desafio adicional

Criar um `JComboBox` chamado:

```java
cmbNivel
```

Adicionar:

```text
Selecione
Iniciante
Intermediário
Avançado
```

Quando o usuário selecionar `Iniciante`, apresentar:

```text
Ótimo. Vamos começar pelos fundamentos.
```

Quando selecionar `Intermediário`:

```text
Nós vamos aprofundar nossos conhecimentos.
```

Quando selecionar `Avançado`:

```text
Prepare se para desafios mais complexos.
```

Podemos utilizar o evento:

```text
ActionPerformed
```

do próprio `JComboBox`.

---

# 52. Exemplo de evento no JComboBox

```java
private void cmbNivelActionPerformed(
        java.awt.event.ActionEvent evt
) {

    String nivel =
            cmbNivel
            .getSelectedItem()
            .toString();

    if (nivel.equals("Iniciante")) {

        JOptionPane.showMessageDialog(
                this,
                "Ótimo. Vamos começar pelos fundamentos."
        );

    }

    if (nivel.equals("Intermediário")) {

        JOptionPane.showMessageDialog(
                this,
                "Nós vamos aprofundar nossos conhecimentos."
        );

    }

    if (nivel.equals("Avançado")) {

        JOptionPane.showMessageDialog(
                this,
                "Prepare se para desafios mais complexos."
        );

    }

}
```

---

# 53. Erros comuns

Durante a atividade nós podemos encontrar alguns erros.

## Nenhum item selecionado no JList

Se utilizarmos:

```java
lstInteresses.getSelectedValue()
```

sem verificar a seleção, podemos receber um valor `null`.

Por isso podemos testar:

```java
if (lstInteresses.isSelectionEmpty()) {

    JOptionPane.showMessageDialog(
            this,
            "Selecione uma opção."
    );

}
```

---

# 54. Outro erro comum

Esquecer de colocar os `JRadioButton` dentro de um `ButtonGroup`.

Nesse caso o usuário consegue marcar várias opções simultaneamente.

Quando nós queremos uma única escolha, precisamos utilizar:

```java
ButtonGroup
```

---

# 55. Outro erro comum

Utilizar `JTextField` para textos muito grandes.

Quando o usuário precisa escrever várias linhas, normalmente o componente mais adequado é:

```java
JTextArea
```

---

# 56. Outro erro comum

Permitir que o usuário altere um `JEditorPane` utilizado apenas para mostrar instruções.

Nesse caso devemos utilizar:

```java
edtInformacoes.setEditable(false);
```

---

# 57. Perguntas para revisão

1. Para que serve o `JComboBox`?

2. Qual é a principal diferença entre `JComboBox` e `JList`?

3. Qual componente utilizamos para escrever textos com várias linhas?

4. Qual componente podemos utilizar para apresentar HTML?

5. Para que serve o `JTabbedPane`?

6. Como descobrimos qual item foi selecionado em um `JComboBox`?

7. Como verificamos se um `JList` está sem seleção?

8. Como limpamos uma seleção de `ButtonGroup`?

9. Como podemos mudar automaticamente de aba?

10. Em qual situação devemos utilizar `JTextArea` em vez de `JTextField`?

---

# 58. Exercício individual

Agora cada aluno deverá desenvolver sozinho um sistema chamado:

```text
CadastroWorkshop
```

A aplicação deverá possuir quatro abas:

```text
Dados
Preferências
Informações
Resumo
```

## Aba Dados

Utilizar:

```text
JTextField
JFormattedTextField
JPasswordField
JComboBox
JRadioButton
ButtonGroup
JSpinner
```

## Aba Preferências

Utilizar:

```text
JList
JCheckBox
JTextArea
```

## Aba Informações

Utilizar:

```text
JEditorPane
```

## Aba Resumo

Utilizar:

```text
JTextArea
```

O sistema deverá possuir os botões:

```text
Cadastrar
Gerar Resumo
Limpar
Sair
```

---

# 59. Regras do exercício

O formulário deverá:

* Validar o nome
* Validar o ComboBox
* Validar o turno
* Validar pelo menos uma seleção no JList
* Apresentar os dados com `JOptionPane`
* Gerar um resumo dentro de um `JTextArea`
* Permitir limpar todo o formulário
* Voltar automaticamente para a primeira aba ao limpar

---

# 60. Encerramento

Nesta aula nós demos mais um passo importante na construção de interfaces gráficas com Java Swing.

Nós aprendemos a trabalhar com componentes que permitem organizar melhor a tela, oferecer opções ao usuário e apresentar informações de forma mais estruturada.

Conhecemos:

```text
JComboBox
JList
JTextArea
JEditorPane
JTabbedPane
```

Também reaproveitamos componentes estudados anteriormente.

Esse é um ponto importante do nosso aprendizado.

Nós não estamos estudando cada componente de forma isolada.

A partir de agora, vamos começar a combinar os componentes para construir sistemas cada vez mais completos.

Na próxima etapa, nós poderemos continuar evoluindo essas telas, adicionando novas regras, eventos, tabelas e outras funcionalidades antes de chegarmos à integração com banco de dados.
