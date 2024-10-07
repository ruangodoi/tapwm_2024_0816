# Explcação do projeto java

## Classe Conta

**Classe abstract**

- Classe concreta: pode instaciar objeto diretamente
- Classe abstract: não pode instanciar o objeto diretamente

- A super é defina como defina como abastrato, ou seja, pode ter instancia de objeto diretamente, e temos métodos abstaratos (Pra ter métodos abstrato, a classe precisa ser abstrato), isso serve como modelo para as suas subclasses.

**Encapsulamento**

- Quando encapsulo algum atributo, estou ocultando, protendo o dados pra não ser acessado diretamente na subclasse, isso pra segurançae deixa o código flexivel, quando definino como **private**, para as subclasse acessar e manipular os atributos usa o método get e set, get pegar o o atrbuto, ele vai retornar, e método set, o atrbuto passa por parâmettro no meu método, isso é deixa certo padrão para subclasses acessarem o atrbuto da superclasse. Outra forma da subclasse acessar, o atributo é defina como protected, quando definido como protected, o atrbuto é acessivel pelo super e subclasse.

**Métodos concretos e métodos abstract**

- Método concreto: tem a implementção da lógica do método

```java
public class Conta {
    public void transeferir(Conta outraConta,double Valor) {
        if(this.sacar(Valor)) {
            outraConta.depositar(Valor);
        }
    }
}
```

- Método abstrato: não tem a implementação da lógica do método, só tem a assinatura

```java
public class Conta {
    public abstract void depositar(double Valor);
}
```

- Quando tem método abstrato, as subclasses tem que sobrescrever o método, sendo método age de maneira diferenete em cada subclasse

**Polimorfismo**

- Poliformismo é varías formas, de se fazer o código, tem reutização de código, e deixar ele mais flexível.

- O método abstract, é um exemplo disso, quando tem só assinatura do meu método, as subclaase vão sobrescever o método abstarct, assim o método tem comportamento especifica desse código, ele não está criando, está reutizando o código.

- E para sobrever o método, o método tem que ter o mesmo nome e tipo de retorno.

**Construtor**

- O construtor é um método especial, cujo nome tem que ser o mesmo da própria classe

- Construtor default: não tem parametro, num classe onde so tem atrbutos e métodos, tem construtor, só que é default.

- Construtor não default: tem parâmetro, isso, facilita dna hora de instanciar objeto usando o construtor não default, posso atribuir valor ao meu atrbuto na hora que instancio a classe, por os atrbutos passa por parâmetro, isso otimiza linha de código.

- Quando declaro construtor não default, tenho que escrver o construtor default, pois a JVM entende que quando escrevo construtor não default, e quero usar construtor default, tenho que escrever o construtor default.

## Classe Conta_corrente

- Ela é uma subclasse da conta Conta, usando a palavara **extends**.

**Herança**

- Quando a subclasse herda **atributos** e **métodos** da super classe, isso evita duplicidade de código, tendo reutilização no meu código.

- Ele não herda construtor pois, o nome do construtor tem sque ser o mesmo da própria classe, então toda classe tem seu construtor

**Sobreposição**

- Quando definido método abstarct na super classe, a subclasse tem que sobresecever o método, para ter implementação da lógica especifíca na subclasse.

- Usa o comando **@Override**

```java
public class Conta_corrente extends Conta {
    @Override
    public void depositar(double Valor) {
        Saldo += Valor;
    }
}
```
## Classe Conta_poupanca

- Na classe, não temos nenhum reuisitos de negócio da própria, como a classe é subclasse da classe Conta, então herda atributos e métodos da superclasse. 

- Como não herda contrutor, cria o construtor sendo o nome Conta_poupanca, e para os atrbutos herdado passar por parâmetro, usa o comando **super**, ele puxa os atributos e métodos da superclasse.

## interface Tributavel

- Uma interface, só possui abstrações do método, não tem implementação lógica do método, não possui nem atrbuos e métodos concretos. Ele cria certo padrão, para as classes que assinam o contrato com a interface, poder sobrescrever todos os métodos criados da interface.

- No código, a classe conta_corrente e seguro de vida, assinam contrato com a interface, então precisa utilizar tdos os métodos da interface sendo método abstract ou não, apenas a assinatura dele, e para a classe sobrescrver precisa ter o mesmo nome e tipo de retorno. Isso já entra o conceito de polimorfismo, pois é o mesmo método, só que tem comportamento diferentes das classes.








