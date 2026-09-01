# Aula 3: Menus em Java Swing com NetBeans

## JMenuBar, JMenu, JMenuItem, JCheckBoxMenuItem, JRadioButtonMenuItem, JSeparator e JPopupMenu

Nesta aula nós vamos continuar evoluindo nossos conhecimentos em Java Swing utilizando o NetBeans.

Nas aulas anteriores nós aprendemos a construir formulários utilizando componentes como:

* `JTextField`
* `JCheckBox`
* `JRadioButton`
* `ButtonGroup`
* `JPasswordField`
* `JFormattedTextField`
* `JSpinner`
* `JComboBox`
* `JList`
* `JTextArea`
* `JEditorPane`
* `JTabbedPane`

Agora nós vamos conhecer componentes muito importantes para organizar a navegação de uma aplicação Desktop.

Vamos trabalhar com menus.

Ainda não vamos utilizar banco de dados.

Nosso objetivo será compreender como criar menus, opções de menu, separadores, opções marcáveis, opções exclusivas e menus de contexto.

---

# 1. Objetivos da aula

Ao final desta aula, nós deveremos ser capazes de:

* Criar uma barra de menus com `JMenuBar`
* Criar menus com `JMenu`
* Criar opções com `JMenuItem`
* Criar opções marcáveis com `JCheckBoxMenuItem`
* Criar opções exclusivas com `JRadioButtonMenuItem`
* Agrupar opções de menu com `ButtonGroup`
* Organizar menus utilizando `JSeparator`
* Criar menus de contexto com `JPopupMenu`
* Programar eventos dos itens de menu
* Integrar menus com componentes estudados anteriormente
* Criar uma interface semelhante à encontrada em aplicações profissionais

---

# 2. Projeto da aula

Nesta aula nós vamos criar um projeto chamado:

```text
Aula03_MenusSwing
```

Dentro desse projeto nós vamos criar uma tela chamada:

```text
FrmPrincipal
```

Nosso objetivo será montar uma pequena aplicação de gerenciamento de cursos.

Ainda não vamos salvar informações.

Nós vamos utilizar os menus para:

* Abrir telas
* Limpar campos
* Mostrar mensagens
* Alterar opções da aplicação
* Selecionar preferências
* Encerrar o programa
* Exibir informações sobre o sistema

---

# 3. Criando o projeto no NetBeans

No NetBeans vamos criar um novo projeto Java.

Vamos utilizar o nome:

```text
Aula03_MenusSwing
```

Depois vamos criar um formulário:

```text
JFrame Form
```

Nome da classe:

```text
FrmPrincipal
```

---

# 4. O que é uma barra de menus

Uma barra de menus é a região localizada normalmente na parte superior de uma aplicação.

Nós encontramos esse recurso em diversos programas.

Exemplos:

```text
Arquivo
Editar
Cadastro
Consulta
Ferramentas
Ajuda
```

Cada menu pode possuir várias opções.

Em Java Swing, a barra de menus é representada pela classe:

```java
JMenuBar
```

---

# 5. Conhecendo o JMenuBar

O `JMenuBar` funciona como o contêiner principal dos menus.

Nós adicionamos dentro dele componentes do tipo:

```java
JMenu
```

Exemplo de estrutura:

```text
JMenuBar

Arquivo
Cadastro
Configurações
Ajuda
```

---

# 6. Adicionando uma Menu Bar no NetBeans

Na paleta do NetBeans vamos localizar:

```text
Menu Bar
```

Vamos adicionar esse componente ao formulário.

Podemos nomeá lo como:

```java
menuBarPrincipal
```

Depois vamos começar a inserir nossos menus.

---

# 7. Conhecendo o JMenu

O `JMenu` representa um menu principal.

Exemplos:

```text
Arquivo
Cadastro
Ferramentas
Ajuda
```

Dentro de cada `JMenu` nós podemos adicionar outras opções.

Exemplo:

```text
Arquivo
    Novo
    Limpar
    Sair
```

---

# 8. Criando nossos primeiros menus

