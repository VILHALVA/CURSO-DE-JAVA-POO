# ENCAPSULAMENTO
Encapsulamento é o processo de esconder os detalhes internos de como um objeto funciona e restringir o acesso direto aos seus componentes internos. Em Java, isso é geralmente alcançado usando modificadores de acesso (public, private, protected) para controlar o acesso aos membros de uma classe (métodos e atributos).

## Exemplo de Encapsulamento em Java:
Considere a seguinte classe em Java que representa uma conta bancária:

```java
public class ContaBancaria {
    private double saldo;

    public ContaBancaria(double saldoInicial) {
        this.saldo = saldoInicial;
    }

    // Método para depositar dinheiro na conta
    public void depositar(double valor) {
        if (valor > 0) {
            this.saldo += valor;
            System.out.println("Depósito de " + valor + " realizado com sucesso.");
        } else {
            System.out.println("Valor inválido para depósito.");
        }
    }

    // Método para sacar dinheiro da conta
    public void sacar(double valor) {
        if (valor > 0 && valor <= saldo) {
            this.saldo -= valor;
            System.out.println("Saque de " + valor + " realizado com sucesso.");
        } else {
            System.out.println("Saldo insuficiente ou valor inválido para saque.");
        }
    }

    // Método para verificar o saldo da conta
    public double getSaldo() {
        return saldo;
    }
}
```

Neste exemplo, a variável `saldo` é declarada como `private`, o que significa que ela só pode ser acessada dentro da própria classe `ContaBancaria`. Isso garante que o saldo só pode ser modificado por métodos da própria classe, como `depositar()` e `sacar()`, e não diretamente por outros objetos.

O método `getSaldo()` é fornecido para permitir que outros objetos obtenham o saldo da conta, mas sem a capacidade de modificá-lo diretamente. Isso é um exemplo de encapsulamento, onde os detalhes internos da implementação da classe são ocultos e o acesso aos dados é controlado através de métodos públicos.

## Diferenças entre `get` e `set`:
Os métodos `get` e `set`, frequentemente chamados de getters e setters, são usados em programação orientada a objetos para acessar (get) e modificar (set) os valores dos atributos de uma classe. Vou explicar as diferenças entre eles:

### Método `get` (Getter):
- **Objetivo**: O método `get` é usado para obter o valor de um atributo de uma classe.
- **Convenção de nomenclatura**: O nome do método `get` geralmente começa com "get" seguido pelo nome do atributo.
- **Retorno de valor**: Um método `get` geralmente retorna o valor atual do atributo.
- **Exemplo**:

```java
public class Exemplo {
    private int numero;

    public int getNumero() {
        return numero;
    }
}
```

### Método `set` (Setter):
- **Objetivo**: O método `set` é usado para definir (setar) o valor de um atributo de uma classe.
- **Convenção de nomenclatura**: O nome do método `set` geralmente começa com "set" seguido pelo nome do atributo.
- **Parâmetros**: Um método `set` geralmente recebe um parâmetro que é o novo valor a ser atribuído ao atributo.
- **Exemplo**:

```java
public class Exemplo {
    private int numero;

    public void setNumero(int numero) {
        this.numero = numero;
    }
}
```

### Diferenças:
1. **Objetivo**: O método `get` é usado para obter o valor de um atributo, enquanto o método `set` é usado para definir o valor de um atributo.

2. **Retorno de valor**: O método `get` retorna o valor do atributo, enquanto o método `set` não retorna nenhum valor (void).

3. **Parâmetros**: O método `set` recebe um parâmetro que é o novo valor a ser atribuído ao atributo, enquanto o método `get` não recebe nenhum parâmetro.

4. **Convenção de nomenclatura**: Em Java, é comum seguir uma convenção de nomenclatura onde os métodos `get` e `set` têm nomes padronizados que começam com "get" e "set", respectivamente, seguido pelo nome do atributo.

## Diferenças entre `private`, `public` e `protect`:
Em Java, os modificadores de acesso (`private`, `public` e `protected`) são usados para controlar o acesso aos membros de uma classe (métodos e atributos) por outras classes. Vou explicar as diferenças entre esses modificadores:

### `private`:
- **Acesso restrito**: Os membros declarados como `private` só podem ser acessados dentro da própria classe onde foram declarados.
- **Encapsulamento**: É útil para garantir o encapsulamento, pois permite que os detalhes internos de uma classe sejam ocultados e protegidos de acesso externo.
- **Exemplo**:

```java
public class Exemplo {
    private int numero;

    public Exemplo() {
        this.numero = 10;
    }

    private void metodoPrivado() {
        // Este método só pode ser chamado dentro da classe Exemplo
    }
}
```

### `public`:
- **Acesso irrestrito**: Membros declarados como `public` podem ser acessados de qualquer lugar, dentro ou fora da classe onde foram declarados.
- **Visibilidade global**: É útil para fornecer uma interface pública para os usuários da classe, permitindo que eles acessem seus métodos e atributos.
- **Exemplo**:

```java
public class Exemplo {
    public int numero;

    public Exemplo() {
        this.numero = 10;
    }

    public void metodoPublico() {
        // Este método pode ser chamado de qualquer lugar
    }
}
```

### `protected`:
- **Acesso na mesma classe e subclasses**: Os membros declarados como `protected` podem ser acessados dentro da mesma classe e também por subclasses (mesmo que estejam em pacotes diferentes).
- **Exemplo**:

```java
public class Exemplo {
    protected int numero;

    public Exemplo() {
        this.numero = 10;
    }

    protected void metodoProtegido() {
        // Este método pode ser chamado dentro da classe Exemplo e suas subclasses
    }
}
```

## Benefícios do Encapsulamento:
1. **Segurança dos dados**: Encapsular os dados dentro de uma classe, controlando o acesso a eles, protege-os contra modificações acidentais ou não autorizadas.

2. **Modularidade e manutenção**: O encapsulamento promove a modularidade do código, tornando mais fácil entender, modificar e manter o sistema, pois os detalhes internos de uma classe são isolados do restante do programa.

3. **Reutilização de código**: Ao encapsular os detalhes de implementação dentro de classes, é possível reutilizar essas classes em diferentes partes do sistema sem modificar seu comportamento externo.

