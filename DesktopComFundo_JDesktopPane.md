# Adicionando uma imagem de fundo ao JDesktopPane no Java Swing

Nesta atividade, nós vamos aprender a criar um `JDesktopPane` personalizado capaz de exibir uma imagem de fundo.

A principal vantagem dessa abordagem é que a imagem será redimensionada automaticamente quando a janela principal for maximizada ou tiver seu tamanho alterado.

## 1. Criar uma classe customizada para o DesktopPane

Em vez de utilizarmos diretamente o `JDesktopPane` padrão da paleta do NetBeans, vamos criar uma versão personalizada que sabe desenhar uma imagem de fundo.

### Passo 1

No projeto do NetBeans, clique com o botão direito sobre o pacote onde estão as classes do sistema.

Depois selecione:

**Novo > Classe Java**

### Passo 2

Dê o seguinte nome para a classe:

```text
DesktopComFundo
```

### Passo 3

Dentro da classe criada, coloque o seguinte código:

```java
import java.awt.Graphics;
import java.awt.Image;
import javax.swing.ImageIcon;
import javax.swing.JDesktopPane;

public class DesktopComFundo extends JDesktopPane {

    private Image imagem;

    public DesktopComFundo() {

        // Altere "fundo.jpg" para o caminho da sua imagem dentro do projeto.
        // O ideal é colocar a imagem na pasta src ou em um pacote de recursos.

        java.net.URL imgUrl = getClass().getResource("/fundo.jpg");

        if (imgUrl != null) {
            this.imagem = new ImageIcon(imgUrl).getImage();
        }
    }

    @Override
    protected void paintComponent(Graphics g) {

        super.paintComponent(g);

        if (imagem != null) {

            // Desenha a imagem preenchendo todo o tamanho atual do componente.

            g.drawImage(
                imagem,
                0,
                0,
                getWidth(),
                getHeight(),
                this
            );
        }
    }
}
```

## Entendendo o código

A nossa classe `DesktopComFundo` herda todas as características do componente `JDesktopPane`.

```java
public class DesktopComFundo extends JDesktopPane
```

Isso significa que ela continua funcionando como um Desktop Pane normal, inclusive permitindo que nós utilizemos `JInternalFrame` dentro dela.

A diferença é que adicionamos o atributo:

```java
private Image imagem;
```

Esse atributo será responsável por armazenar a imagem utilizada como fundo.

No construtor da classe, procuramos a imagem dentro do projeto:

```java
java.net.URL imgUrl = getClass().getResource("/fundo.jpg");
```

Caso a imagem seja encontrada, ela será carregada:

```java
if (imgUrl != null) {
    this.imagem = new ImageIcon(imgUrl).getImage();
}
```

Depois sobrescrevemos o método:

```java
paintComponent(Graphics g)
```

Esse método é utilizado pelo Swing sempre que o componente precisa ser redesenhado.

Dentro dele utilizamos:

```java
g.drawImage(
    imagem,
    0,
    0,
    getWidth(),
    getHeight(),
    this
);
```

Os métodos `getWidth()` e `getHeight()` pegam automaticamente a largura e a altura atuais do `JDesktopPane`.

Dessa forma, quando a janela aumentar ou diminuir, a imagem acompanhará o novo tamanho.

## 2. Adicionar a imagem ao projeto

Agora precisamos colocar a imagem que será utilizada como fundo dentro do projeto.

Uma forma simples é colocar o arquivo diretamente dentro da pasta `src`.

Exemplo:

```text
src
    DesktopComFundo.java
    fundo.jpg
```

Nesse caso, o código poderá utilizar:

```java
getClass().getResource("/fundo.jpg");
```

Também podemos criar um pacote exclusivo para imagens.

Exemplo:

```text
src
    imagens
        fundo.jpg
```

Nesse caso, precisamos alterar o caminho no código:

```java
getClass().getResource("/imagens/fundo.jpg");
```

## 3. Limpar e construir o projeto

Antes de utilizarmos o novo componente no Editor Visual do NetBeans, devemos compilar o projeto.

No NetBeans, utilize:

**Limpar e Construir Projeto**

Também podemos utilizar o atalho:

```text
Shift + F11
```

Isso fará com que o NetBeans reconheça corretamente a nova classe personalizada.

## 4. Usar o componente customizado no Editor Visual

Agora podemos utilizar o nosso `DesktopComFundo` dentro da janela principal.

Abra o formulário `JFrame` principal do sistema.

Normalmente será uma classe semelhante a:

```text
FrmPrincipal
```

ou:

```text
TelaPrincipal
```

Depois localize o arquivo:

```text
DesktopComFundo.java
```

na árvore de arquivos do NetBeans.

Clique sobre ele e arraste para dentro do formulário principal.

O NetBeans adicionará o componente personalizado ao formulário.

## 5. Ajustar o tamanho do DesktopComFundo

Depois de adicionar o componente, precisamos fazer com que ele ocupe toda a área disponível da janela.

Podemos ajustar manualmente o componente no Editor Visual.

Porém, uma opção melhor é utilizar o layout:

```text
BorderLayout
```

Com o `BorderLayout`, podemos colocar o `DesktopComFundo` na região central da janela.

```text
CENTER
```

Assim, quando a janela for redimensionada, o componente acompanhará automaticamente o tamanho disponível.

## 6. Testar o sistema

Agora execute o projeto.

Maximize a janela principal.

Depois diminua e aumente novamente o tamanho da janela.

A imagem de fundo deverá acompanhar automaticamente o tamanho do `JDesktopPane`.

Isso acontece porque utilizamos:

```java
getWidth()
```

e:

```java
getHeight()
```

no momento em que a imagem é desenhada.

## Resultado esperado

Ao final desta atividade, nós teremos uma janela principal utilizando um `JDesktopPane` personalizado com imagem de fundo.

O componente continuará permitindo normalmente a abertura de telas internas utilizando `JInternalFrame`.

Além disso, quando a janela principal for maximizada ou redimensionada, a imagem será adaptada automaticamente ao espaço disponível.

## Estrutura esperada do projeto

Um exemplo simples da organização pode ficar assim:

```text
ProjetoJavaSwing
│
└── src
    │
    ├── DesktopComFundo.java
    ├── FrmPrincipal.java
    │
    └── imagens
        └── fundo.jpg
```

Caso utilize essa estrutura, lembre de alterar o caminho da imagem para:

```java
getClass().getResource("/imagens/fundo.jpg");
```

## Observação importante

O nome do arquivo e o caminho informado no método `getResource()` precisam ser exatamente iguais ao arquivo existente no projeto.

Por exemplo:

```text
fundo.jpg
```

é diferente de:

```text
Fundo.jpg
```

Também devemos conferir a extensão correta da imagem.

Exemplos:

```text
.jpg
.png
.jpeg
```

Se utilizarmos uma imagem chamada:

```text
fundosistema.png
```

o código deverá ficar assim:

```java
getClass().getResource("/imagens/fundosistema.png");
```

Com isso, nós conseguimos deixar a tela principal do sistema visualmente mais organizada, mantendo o funcionamento normal do `JDesktopPane` e dos `JInternalFrame`.