Vamos criar quatro menus principais:

```text
Arquivo
Cadastro
Configurações
Ajuda
```

Podemos utilizar os seguintes nomes:

```java
menuArquivo

menuCadastro

menuConfiguracoes

menuAjuda
```

---

# 9. Conhecendo o JMenuItem

O `JMenuItem` representa uma opção dentro de um menu.

Exemplo:

```text
Arquivo
    Novo
    Salvar
    Sair
```

Cada uma dessas opções pode ser um:

```java
JMenuItem
```

---

# 10. Criando itens no menu Arquivo

Dentro do menu Arquivo vamos criar:

```text
Novo Cadastro
Limpar
Sair
```

Vamos utilizar os nomes:

```java
itemNovo

itemLimpar

itemSair
```

---

# 11. Programando o JMenuItem

Assim como fazemos com um botão, podemos utilizar o evento:

```text
ActionPerformed
```

Exemplo:

```java
private void itemNovoActionPerformed(
        java.awt.event.ActionEvent evt
) {

    JOptionPane.showMessageDialog(
            this,
            "Novo cadastro iniciado."
    );

}
```

---

# 12. Criando o item Sair

Podemos utilizar:

```java
private void itemSairActionPerformed(
        java.awt.event.ActionEvent evt
) {

    int resposta =
            JOptionPane.showConfirmDialog(
                    this,
                    "Deseja realmente encerrar o sistema?",
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

Não podemos esquecer do import:

```java
import javax.swing.JOptionPane;
```

---

# 13. Criando um formulário dentro da tela

Para tornar nossa aula mais prática, vamos colocar alguns componentes na tela principal.

Vamos utilizar:

```text
Nome
Curso
Turno
Observações
```

Componentes:

```text
JTextField
JComboBox
JRadioButton
ButtonGroup
JTextArea
```

Sugestão de nomes:

```java
txtNome

cmbCurso

rbManha

rbTarde

rbNoite

grpTurno

txtObservacoes
```

Assim nós podemos utilizar os itens de menu para controlar o formulário.

---

# 14. Programando o item Limpar

Vamos criar um item chamado:

```text
Limpar
```

Podemos programar:

```java
private void itemLimparActionPerformed(
        java.awt.event.ActionEvent evt
) {

    txtNome.setText("");

    cmbCurso.setSelectedIndex(0);

    grpTurno.clearSelection();

    txtObservacoes.setText("");

    txtNome.requestFocus();

}
```

Agora nós conseguimos limpar o formulário através do menu.

---

# 15. Conhecendo o JCheckBoxMenuItem

O `JCheckBoxMenuItem` é um item de menu que pode ficar marcado ou desmarcado.

Ele funciona de forma parecida com um `JCheckBox`.

Podemos utilizar quando a opção pode ser ativada ou desativada independentemente de outras opções.

Exemplos:

```text
Exibir dicas
Ativar sons
Mostrar barra de status
Receber notificações
Modo compacto
```

---

# 16. Criando um JCheckBoxMenuItem

Dentro do menu Configurações vamos criar:

```text
Exibir dicas
```

Nome sugerido:

```java
chkMenuDicas
```

Podemos verificar se está selecionado:

```java
if (chkMenuDicas.isSelected()) {

    JOptionPane.showMessageDialog(
            this,
            "As dicas estão ativadas."
    );

} else {

    JOptionPane.showMessageDialog(
            this,
            "As dicas estão desativadas."
    );

}
```

---

# 17. Utilizando o JCheckBoxMenuItem na prática

Imagine que nós temos um `JLabel` chamado:

```java
lblDica
```

Podemos fazer o item do menu controlar a visibilidade desse componente.

```java
private void chkMenuDicasActionPerformed(
        java.awt.event.ActionEvent evt
) {

    if (chkMenuDicas.isSelected()) {

        lblDica.setVisible(true);

    } else {

        lblDica.setVisible(false);

    }

}
```

Agora o próprio menu altera a interface.

---

# 18. Conhecendo o JRadioButtonMenuItem

O `JRadioButtonMenuItem` funciona de maneira semelhante ao `JRadioButton`.

Ele é utilizado quando temos várias opções, mas apenas uma deve permanecer selecionada.

Exemplos:

```text
Tema claro
Tema escuro

