# Aula 5: Desktop Pane e Internal Frame no Java Swing

## Criando uma aplicação com várias janelas internas no NetBeans

Nesta aula nós vamos continuar evoluindo nossas aplicações Java Swing utilizando o NetBeans.

Até aqui nós já trabalhamos com formulários, abas, tabelas, menus, campos de texto, listas, caixas de seleção e vários outros componentes.

Agora nós vamos conhecer dois componentes fundamentais para a construção de sistemas Desktop com várias telas:

```java
JDesktopPane
```

e:

```java
JInternalFrame
```

Ainda não vamos utilizar banco de dados.

Nosso objetivo será compreender como criar uma janela principal e abrir outras janelas dentro dela, sem fechar a tela principal.

## 1. Objetivos da aula

Ao final desta aula, nós deveremos ser capazes de:

* Entender o que é um `JDesktopPane`
* Entender o que é um `JInternalFrame`
* Criar uma janela principal com `JFrame`
* Adicionar um `JDesktopPane`
* Criar janelas internas
* Abrir uma janela interna através de botão
* Abrir uma janela interna através de menu
* Fechar uma janela interna sem encerrar a aplicação
* Centralizar uma janela interna
* Maximizar uma janela interna
* Evitar abrir várias cópias da mesma janela
* Fechar todas as janelas internas
* Misturar componentes estudados anteriormente

## 2. Projeto da aula

Vamos criar um projeto chamado:

```text
Aula05_DesktopPane_InternalFrame
```

Nossa aplicação terá:

```text
FrmPrincipal
FrmProduto
FrmConsulta
FrmSobre
```

A `FrmPrincipal` será nossa janela principal.

As demais telas serão abertas dentro dela.

## 3. Estrutura da aplicação

Nossa organização será:

```text
FrmPrincipal
    JDesktopPane
        FrmProduto
        FrmConsulta
        FrmSobre
```

A `FrmPrincipal` será criada como:

```text
JFrame Form
```

As outras telas serão criadas como:

```text
JInternalFrame Form
```

## 4. O que é o JDesktopPane

O `JDesktopPane` funciona como uma área de trabalho dentro da janela principal.

Nós podemos imaginar que ele é uma mesa.

Dentro dessa mesa nós podemos abrir várias janelas internas.

Esse tipo de estrutura é encontrado em sistemas:

* Comerciais
* Escolares
* Hospitalares
* Administrativos
* Financeiros
* De estoque
* De atendimento

## 5. Criando a FrmPrincipal

Vamos criar:

```text
FrmPrincipal
```

como um:

```text
JFrame Form
```

Dentro dela vamos adicionar o componente:

```text
Desktop Pane
```

Vamos nomeá lo como:

```java
desktopPrincipal
```

## 6. Abrindo a tela principal maximizada

Podemos fazer a `FrmPrincipal` abrir maximizada.

No construtor:

```java
public FrmPrincipal() {

    initComponents();

    setExtendedState(
            javax.swing.JFrame.MAXIMIZED_BOTH
    );

}
```

Assim nossa tela principal utilizará praticamente todo o espaço disponível.

## 7. O que é o JInternalFrame

O `JInternalFrame` é uma janela que funciona dentro de um `JDesktopPane`.

Ele pode possuir:

* Título
* Botão de fechar
* Botão de minimizar
* Botão de maximizar
* Campos
* Botões
* Abas
* Tabelas
* Listas
* Outros componentes Swing

## 8. Criando o FrmProduto

Vamos criar:

```text
FrmProduto
```

No NetBeans devemos escolher:

```text
JInternalFrame Form
```

Essa diferença é muito importante.

Se a tela será aberta dentro do `JDesktopPane`, nós não vamos utilizar `JFrame Form`.

## 9. Propriedades importantes do Internal Frame

No `JInternalFrame`, vamos observar propriedades como:

### Closable

Permite fechar a janela interna.

### Iconifiable

Permite minimizar a janela interna.

### Maximizable

Permite maximizar a janela interna.

### Resizable

Permite redimensionar a janela.

### Title

Define o título apresentado na parte superior.

Para nosso `FrmProduto`, podemos utilizar:

```text
Cadastro de Produtos
```

## 10. Configuração sugerida

Podemos deixar:

```text
Closable: true
Iconifiable: true
Maximizable: true
Resizable: true
```

Assim o usuário poderá controlar a janela interna.

