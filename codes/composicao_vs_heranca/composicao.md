# Mundo Java Herança VS Composição

## Herança

Herança é utilizado para reutilização e polimorfismo em java, por exemplo, uma classe Gerente extende Funcionario, estamos utilizando a classe funcionario para reutilizar seus atributos e funções e construindo o polimorfismo.

## Interface

A interface é comparada a um contrato, ou seja, todos que implementar uma interface será necessário assinar os tópicos dentro do contrato. São classes abstratas que consiste em somente as assinaturas dos métodos também abstratos um exemplo:

```java
public abstract interface Autenticavel {
    public abstract void setSenha(int senha) ;

    public abstract boolean autentica(int senha) ;
}
```

## Composição em Classes no Java

Composições são formas de reutilização de código, em comparação com herança ela precisa de dois componentes, reutilização e polimorfismo já a composição só trabalha com reutilização, onde temos um problema de repetição de código em vários lugares que não foi solucionado pelo contrato por exemplo.

Com composição teremos uma classe que delega as funcionalidades para outra classe com métodos abstratos como por exemplo:

```java

// Classe cliente para implementação de composição

public class Cliente implements Autenticavel {
    private AutenticavelUtil util;

    public Cliente(){
        this.util = new AutenticavelUtil();
    }


 @Override
    public void setSenha(int senha){
        this.util.setSenha(senha);
    }

    @Override
    public boolean autentica(int senha){
        return this.util.autentica(senha);
    }
}


// Classe AutenticacaoUtil que é a classe de composição.

public class AutenticavelUtil {

    private int senha;

    public void setSenha(int senha) {
        this.senha = senha;
    }

    public boolean autentica(int senha) {
        if (this.senha == senha) {
            return true;
        } else {
            return false;
        }
    }

}
```

## Conclusão

Para utilização da composição é preciso entender que usamos esses tópicos em diferentes momentos dos nossos projetos, vamos a uma análise.

1. Composição - Reutilização de código.
1. Herança - Polimorfismo e reutilização de código.
1. Interfaces -  Abstração de códigos.
