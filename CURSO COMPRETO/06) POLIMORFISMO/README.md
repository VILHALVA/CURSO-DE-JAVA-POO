# POLIMORFISMO
Polimorfismo permite que objetos de diferentes classes sejam tratados de forma uniforme, proporcionando flexibilidade e extensibilidade ao código. Existem duas formas principais de polimorfismo em Java: polimorfismo de subtipo (ou polimorfismo de herança) e polimorfismo de sobrecarga (ou polimorfismo estático). Vou explicar cada um deles:

## Polimorfismo de Subtipo (Herança):
O polimorfismo de subtipo ocorre quando uma classe herda de outra classe e substitui (ou sobrescreve) um método da classe base. Isso permite que um objeto da classe derivada seja tratado como um objeto da classe base.

Exemplo:

```java
// Superclasse
class Animal {
    public void fazerSom() {
        System.out.println("Animal fazendo som");
    }
}

// Subclasse
class Cachorro extends Animal {
    @Override
    public void fazerSom() {
        System.out.println("Cachorro latindo");
    }
}

// Exemplo de uso
public class ExemploPolimorfismo {
    public static void main(String[] args) {
        Animal animal = new Cachorro(); // Polimorfismo de subtipo
        animal.fazerSom(); // O método fazerSom() do Cachorro é chamado
    }
}
```

Neste exemplo, a classe `Cachorro` herda da classe `Animal` e sobrescreve o método `fazerSom()`. Ao criar um objeto do tipo `Cachorro` e atribuí-lo a uma referência do tipo `Animal`, podemos chamar o método `fazerSom()` e obter o comportamento específico da classe `Cachorro`. Isso é polimorfismo de subtipo.

## Polimorfismo de Sobrecarga (Estático):
O polimorfismo de sobrecarga ocorre quando duas ou mais classes têm métodos com o mesmo nome, mas diferentes parâmetros. Isso permite que métodos com o mesmo nome se comportem de maneira diferente com base nos argumentos fornecidos.

Exemplo:

```java
class Calculadora {
    public int somar(int a, int b) {
        return a + b;
    }

    public double somar(double a, double b) {
        return a + b;
    }
}

// Exemplo de uso
public class ExemploPolimorfismo {
    public static void main(String[] args) {
        Calculadora calc = new Calculadora();
        int resultadoInteiro = calc.somar(5, 3); // Chama o método com inteiros
        double resultadoDouble = calc.somar(2.5, 3.5); // Chama o método com doubles
        System.out.println("Resultado Inteiro: " + resultadoInteiro);
        System.out.println("Resultado Double: " + resultadoDouble);
    }
}
```

Neste exemplo, a classe `Calculadora` tem dois métodos `somar()`, um que aceita dois inteiros e outro que aceita dois doubles. Dependendo dos tipos dos argumentos fornecidos, o compilador Java selecionará automaticamente o método apropriado para chamar. Isso é polimorfismo de sobrecarga.

Em resumo, o polimorfismo em Java permite que objetos de diferentes classes sejam tratados de forma uniforme, aumentando a flexibilidade e extensibilidade do código. Ele é alcançado através de herança (polimorfismo de subtipo) e sobrecarga de métodos (polimorfismo de sobrecarga).