## 11. Abrindo um Internal Frame

Para abrir o `FrmProduto`, nós seguimos três passos.

Primeiro criamos a tela:

```java
FrmProduto tela =
        new FrmProduto();
```

Depois adicionamos ao Desktop Pane:

```java
desktopPrincipal.add(tela);
```

Depois mostramos:

```java
tela.setVisible(true);
```

## 12. Código completo para abrir a janela

```java
FrmProduto tela =
        new FrmProduto();

desktopPrincipal.add(tela);

tela.setVisible(true);
```

A sequência é:

```text
Criar
Adicionar
Mostrar
```

## 13. Abrindo através de um botão

Na `FrmPrincipal`, podemos criar um botão:

```text
Produtos
```

No evento:

```java
private void btnProdutosActionPerformed(
        java.awt.event.ActionEvent evt
) {

    FrmProduto tela =
            new FrmProduto();

    desktopPrincipal.add(tela);

    tela.setVisible(true);

}
```

## 14. Abrindo através de um menu

Também podemos utilizar um `JMenuItem`.

Exemplo:

```text
Cadastro
    Produtos
```

No evento:

```java
private void itemProdutosActionPerformed(
        java.awt.event.ActionEvent evt
) {

    FrmProduto tela =
            new FrmProduto();

    desktopPrincipal.add(tela);

    tela.setVisible(true);

}
```

## 15. JFrame e JInternalFrame

Nós precisamos entender a diferença.

### JFrame

Representa uma janela independente.

### JInternalFrame

Representa uma janela que funciona dentro de um `JDesktopPane`.

Em nosso projeto teremos normalmente um `JFrame` principal e vários `JInternalFrame`.

## 16. Fechando somente a janela interna

Dentro do `FrmProduto`, podemos criar um botão:

```text
Fechar
```

No evento:

```java
private void btnFecharActionPerformed(
        java.awt.event.ActionEvent evt
) {

    this.dispose();

}
```

O comando:

```java
this.dispose();
```

fecha somente a janela interna atual.

A `FrmPrincipal` continua aberta.

## 17. Cuidado com System.exit

Dentro de um `JInternalFrame`, normalmente nós não devemos utilizar:

```java
System.exit(0);
```

Esse comando encerra toda a aplicação.

Para fechar somente a janela interna, usamos:

```java
this.dispose();
```

## 18. Criando componentes no FrmProduto

Dentro do `FrmProduto`, podemos reaproveitar conteúdos das aulas anteriores.

Vamos criar:

```text
Código
Descrição
Quantidade
Fornecedor
Tipo
Situação
Observações
```

Podemos utilizar:

```text
JTextField
JSpinner
JComboBox
JRadioButton
ButtonGroup
JCheckBox
JTextArea
JButton
```

## 19. Utilizando JTabbedPane dentro do Internal Frame

Podemos colocar um `JTabbedPane` dentro do `FrmProduto`.

Criar quatro abas:

```text
Cadastro
Classificação
Observações
Consulta
```

Isso mostra que nós podemos combinar vários componentes dentro da mesma estrutura.

## 20. Aba Cadastro

Adicionar:

```text
Código
Descrição
Quantidade
Fornecedor
Valor
```

Utilizar:

```text
JTextField
JSpinner
JComboBox
JFormattedTextField
```

## 21. Aba Classificação

Adicionar:

```text
Tipo
Situação
Características
```

Utilizar:

```text
JRadioButton
ButtonGroup
JCheckBox
```

## 22. Aba Observações

Adicionar:

```text
JTextArea
JEditorPane
```

## 23. Aba Consulta

Adicionar:

```text
JTable
JTextField
JComboBox
JButton
```

Ainda sem banco de dados.

Os dados existirão somente enquanto a aplicação estiver aberta.

## 24. Centralizando uma janela interna

Nós podemos centralizar o Internal Frame dentro do Desktop Pane.

Exemplo:

```java
int x =
        (
            desktopPrincipal.getWidth()
            - tela.getWidth()
        ) / 2;

int y =
        (
            desktopPrincipal.getHeight()
            - tela.getHeight()
        ) / 2;

tela.setLocation(x, y);
```

## 25. Criando um método para centralizar

Podemos organizar melhor criando:

```java
private void centralizar(
        javax.swing.JInternalFrame tela
) {

    int x =
            (
                desktopPrincipal.getWidth()
                - tela.getWidth()
            ) / 2;

    int y =
            (
                desktopPrincipal.getHeight()
                - tela.getHeight()
            ) / 2;

    tela.setLocation(x, y);

}
```

