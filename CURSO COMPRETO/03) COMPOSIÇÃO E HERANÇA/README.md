# COMPOSIÇÃO E HERANÇA
A composição é um princípio de design em que objetos complexos são construídos a partir de outros objetos mais simples. Em outras palavras, um objeto contém outros objetos como parte de sua estrutura interna. A relação entre os objetos é frequentemente referida como uma relação "tem-um".

Exemplo de composição em Java:

```java
class Motor {
    public void ligar() {
        System.out.println("Motor ligado");
    }
}

class Carro {
    private Motor motor;

    public Carro() {
        this.motor = new Motor(); // Composição: o carro tem um motor
    }

    public void ligarCarro() {
        motor.ligar();
        System.out.println("Carro ligado");
    }
}
```

Neste exemplo, a classe `Carro` possui uma instância da classe `Motor` como um de seus atributos. Isso demonstra a relação de composição entre as duas classes.

## Herança:
Herança é outro princípio fundamental da POO, onde uma classe pode herdar atributos e métodos de outra classe. A classe que herda é chamada de subclasse ou classe derivada, enquanto a classe da qual ela herda é chamada de superclasse ou classe base. A herança é frequentemente referida como uma relação "é-um".

Exemplo de herança em Java:

```java
class Animal {
    public void comer() {
        System.out.println("Animal comendo");
    }
}

class Cachorro extends Animal {
    public void latir() {
        System.out.println("Cachorro latindo");
    }
}
```

Neste exemplo, a classe `Cachorro` herda da classe `Animal`, o que significa que ela pode acessar o método `comer()` definido na classe `Animal`. A relação aqui é que um cachorro é um tipo de animal.

## Diferenças entre Composição e Herança:
1. **Flexibilidade**: Composição permite uma maior flexibilidade, pois as relações entre objetos podem ser alteradas em tempo de execução. No entanto, na herança, as relações entre as classes são definidas em tempo de compilação e não podem ser alteradas facilmente.

2. **Acoplamento**: Composição tende a resultar em menor acoplamento entre classes, pois as classes são independentes umas das outras. Por outro lado, herança pode levar a um acoplamento mais forte, pois as subclasses dependem das superclasses.

3. **Reutilização de código**: Ambas as técnicas promovem a reutilização de código, mas a herança pode levar a problemas de herança múltipla e hierarquias profundas, enquanto a composição evita esses problemas.

Em resumo, composição é geralmente preferida sobre herança sempre que possível, pois oferece maior flexibilidade e menor acoplamento entre classes. No entanto, herança ainda é uma ferramenta útil em certos contextos, especialmente quando há uma clara relação "é-um" entre as classes.