Fonte pequena
Fonte média
Fonte grande

Visualização simples
Visualização completa
```

---

# 19. Criando opções de tamanho da fonte

Dentro do menu Configurações vamos criar um submenu chamado:

```text
Tamanho da Fonte
```

Dentro dele podemos adicionar:

```text
Pequena
Média
Grande
```

Essas opções serão representadas por:

```java
JRadioButtonMenuItem
```

Nomes:

```java
radioFontePequena

radioFonteMedia

radioFonteGrande
```

---

# 20. Agrupando os RadioButtonMenuItem

Assim como ocorre com os `JRadioButton`, nós precisamos impedir que várias opções fiquem marcadas ao mesmo tempo.

Para isso vamos utilizar um:

```java
ButtonGroup
```

Nome sugerido:

```java
grupoFonte
```

Vamos adicionar os três componentes ao grupo.

---

# 21. Programando a fonte pequena

```java
private void radioFontePequenaActionPerformed(
        java.awt.event.ActionEvent evt
) {

    txtObservacoes.setFont(
            new java.awt.Font(
                    "Arial",
                    java.awt.Font.PLAIN,
                    12
            )
    );

}
```

---

# 22. Programando a fonte média

```java
private void radioFonteMediaActionPerformed(
        java.awt.event.ActionEvent evt
) {

    txtObservacoes.setFont(
            new java.awt.Font(
                    "Arial",
                    java.awt.Font.PLAIN,
                    16
            )
    );

}
```

---

# 23. Programando a fonte grande

```java
private void radioFonteGrandeActionPerformed(
        java.awt.event.ActionEvent evt
) {

    txtObservacoes.setFont(
            new java.awt.Font(
                    "Arial",
                    java.awt.Font.PLAIN,
                    20
            )
    );

}
```

Agora nós conseguimos modificar uma propriedade da interface através de itens do menu.

---

# 24. Conhecendo o JSeparator

O `JSeparator` é utilizado para separar visualmente grupos de opções.

Ele ajuda a organizar os menus.

Exemplo:

```text
Arquivo

Novo Cadastro
Limpar

────────────

Sair
```

No NetBeans podemos utilizar:

```text
Separator
```

---

# 25. Onde utilizar o Separator

Um exemplo interessante é organizar o menu Arquivo desta forma:

```text
Novo Cadastro
Limpar

Separador

Sair
```

Assim nós deixamos o comando de saída separado das demais ações.

Também podemos organizar:

```text
Configurações

Exibir dicas

Separador

Tamanho da Fonte
```

---

# 26. Criando um menu Cadastro

Agora vamos criar um menu:

```text
Cadastro
```

Dentro dele podemos adicionar:

```text
Aluno
Professor
Curso
```

Mesmo sem banco de dados, cada opção pode abrir uma mensagem ou uma nova tela.

---

# 27. Criando uma nova tela

Podemos criar um novo formulário chamado:

```text
FrmAluno
```

Esse formulário poderá utilizar componentes estudados anteriormente.

Por exemplo:

```text
Nome
Telefone
Senha
Curso
Turno
Interesses
Observações
```

---

# 28. Abrindo outra tela pelo menu

No item:

```text
Aluno
```

podemos utilizar:

```java
private void itemAlunoActionPerformed(
        java.awt.event.ActionEvent evt
) {

    FrmAluno tela =
            new FrmAluno();

    tela.setVisible(true);

}
```

Assim nós começamos a criar uma aplicação com várias telas.

---

# 29. Centralizando uma nova tela

Podemos melhorar o código:

```java
private void itemAlunoActionPerformed(
        java.awt.event.ActionEvent evt
) {

    FrmAluno tela =
            new FrmAluno();

    tela.setLocationRelativeTo(null);

    tela.setVisible(true);

}
```

Agora a nova janela será centralizada.

---

# 30. Conhecendo o JPopupMenu

O `JPopupMenu` é conhecido como menu de contexto.

Ele normalmente aparece quando clicamos com o botão direito do mouse sobre algum componente.

Podemos utilizá lo em:

```text
Campos de texto
Tabelas
Listas
Áreas de texto
Painéis
Imagens
```

Exemplos de opções:

```text
Limpar
Copiar
Colar
Excluir
Detalhes
```

---

# 31. Criando um Popup Menu

Na paleta do NetBeans vamos localizar:

```text
Popup Menu
```

No Java Swing, o componente é:

```java
JPopupMenu
```

Vamos nomeá lo:

```java
popupObservacoes
```

Dentro dele vamos criar três itens:

```text
Limpar
Copiar
Selecionar Tudo
```

Nomes sugeridos:

```java
popupLimpar

