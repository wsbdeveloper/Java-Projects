# Diferencia de Classe abstrata vs interface

## Interface

Define os métodos que nececssitam de implementação ao assinar o contrato, ou seja, ao extender uma interface você terá que assinar o contrato (realizar a implementação dos métodos). Uma interface é composta de todos os métodos abstratos, sem a implementação, não é possível a implementação desses métodos diretamente na interface.

```java

public abstract interface Autenticavel {
    public abstract void senha(int senha);

    public abstract boolean autentica(int senha);

    // ou podemos tirar o abstract, já que todos os métodos dentro da interface são abstratos
    // podemos remover o abstract

    public void senha(int senha);

    public boolean autentica(int senha);
}

```

## Classe Abstrata

Na classe abstrata podemos ter métodos implementados ou não, podemos definir métodos para serem implementados para sua classe filha, que herdará sua instancia. Podemos ter construtores, campos de inicialização propriedades e destrutores já a interface não. Classes abstratas não suporta multiplas herança, segue o padrão de uma classe normal, herda várias interfaces se for necessário outra coisa é que na classe abstrata não somos obrigados a implementar os métodos na sua herança.

```java
// nao pode instanciar dessa classe, pq é abstrata somente quem extender essa classe
// pode implementar as funcionalidades de abstract
public abstract class Funcionario {

 private String nome;
 private String cpf;
 private double salario;

 // metodo sem corpo, nao há implementacao
 public abstract double getBonificacao();
    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public String getCpf() {
        return cpf;
    }

    public void setCpf(String cpf) {
        this.cpf = cpf;
    }

    public double getSalario() {
        return salario;
    }

    public void setSalario(double salario) {
        this.salario = salario;
    }

}

```
