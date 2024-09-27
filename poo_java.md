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

   public acessorio(String Cor, String Forma, floar Tamanho) {
      this.Cor = Cor;
      this.Forma = Forma;
      this.Tamanho = Tamanho;
   }
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
      acessorio pulseira = new acessorio("Verde", "Redonda", 10.0f);
   }
}
```