popupCopiar

popupSelecionarTudo
```

---

# 32. Associando o Popup Menu ao JTextArea

Vamos associar o `JPopupMenu` ao nosso:

```java
txtObservacoes
```

Uma forma simples é utilizar:

```java
txtObservacoes.setComponentPopupMenu(
        popupObservacoes
);
```

Podemos colocar esse código no construtor do formulário depois de:

```java
initComponents();
```

Exemplo:

```java
public FrmPrincipal() {

    initComponents();

    txtObservacoes.setComponentPopupMenu(
            popupObservacoes
    );

}
```

---

# 33. Programando a opção Limpar do Popup Menu

```java
private void popupLimparActionPerformed(
        java.awt.event.ActionEvent evt
) {

    txtObservacoes.setText("");

}
```

---

# 34. Programando a opção Copiar

```java
private void popupCopiarActionPerformed(
        java.awt.event.ActionEvent evt
) {

    txtObservacoes.copy();

}
```

---

# 35. Programando Selecionar Tudo

```java
private void popupSelecionarTudoActionPerformed(
        java.awt.event.ActionEvent evt
) {

    txtObservacoes.selectAll();

}
```

Agora nós temos um menu de contexto funcionando dentro da aplicação.

---

# 36. Criando um menu Ajuda

Vamos criar o menu:

```text
Ajuda
```

Dentro dele podemos adicionar:

```text
Como usar
Sobre
```

---

# 37. Criando o item Como usar

```java
private void itemComoUsarActionPerformed(
        java.awt.event.ActionEvent evt
) {

    JOptionPane.showMessageDialog(
            this,
            "Preencha os dados do formulário e utilize os menus para executar as ações disponíveis."
    );

}
```

---

# 38. Criando o item Sobre

```java
private void itemSobreActionPerformed(
        java.awt.event.ActionEvent evt
) {

    JOptionPane.showMessageDialog(
            this,
            "Sistema de Exemplo\n"
            + "Curso de Java Swing\n"
            + "Desenvolvido em aula"
    );

}
```

---

# 39. Estrutura completa sugerida da Menu Bar

Nossa barra de menus poderá ficar assim:

```text
Arquivo
    Novo Cadastro
    Limpar
    Separator
    Sair

Cadastro
    Aluno
    Professor
    Curso

Configurações
    Exibir Dicas
    Separator
    Tamanho da Fonte
        Pequena
        Média
        Grande

Ajuda
    Como usar
    Sobre