Depois podemos utilizar:

```java
FrmProduto tela =
        new FrmProduto();

desktopPrincipal.add(tela);

tela.setVisible(true);

centralizar(tela);
```

## 26. Abrindo um Internal Frame maximizado

Também podemos abrir uma janela interna maximizada.

```java
try {

    tela.setMaximum(true);

} catch (
        java.beans.PropertyVetoException e
) {

    JOptionPane.showMessageDialog(
            this,
            "Não foi possível maximizar a janela."
    );

}
```

Esse recurso é interessante para telas como:

```text
Consultas
Tabelas grandes
Relatórios
Cadastros com muitas abas
```

## 27. Problema de abrir várias janelas iguais

Se nós criarmos uma nova instância sempre que o usuário clicar no botão, podemos acabar com várias telas iguais abertas.

Exemplo:

```text
Cadastro de Produtos
Cadastro de Produtos
Cadastro de Produtos
```

Em muitos sistemas isso não é desejável.

## 28. Verificando as janelas abertas

Podemos verificar todas as janelas existentes através de:

```java
desktopPrincipal.getAllFrames()
```

Esse método retorna os `JInternalFrame` que estão abertos.

## 29. Evitando duplicidade

Podemos verificar se o `FrmProduto` já está aberto.

```java
for (
        javax.swing.JInternalFrame frame
        : desktopPrincipal.getAllFrames()
) {

    if (
        frame instanceof FrmProduto
    ) {

        frame.toFront();

        try {

            frame.setSelected(true);

        } catch (
                java.beans.PropertyVetoException e
        ) {

        }

        return;

    }

}
```

Depois desse bloco, criamos a tela somente se ela ainda não estiver aberta.

```java
FrmProduto tela =
        new FrmProduto();

desktopPrincipal.add(tela);

tela.setVisible(true);

centralizar(tela);
```

## 30. O que significa instanceof

Quando utilizamos:

```java
frame instanceof FrmProduto
```

estamos verificando se aquela janela aberta é do tipo `FrmProduto`.

Se for, não precisamos criar outra.

## 31. Trazendo a janela para frente

Podemos utilizar:

```java
frame.toFront();
```

E também:

```java
frame.setSelected(true);
```

Assim nós trazemos a janela existente para a frente.

## 32. Criando um método abrirProduto

Podemos organizar:

```java
private void abrirProduto() {

    for (
            javax.swing.JInternalFrame frame
            : desktopPrincipal.getAllFrames()
    ) {

        if (
                frame instanceof FrmProduto
        ) {

            frame.toFront();

            try {

                frame.setSelected(true);

            } catch (
                    java.beans.PropertyVetoException e
            ) {

            }

            return;

        }

    }

    FrmProduto tela =
            new FrmProduto();

    desktopPrincipal.add(tela);

    tela.setVisible(true);

    centralizar(tela);

}
```

Agora podemos utilizar o mesmo método em botões ou menus.

## 33. Criando o FrmConsulta

Vamos criar:

```text
FrmConsulta
```

como:

```text
JInternalFrame Form
```

Dentro dele podemos adicionar:

```text
Pesquisar por
Campo de pesquisa
JTable
```

Botões:

```text
Pesquisar
Limpar Pesquisa
Fechar
```

## 34. Criando o FrmSobre

Vamos criar:

```text
FrmSobre
```

como `JInternalFrame`.

Podemos apresentar:

```text
Nome do sistema
Versão
Curso
Tecnologia utilizada
Informações do projeto
```

Criar um botão:

```text
Fechar
```

## 35. Abrindo várias telas diferentes

Nós podemos deixar abertas ao mesmo tempo:

```text
FrmProduto
FrmConsulta
FrmSobre
```

Todas ficarão dentro de:

```java
desktopPrincipal
```

## 36. Fechando todas as janelas internas

Podemos criar um botão:

```text
Fechar Todas
```

Utilizar:

```java
for (
        javax.swing.JInternalFrame frame
        : desktopPrincipal.getAllFrames()
) {

    frame.dispose();

}
```

Isso fecha todos os Internal Frames.

A janela principal continua aberta.

## 37. Criando um método fecharTodas

Podemos organizar:

