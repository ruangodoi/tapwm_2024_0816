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
   String Cor;
   float Tamanho;
   String Forma;
}