```

---

# 40. Misturando componentes das aulas anteriores

Agora nós vamos aproveitar vários componentes já estudados.

Na tela principal podemos utilizar:

```text
JTextField
JFormattedTextField
JComboBox
JRadioButton
ButtonGroup
JCheckBox
JSpinner
JList
JTextArea
JTabbedPane
JMenuBar
JMenu
JMenuItem
JCheckBoxMenuItem
JRadioButtonMenuItem
JSeparator
JPopupMenu
```

Nosso objetivo é perceber que os componentes não precisam ser estudados separadamente.

Nós podemos combiná los para construir interfaces mais completas.

---

# 41. Projeto prático da aula

Agora nós vamos construir um pequeno sistema chamado:

```text
SistemaAcademicoSwing
```

A tela principal deverá possuir uma barra de menus e um formulário com abas.

---

# 42. Estrutura da tela principal

Vamos criar um:

```java
JTabbedPane
```

com três abas:

```text
Cadastro
Preferências
Informações
```

---

# 43. Aba Cadastro

Adicionar:

```text
Nome
Telefone
Curso
Turno
Idade
```

Componentes:

```text
JTextField
JFormattedTextField
JComboBox
JRadioButton
ButtonGroup
JSpinner
```

---

# 44. Aba Preferências

Adicionar:

```text
Interesses
Receber certificado
Receber material
Observações
```

Componentes:

```text
JList
JCheckBox
JTextArea
```

---

# 45. Aba Informações

Adicionar:

```text
JEditorPane
```

com informações sobre o curso.

---

# 46. Menu Arquivo

Criar:

```text
Novo
Limpar
Separator
Sair
```

---

# 47. Menu Cadastro

Criar:

```text
Aluno
Curso
Professor
```

Por enquanto, podemos utilizar `JOptionPane` para indicar qual cadastro foi selecionado.

Exemplo:

```java
private void itemCursoActionPerformed(
        java.awt.event.ActionEvent evt
) {

    JOptionPane.showMessageDialog(
            this,
            "Cadastro de Curso selecionado."
    );

}
```

---

# 48. Menu Configurações

Criar:

```text
Exibir Dicas

Separator

Tamanho da Fonte
    Pequena
    Média
    Grande
```

---

# 49. Menu Ajuda

Criar:

```text
Como usar
Sobre
```

---

# 50. Popup Menu

Criar um `JPopupMenu` para o campo de observações.

Adicionar:

```text
Limpar
Copiar
Selecionar Tudo
```

---

# 51. Criando uma função para limpar o formulário

Nós podemos evitar repetir código criando um método:

```java
private void limparCampos() {

    txtNome.setText("");

    fmtTelefone.setText("");

    cmbCurso.setSelectedIndex(0);

    grpTurno.clearSelection();

    spnIdade.setValue(18);

    lstInteresses.clearSelection();

    chkCertificado.setSelected(false);

    chkMaterial.setSelected(false);

    txtObservacoes.setText("");

    txtNome.requestFocus();

}
```

Agora podemos chamar esse método tanto em um botão quanto em um item de menu.

---

# 52. Utilizando o método no item Limpar

```java
private void itemLimparActionPerformed(
        java.awt.event.ActionEvent evt
) {

    limparCampos();

}
```

---

# 53. Utilizando o mesmo método em um botão

```java
private void btnLimparActionPerformed(
        java.awt.event.ActionEvent evt
) {

    limparCampos();

}
```

Esse é um conceito importante.

Nós podemos reutilizar o mesmo método em diferentes partes da interface.

---

# 54. Criando uma função para apresentar os dados

Também podemos criar um método chamado:

```java
private void mostrarResumo() {

    String nome =
            txtNome.getText();

    String curso =
            cmbCurso
            .getSelectedItem()
            .toString();

    JOptionPane.showMessageDialog(
            this,
            "Nome: " + nome
            + "\nCurso: " + curso
    );

}
```

Assim podemos utilizar esse método em botões e menus.

---

# 55. Exercício guiado

Vamos criar um sistema chamado:

```text
CentralCursos
```

A aplicação deverá possuir:

```text
Menu Bar
Tabbed Pane
Formulário de cadastro
Área de observações
Área de informações
Popup Menu
```

---

# 56. Requisitos do exercício guiado

A aplicação deverá possuir os menus:

```text
Arquivo
Cadastro
Configurações
Ajuda
```

O menu Arquivo deverá possuir:

```text
Novo
Limpar
Separator
Sair
```

---

# 57. Requisitos do menu Cadastro

Criar:

```text
Aluno
Professor
Curso
```

Cada opção deverá apresentar uma mensagem diferente com `JOptionPane`.

---

# 58. Requisitos do menu Configurações

Criar um `JCheckBoxMenuItem` chamado:

```text
Exibir Dicas
```

Criar três `JRadioButtonMenuItem`:

```text
Fonte Pequena
Fonte Média
Fonte Grande
```

Eles deverão ficar agrupados em um `ButtonGroup`.

---

# 59. Requisitos do menu Ajuda

Criar:

```text
Como usar
Sobre
```

O item Sobre deverá apresentar:

```text
Nome do sistema
Versão
Curso
Turma
```

---

# 60. Requisitos do Popup Menu

No `JTextArea` de observações, criar um menu de contexto com:

```text
Limpar
Copiar
Selecionar Tudo
```

---

# 61. Desafio 1

Criar um item no menu:

```text
Arquivo
    Gerar Resumo
