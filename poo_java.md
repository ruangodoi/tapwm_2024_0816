# Programação orientada a objeto

## JVM, JRE, JDK

- JVM: permite que o programa roda no sistema operacioanis, como windonws e IOS, e mobile.
- JRE: execute o programa java
- JDK: permite que desenvolvedor programa no java
   
**Curiosidade**
- única blblioteca que não precisa ser importada é java.lang, pq a jvm já coloca pra nós.

## Classes e objetos

- Classes: agrupa os objetos, por exemplo, classe acessório, temos o objeto, óculos, pulseiras, etc...
- Objetos: o objeto é criado a partir de uma classe, é caracterizada por atributo e método.

```java
public class teste {
    oculos oculo = new oculos();
    pulseiras pulseira = new pulseira();
}
```

## Atrbutos e métodos

- Atributos: denini as características do objeto, por exemplo, cor, tamanho, forma. No java variável e atributos são as mesma coisas.
- Métodos: denifi o comprtamento do objeto. No java, função e método são as mesmas coisas

```java
public class acessorio {
   String Cor, Forma; // Definindo o atributo do tipo String
   float Tamanho; // Definindo o atributo do tipo float

   public void colocar() { //Definido o método do tipo void, ou seja, sem retorno
      System.out.println("Colocar no braço");
   }
   public void colocar() { //Definindo o método do tipo void
      System.out.println("Colocar no olho");
   }
}
```

**Curiosidade**

- Nas regras de nomenclatura, os nomes dos atributos, classes e métodos devem começar em letra maiúscula.

## Exemplo

**Este é o código completo**

```java
public class acessorio {
   String Cor, Forma;
   float Tamanho;

   public void Colocar_pulseira() {
      System.out.println("Colocar no braço");
   }

   public void Colocar_oculos() {
      System.out.println("Colocar no olho");
   }
}
```

```java
public class teste {
   public static void main(String[] args) {
      acessorio pulseira = new acessorio();  //Instanciou o objeto do tipo acessorio, com construtor acessorio
      acessorio oculos = new acessorio();

      pulseira.Cor = "Verde"; // Atribiu valor para atributo Cor, do objeto pulseira
      pulseira.Forma = "Redonda";
      pulseira.Tamanho = 10.0f;

      oculos.Cor = "Preto";
      oculos.Forma = "Redonda";
      oculos.Tamanho = 1.50f;

      System.out.println("A cor da pulseira " + pulseira.Cor + "\nA forma da pulseira é: " + pulseira.Forma + "O tamanho da pulseira é: " + pulseira.Tamano);

      pulseira.Colocar_pulseira(); // Chamando o método, através do objeto pulseira

      System.out.println("A cor do óculos " + Oculos.Cor + "\nA forma do óculos é: " + Oculos.Forma + "O tamanho do óculos é: " + Oculos.Tamano);

      oculos.Colocar_oculos();
   }
}
```

## Construtor

- É um método especial, onde passa por parâmetro os atributos da classe. Com isso, pode dar valor aos atributos na hora de instaciar os objetos.

- O nome do construtor tem que ser o mesmo nome da classe.

## Exemplo

```java
public class acessorio {
   String Cor, Forma;
   float Tamanho;

    public aessorio(String Cor, String Forma, floar Tamanho) {
      this.Cor = Cor;
      this.Forma = Forma;
      this.Tamanho = Tamanho;
   }
   public void Colocar_pulseira() {
      this.Cor = Cor;
      System.out.println("Colocar no braço");
   }

   public void Colocar_oculos() {
      System.out.println("Colocar no olho");
   }
}

```

```java


public class teste {
   public static void main(String[] args) {
      acessorio pulseira = new acessorio("Verde", "Redonda", 10.0f);
   }
}
```

**Tipos de construtor**

- Construtor default: não tem parâmetro, toda classe tem contrutor sendo default ou não default, se não estiver explicito na classe, tem construtor default.

```java
public class acessorio {

   public acessorio() {
   }
}
```

- Construtor não default: tem parâmetro, é um construtor personalizado.

```java
public class acessorio() {

   public aessorio(String Cor, String Forma, float Tamanho) {
      this.Cor = Cor;
      this.Forma = Forma;
      this.Tamanho = Tamanho;
   }

}
``` 

## Herança

Na programação orientada objeto java, no conceito de herança, existe superclasse e subclasse, cujo a subclasse her atributo e método na superclasse. Esse conceito é importante, pois elimina duplicidade de código,ou seja, subclasse reutiliza código, isso deixa o código flexivel, enxuto e fácil manutenção.

Para a subclasse ser herdado na superclasse, utiliza a palavra "extends".

```java
public class pulseira extends acessorio {

}
```

```java
public class oculos extends acessorio {

}
```
**Curiosidade**
- Construtor não é herdado, pois toda classe tem construtor, e construtor tem que ter o mesmo nome da classe, então não faz sentido o construtor ser herdado.

- Na sublasse, ter o construtor não default, ou seja os atributos passarem por parâmetro, os atributos que estão sendo herdado, você pode usar o comando super.