```java
private void fecharTodas() {

    for (
            javax.swing.JInternalFrame frame
            : desktopPrincipal.getAllFrames()
    ) {

        frame.dispose();

    }

}
```

Depois basta chamar:

```java
fecharTodas();
```

## 38. Quantidade de janelas abertas

Podemos descobrir quantas janelas estão abertas utilizando:

```java
desktopPrincipal.getAllFrames().length
```

Podemos apresentar:

```java
JOptionPane.showMessageDialog(
        this,
        "Janelas abertas: "
        + desktopPrincipal.getAllFrames().length
);
```

## 39. Saindo do sistema

Na `FrmPrincipal`, podemos criar um botão:

```text
Sair
```

Como agora queremos encerrar toda a aplicação, podemos pedir confirmação.

```java
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
```

## 40. Regra importante

Dentro de um Internal Frame:

```java
this.dispose();
```

Na janela principal, quando queremos encerrar toda a aplicação:

```java
System.exit(0);
```

Nós devemos saber diferenciar essas duas situações.

# Projeto prático da aula

## 41. SistemaEstoqueSwing

Agora nós vamos construir uma aplicação chamada:

```text
SistemaEstoqueSwing
```

Ela terá:

```text
FrmPrincipal
FrmProduto
FrmConsulta
FrmSobre
```

Ainda sem banco de dados.

## 42. FrmPrincipal

Deverá possuir:

```text
JDesktopPane
JButton
JMenuBar
```

A janela deverá abrir maximizada.

Criar botões:

```text
Produtos
Consulta
Sobre
Fechar Todas
Quantidade de Janelas
Sair
```

## 43. FrmProduto

Criar como:

```text
JInternalFrame
```

Utilizar pelo menos quatro abas:

```text
Cadastro
Classificação
Observações
Consulta
```

## 44. Componentes obrigatórios no FrmProduto

Utilizar:

```text
JTextField
JFormattedTextField
JComboBox
JSpinner
JRadioButton
ButtonGroup
JCheckBox
JList
JTextArea
JEditorPane
JTabbedPane
JTable
JButton
```

## 45. Funcionalidades do FrmProduto

Nossa tela deverá permitir:

* Preencher os dados do produto
* Navegar entre as abas
* Mostrar os dados em `JOptionPane`
* Inserir os dados diretamente no `JTable`
* Pesquisar registros
* Excluir registros da tabela
* Limpar os campos
* Fechar somente o Internal Frame

Não vamos utilizar banco de dados.

Não vamos criar uma classe Produto.

## 46. FrmConsulta

Criar como `JInternalFrame`.

Adicionar:

```text
JTextField
JComboBox
JTable
JButton
```

Criar:

```text
Pesquisar
Limpar
Fechar
```

## 47. FrmSobre

Criar como `JInternalFrame`.

Adicionar informações sobre a aplicação.

Criar botão:

```text
Fechar
```

# Exercícios

## 48. Exercício 1

Crie um projeto chamado:

```text
SistemaAcademicoDesktop
```

Criar:

```text
FrmPrincipal
FrmAluno
FrmCurso
FrmSobre
```

## 49. FrmPrincipal do exercício

Deverá possuir:

```text
JDesktopPane
```

e os botões:

```text
Aluno
Curso
Sobre
Fechar Todas
Sair
```

## 50. FrmAluno

Criar como `JInternalFrame`.

Adicionar:

```text
Nome
Telefone
Curso
Turno
Observações
```

Criar:

```text
Mostrar Dados
Limpar
Fechar
```

## 51. FrmCurso

Criar como `JInternalFrame`.

Adicionar:

```text
Nome do curso
Carga horária
Turno
Quantidade de vagas
Descrição
```

Criar:

```text
Mostrar Dados
Limpar
Fechar
```

## 52. Desafio 1

Impedir que duas telas `FrmAluno` sejam abertas ao mesmo tempo.

Se a tela já estiver aberta, nós devemos trazê la para frente.

## 53. Desafio 2

Aplicar o mesmo controle para:

```text
FrmCurso
FrmSobre
```

## 54. Desafio 3

Abrir a tela de consulta maximizada dentro do Desktop Pane.

## 55. Desafio 4

Criar um botão:

```text
Quantidade de Janelas
```

Apresentar quantas janelas internas estão abertas.

## 56. Desafio 5

Criar um botão:

```text
Fechar Todas
```

Fechar todos os Internal Frames sem fechar a janela principal.