```

Ao selecionar essa opção, nós devemos apresentar todos os dados preenchidos no formulário utilizando `JOptionPane`.

---

# 62. Desafio 2

Criar um `JCheckBoxMenuItem` chamado:

```text
Bloquear Edição
```

Quando ele estiver marcado, o campo de observações deverá ficar bloqueado.

Podemos utilizar:

```java
txtObservacoes.setEditable(
        !chkMenuBloquear.isSelected()
);
```

---

# 63. Desafio 3

Criar um submenu:

```text
Configurações
    Aba Inicial
```

Dentro dele criar:

```text
Cadastro
Preferências
Informações
```

Utilizar `JRadioButtonMenuItem`.

Quando o usuário selecionar uma opção, o `JTabbedPane` deverá mudar para a aba correspondente.

---

# 64. Exemplo do desafio de abas

Para a aba Cadastro:

```java
private void radioAbaCadastroActionPerformed(
        java.awt.event.ActionEvent evt
) {

    tabPrincipal.setSelectedIndex(0);

}
```

Para Preferências:

```java
tabPrincipal.setSelectedIndex(1);
```

Para Informações:

```java
tabPrincipal.setSelectedIndex(2);
```

---

# 65. Desafio 4

Criar um `JPopupMenu` também para o campo de nome.

Adicionar:

```text
Limpar
Copiar
Colar
Selecionar Tudo
```

Podemos utilizar:

```java
txtNome.copy();

txtNome.paste();

txtNome.selectAll();
```

---

# 66. Exercício individual

Agora cada aluno deverá desenvolver uma aplicação chamada:

```text
SistemaEventosSwing
```

A aplicação deverá utilizar os componentes estudados nesta aula e nas aulas anteriores.

---

# 67. Estrutura obrigatória

A aplicação deverá possuir:

```text
JMenuBar
JMenu
JMenuItem
JCheckBoxMenuItem
JRadioButtonMenuItem
JSeparator
JPopupMenu
JTabbedPane
JComboBox
JList
JTextArea
JCheckBox
JRadioButton
ButtonGroup
JSpinner
```

---

# 68. Barra de menus do exercício individual

Criar:

```text
Arquivo
Participante
Preferências
Ajuda
```

---

# 69. Menu Arquivo

Adicionar:

```text
Novo
Limpar
Separator
Sair
```

---

# 70. Menu Participante

Adicionar:

```text
Cadastrar
Gerar Resumo
```

O item Gerar Resumo deverá apresentar os dados preenchidos.

---

# 71. Menu Preferências

Adicionar:

```text
Exibir Dicas

Separator

Tamanho da Fonte
    Pequena
    Média
    Grande
