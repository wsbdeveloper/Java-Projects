# Compiladores e método main

## Método main

O tal método de entrada deve seguir algumas regras para ser executado pela JVM:

1. Ser público (public);
1. Ser estático (static);
1. Não ter retorno (void);
1. Ter o nome main;

Receber como parâmetro um array ou varargs de String (String[] ou String...).

São então métodos main válidos os seguintes exemplos:

```java

//Parâmetro como array
public static void main (String[] args) {}

//Parâmetro como varargs
public static void main (String... args) {}

//A ordem dos modificadores não importa
static public void main(String[] args) {}

//O nome do parâmetro não importa
public static void main (String... argumentos){}

//Também é uma definição válida de array
public static void main (String args[]) {}

```

## Compilador java - javac

Para criar um programa java, é preciso escrever um código-fonte e, através de um compilador, gerar o executável (bytecode). O compilador do JDK (Java Development Kit) é o javac. Para a prova de certificação, devemos conhecer o comportamento desse compilador.

```java

class Prova {
    double tempo;
}

```

```bash
    javac Prova.java
```

Compilando com package

```java
    package certificacao;

    class Prova {
        double tempo;
    }
```

```bash
    javac certificacao/Prova.java
```

Escolhendo a versão no momento da compilação.

```bash
    javac MinhaClasse.java -source 1.3
```

Vamos utilizar um exemplo para mostrar o funcionamento do comando java, criando o arquivo Teste.java no mesmo diretório, no mesmo pacote:

```java
    package certificacao;
    class Teste {
        public static void main(String[] args) {
            Prova p = new Prova();
            p.tempo = 210;
            System.out.println(p.tempo);
        }
    }
```

compilar

```bash
  javac certificacao/Teste.java
  java certificacao.Teste
```

## Propriedades na linha de comando

A prova ainda cobra conhecimentos sobre como executar um programa java passando parâmetros ou propriedades para a JVM e essas propriedades são identificadas pelo -D antes delas. Este -D não faz parte da chave.

```java
    java -Dchave1=abc -Dchave2=def Foo xpto bar
```

## Classpath

Para compilar ou para executar, é necessário que os comandos javac e java possam encontrar as classes referenciadas pela aplicação java.

A prova de certificação exige o conhecimento do algoritmo de busca das classes. As classes feitas pelo programador são encontradas através do classpath (caminho das classes).

O classpath é formado por diretórios, jars e zips que contenham as classes e pacotes da nossa aplicação. Por padrão, o classpath está configurado para o diretório corrente (.).

## Configurando o classpath

Há duas maneiras de configurar o classpath:

1. Configurando a variável de ambiente CLASSPATH no sistema operacional.

Basta seguir as opções do SO em questão e definir a variável. Isso é considerado uma má prática no dia a dia porque é um classpath global, que vai valer para qualquer programa java executado na máquina.

2. Com as opções -cp ou -classpath dos comandos javac ou java.

É a forma mais usada. Imagine que queremos usar alguma biblioteca junto com nosso programa:

```java
    javac -cp /diretorio/biblioteca.jar Prova.java

    java -cp /diretorio/biblioteca.jar Prova
```

## arquivos JAR

ara facilitar a distribuição de bibliotecas de classes ou de aplicativos, o JDK disponibiliza uma ferramenta para a compactação das classes java.

Um arquivo JAR nada mais é que a pasta de nossas classes no formato ZIP mas com extensão .jar.

Para criar um jar incluindo a pasta scjp que fizemos antes:

```java
    jar -cf bib.jar scjp
```

Agora podemos executar nossa classe usando esse jar:

```java
   java -cp bib.jar scjp.Prova
```

## META-INF/Manifest.mf

Ao criar o jar usando o comando jar do JDK, ele cria automaticamente a pasta META-INF, que é usada para configurações relativas ao nosso jar. E dentro dela, cria o arquivo Manifest.mf.

Esse arquivo pode ser usado para algumas configurações. Por exemplo, é possível dizer qual classe do nosso jar é a classe principal (Main-Class) e que deve ser executada.

Basta criar um arquivo chamado Manifest.mf com a seguinte instrução indicando a classe com o método main:

```bash
    Main-Class: scjp.Teste
```

E depois gerar o jar passando esse arquivo:

```bash
    jar -cmf bib.jar meumanifest scjp
```

Na hora de rodar um jar com Main-Class, basta usar:

```bash
    java -jar bib.jar
```

Compilando um arquivo jar do pacote b

```java
    package b;
    class A {
        public static void main(String[] args) {
            System.out.println(args[0]);
        }
    }
```

Execute :

```bash
    java -cp programa.jar b.A
```
