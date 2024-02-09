# SINTAXE POO
POO (Programação Orientada a Objetos) é um paradigma de programação que se baseia na ideia de "objetos", que podem conter dados na forma de campos, também conhecidos como atributos, e código, na forma de procedimentos, geralmente chamados de métodos. Esses objetos são instâncias de classes, que funcionam como modelos para criar objetos.

Os quatro pilares da programação orientada a objetos são:

1. **Encapsulamento:**
   - O encapsulamento em Java é alcançado usando modificadores de acesso (public, private, protected) para controlar o acesso aos membros de uma classe.
   
   Exemplo:
   ```java
   public class ContaBancaria {
       private double saldo;
       
       public void depositar(double valor) {
           saldo += valor;
       }
       
       public double getSaldo() {
           return saldo;
       }
   }
   ```
   Neste exemplo, `saldo` é encapsulado com o modificador `private`, impedindo o acesso direto de outras classes a ele.

2. **Herança:**
   - A herança em Java permite que uma classe herde características (métodos e atributos) de outra classe, promovendo a reutilização de código.
   
   Exemplo:
   ```java
   public class Animal {
       public void emitirSom() {
           System.out.println("Som do animal");
       }
   }
   
   public class Cachorro extends Animal {
       public void latir() {
           System.out.println("Au Au!");
       }
   }
   ```
   Na classe `Cachorro`, a palavra-chave `extends` é usada para indicar que `Cachorro` herda de `Animal`.

3. **Polimorfismo:**
   - O polimorfismo em Java permite que objetos de diferentes classes sejam tratados de maneira uniforme. Isso pode ser alcançado por meio de sobrecarga (overloading) e substituição (overriding) de métodos.
   
   Exemplo:
   ```java
   public class Animal {
       public void emitirSom() {
           System.out.println("Som do animal");
       }
   }
   
   public class Cachorro extends Animal {
       @Override
       public void emitirSom() {
           System.out.println("Au Au!");
       }
   }
   ```
   Aqui, o método `emitirSom` é substituído na classe `Cachorro`, alterando seu comportamento.

4. **Abstração:**
   - A abstração em Java é alcançada usando classes abstratas e interfaces, permitindo a definição de métodos sem implementação.
   
   Exemplo:
   ```java
   public abstract class Forma {
       public abstract double calcularArea();
   }
   
   public class Circulo extends Forma {
       private double raio;
       
       @Override
       public double calcularArea() {
           return Math.PI * raio * raio;
       }
   }
   ```
   A classe `Forma` é abstrata e define um método `calcularArea` que deve ser implementado por suas subclasses, como `Circulo`.

Estes são os quatro pilares da programação orientada a objetos implementados em JAVA. Cada pilar desempenha um papel fundamental na criação de sistemas orientados a objetos robustos e reutilizáveis.