```

---

# 72. Menu Ajuda

Adicionar:

```text
Instruções
Sobre
```

---

# 73. Popup Menu obrigatório

Criar um `JPopupMenu` no campo de observações com:

```text
Limpar
Copiar
Selecionar Tudo
```

---

# 74. Critérios do exercício

A aplicação deverá:

* Abrir corretamente
* Possuir menus organizados
* Utilizar pelo menos um `JSeparator`
* Utilizar pelo menos um `JCheckBoxMenuItem`
* Utilizar pelo menos três `JRadioButtonMenuItem`
* Utilizar `ButtonGroup`
* Possuir pelo menos um `JPopupMenu`
* Limpar o formulário através do menu
* Encerrar o sistema com confirmação
* Apresentar mensagens com `JOptionPane`
* Reutilizar componentes estudados nas aulas anteriores

---

# 75. Erros comuns

## Esquecer de agrupar os JRadioButtonMenuItem

Se nós não utilizarmos um `ButtonGroup`, várias opções poderão ficar selecionadas ao mesmo tempo.

Quando desejamos apenas uma escolha, precisamos agrupá las.

---

# 76. Outro erro comum

Criar muitos itens de menu sem organização.

Quando o menu possui vários comandos, podemos utilizar:

```java
JSeparator
```

Isso facilita a leitura e separa ações diferentes.

---

# 77. Outro erro comum

Utilizar `JCheckBoxMenuItem` quando apenas uma opção deve ser escolhida.

O `JCheckBoxMenuItem` serve para opções independentes.

Quando apenas uma opção deve permanecer selecionada, devemos utilizar:

```java
JRadioButtonMenuItem
```

junto com:

```java
ButtonGroup
```

---

# 78. Outro erro comum

Criar o `JPopupMenu`, mas esquecer de associá lo ao componente.

Podemos utilizar:

```java
txtObservacoes.setComponentPopupMenu(
        popupObservacoes
);
```

---

# 79. Comparando os novos componentes

| Componente | Utilização |
| --- | --- |
| `JMenuBar` | Barra principal que contém os menus |
| `JMenu` | Cria um menu ou submenu |
| `JMenuItem` | Cria uma opção comum de menu |
| `JCheckBoxMenuItem` | Cria uma opção que pode ficar marcada ou desmarcada |
| `JRadioButtonMenuItem` | Cria opções exclusivas dentro de um grupo |
| `ButtonGroup` | Controla opções exclusivas |
| `JSeparator` | Separa visualmente grupos de itens |
| `JPopupMenu` | Cria um menu de contexto |

---

# 80. Perguntas para revisão

1. Para que serve o `JMenuBar`?

2. Qual é a função do `JMenu`?

3. Qual é a diferença entre `JMenu` e `JMenuItem`?

4. Quando devemos utilizar `JCheckBoxMenuItem`?

5. Quando devemos utilizar `JRadioButtonMenuItem`?

6. Por que utilizamos `ButtonGroup` com `JRadioButtonMenuItem`?

7. Para que serve o `JSeparator`?

8. O que é um `JPopupMenu`?

9. Como associamos um `JPopupMenu` a um componente?

10. Podemos executar o mesmo método através de um botão e de um menu?

11. Qual método podemos utilizar para limpar uma seleção de `ButtonGroup`?

12. Como podemos encerrar uma aplicação com confirmação?

---

# 81. Resumo da aula

Nesta aula nós aprendemos a criar menus em aplicações Java Swing.

Conhecemos:

```text
JMenuBar
JMenu
JMenuItem
JCheckBoxMenuItem
JRadioButtonMenuItem
JSeparator
JPopupMenu
```

Também utilizamos novamente:

```text
ButtonGroup
JOptionPane
JTabbedPane
JComboBox
JList
JTextArea
JCheckBox
JRadioButton
JSpinner
```

---

# 82. Encerramento

Nesta etapa nós começamos a transformar nossos formulários em aplicações com uma estrutura de navegação mais completa.

Os menus são importantes porque permitem organizar comandos sem ocupar toda a área principal da tela.

Nós também percebemos que um mesmo comando pode ser executado através de diferentes componentes.

Por exemplo, podemos limpar um formulário utilizando:

```text
Botão Limpar
Item de menu Limpar
Popup Menu
```

Todos eles podem chamar o mesmo método.

Esse tipo de organização será cada vez mais importante conforme nossos projetos crescerem.

Ainda não utilizamos banco de dados.

Por enquanto, nosso foco continua sendo dominar a interface gráfica, os eventos, a organização do código e a integração entre os componentes.

Com essa base, nós estaremos preparados para construir aplicações Java Swing cada vez mais completas.