# Exercício individual

## 57. SistemaDesktopSwing

Cada aluno deverá criar um projeto chamado:

```text
SistemaDesktopSwing
```

O tema poderá ser:

```text
Loja
Biblioteca
Escola
Clínica
Oficina
Academia
Restaurante
Pet Shop
```

## 58. Requisitos obrigatórios

A aplicação deverá possuir:

```text
1 JFrame principal
1 JDesktopPane
No mínimo 3 JInternalFrame
```

Também deverá:

* Abrir janelas internas por botões
* Fechar janelas internas
* Manter a janela principal aberta
* Evitar pelo menos uma janela duplicada
* Fechar todas as janelas internas
* Abrir pelo menos uma janela centralizada
* Abrir pelo menos uma janela maximizada
* Utilizar componentes vistos anteriormente
* Mostrar dados com `JOptionPane`
* Utilizar pelo menos um `JTable`
* Utilizar pelo menos um `JTabbedPane`

## 59. Regras do exercício

Nesta atividade:

* Não vamos utilizar banco de dados
* Não vamos criar DAO
* Não vamos criar classe de entidade
* Não vamos utilizar PostgreSQL
* Não vamos utilizar objetos para armazenar registros
* Vamos trabalhar somente com telas, componentes e eventos

# Erros comuns

## 60. Criar a tela interna como JFrame

Se uma janela será aberta dentro do Desktop Pane, devemos criar:

```text
JInternalFrame Form
```

e não:

```text
JFrame Form
```

## 61. Esquecer de adicionar a tela ao Desktop Pane

Não basta criar:

```java
FrmProduto tela =
        new FrmProduto();
```

Precisamos utilizar:

```java
desktopPrincipal.add(tela);
```

## 62. Esquecer de mostrar a tela

Depois de adicionar, precisamos utilizar:

```java
tela.setVisible(true);
```

## 63. Utilizar System.exit na janela interna

Esse comando encerra toda a aplicação.

Para fechar somente o Internal Frame:

```java
this.dispose();
```

## 64. Abrir várias cópias da mesma tela

Quando isso não for desejado, podemos verificar as janelas existentes através de:

```java
desktopPrincipal.getAllFrames()
```

## 65. Confundir Desktop Pane com Tabbed Pane

Eles possuem funções diferentes.

`JDesktopPane`:

```text
Recebe janelas internas
```

`JTabbedPane`:

```text
Organiza conteúdo em abas
```

Nós podemos utilizar um `JTabbedPane` dentro de um `JInternalFrame`.

# Revisão

## 66. Perguntas

1. Para que serve o `JDesktopPane`?

2. Para que serve o `JInternalFrame`?

3. Qual é a diferença entre `JFrame` e `JInternalFrame`?

4. Como adicionamos uma janela interna ao Desktop Pane?

5. Como mostramos um Internal Frame?

6. Como fechamos somente a janela interna?

7. Por que não devemos utilizar `System.exit(0)` dentro de um Internal Frame?

8. Como descobrimos quais janelas internas estão abertas?

9. Como podemos evitar abrir a mesma tela várias vezes?

10. Como trazemos uma janela para frente?

11. Como fechamos todas as janelas internas?

12. Como descobrimos a quantidade de janelas abertas?

13. Podemos utilizar `JTabbedPane` dentro de um `JInternalFrame`?

14. Podemos utilizar `JTable` dentro de um `JInternalFrame`?

15. Qual componente recebe os Internal Frames?

# Encerramento

Nesta aula nós aprendemos a criar uma estrutura muito importante para aplicações Java Swing.

Agora nossa aplicação pode possuir uma janela principal e várias janelas internas.

Utilizamos:

```java
JDesktopPane
```

como área principal.

E utilizamos:

```java
JInternalFrame
```

para representar as telas internas.

Também aprendemos que fechar uma janela interna não significa encerrar o sistema.

Quando queremos fechar somente a janela atual, utilizamos:

```java
this.dispose();
```

Quando realmente queremos encerrar toda a aplicação, utilizamos:

```java
System.exit(0);
```

Com essa estrutura nós conseguimos organizar melhor nossas aplicações Desktop e reaproveitar todos os componentes que já estudamos.

Ainda não estamos utilizando banco de dados.

Nosso foco continua sendo dominar a interface gráfica, os eventos, a navegação entre telas e a organização da aplicação antes de avançarmos para a persistência dos dados.