```java 
public class pulseira extends acessorio {
   public pulseira (String Cor, String Forma, float Tamanho) {
      super(Cor, Forma ,Tamanho);
   }
}
```
Nesse código, na hora de atribuir valor, qunado instaciar o objeto do tipo pulseira e construtor pulseira, e chamar os métodos do objeto do tipo pulseira, vai funcionar, porque a subclasse herda atributos e métodos da superclasse, ele reutiliza o código, não precisa digitar novamente.

## Encapsulamento

Encapsular os atributos é essencial para desenvolvimento para o sistema, pois a maior vantagem **proteger** e **padronizar** os atributos nem numa outra classe.

**Qualificador**: é o nível de encapsulamento

**Tipos de encapsulamento**

- public: variável visível por outras classe.
- Private: variável visível apenas em uma classe.
- protected: variável visível por superclasse e subclasse.
- package: varíavel apenas que estão dentro de uma determinada pasta.

**Curiosidade**
- Ao definir private nos atributos, as subclasse pode acessar e fazer manutenções usando os métodos get e set.

```java
public class acessorio {
   private String Cor, Forma;
   private float Tamanho;

   public String getCor() {
      return Cor;
   }
   public void setCor(String Cor) {
      this.Cor = Cor;
   }

   public String getForma() {
      return Forma;
   }
   public void setForma(String Forma) {
      this.Forma = Forma;
   }

   public float getTamanho() {
      return Tamanho;
   }
   public void setTamanho(float Tamanho) {
      this.Tamanho = Tamanho
   }
}
``` 
```java
public class Teste {
   public static void main(String[] args) {
      acessorio pulseira = new acessorio();

      pulseira.setCor("verde"); // set atribui valor, pois no método set, o atributo passar por parâmetro
      pulseira.setForma("redonda");
      pulseira.setTamanho(10.0f);

      System.out.println("Cor da pulseira: " + pulseira.getCor() + "Forma da pulseira: " + pulseira.getForma() + "Tamanho da pulseira: " + pulseira.getTamanho()); // get retorna o valor do atributo
   }
}
```

## Polimorfismo

Polimorfismo no java, em tradução é "várias formas", o código pode pode ter várias formas de executar o programa, deixando o código mais enxuto, flexível, padronização, evitar duplicidade de código, por exemplo, para evitar code small (duplicidade de código), pode isolar numa classe, usar o coceito de herança, jogar atributos e métodos na superclasse.  

## Abstract

Para ter a classe e método abstrato, basta colocar a palavra "abstract", isso deixa o código masi flexivel na hora de fazer manutenção, evitar duplicidade de código

**Classes abstratos**

 - Classe concreta: permite a instância de objeto.
 - Classe abstrata: não permite a instância de objeto.

 **Método abstrato**

 - Método abstrato: não têm lógica do método, é a assinatura dele, sendo que na subclasse pode reutilizar esse método, seguindo o mesmo nome e tipo de retorno.

 ```java
 public abstract class acessorio {
   
   public abstract void Colocar_puseira();
 }
 ``` 

**curiosidade**

-Para ter métodos abstrato, a classe tem que ser abstrato

##Exercício

**Faz o código acessorio usando todos esses conceitos**

```java
public abstract class acessorio {
   private String Cor, Forma;
   private float Tamanho;

   public acessorio(String Cor, String Forma, float Tamanho) {
      this.Cor = Cor;
      this.Forma = Forma;
      this.Tamanho = Tamanho;
   }

   public String getCor() {
      return Cor;
   }
   public void setCor(String Cor) {
      this.Cor = Cor;
   }

   public String getForma() {
      return Forma;
   }
   public void setForma(String Forma) {
      this.Forma = Forma;
   }

   public float getTamanho() {
      return Tamanho;
   }
   public void setTamanho(float Tamanho) {
      this.Tamanho = Tamanho;
   }

   public abstract void Colocar_pulseira();

   public abstract void Colocar_Oculos();
}
```

```java
public class pulseira extends acessorio {
   
   public pulseira(String Cor, String Forma, float Tamanho) {
      super(Cor, Forma, Tamanho);
   }

   public void Colocar_pulseira() {
      System.out.println("Colocar no braço");
   }
}
```

```java
public class oculos extends acessorio {
   
   public oculos(String Cor, String Forma, float Tamanho) {
      super(Cor, Forma, Tamanho);
   }

   public void Colocar_oculos() {
      System.out.println("Colocar no olho");
   }
}
```

```java
public class Teste {
   public static void main(String[] args) {
      acessorio pulseira = new acessorio("Verde", "Redondo", 10.0f);
      acessorio oculos = new acessorio("Amarelo", "Redondo", 10.5f);

      System.out.println("A cor da pulseira: " + pulseira.getCor() + "A forma da pulseira é: " + pulseira.getForma() + "O tamanho da pulseira é: " + pulseira.getTamanho());

      System.out.println("A cor do óculos: " + oculos.getCor() + "A forma do óculos é: " + oculos.getForma() + "O tamanho do óculos é: " + oculos.getTamanho());
   }
}
``` 
