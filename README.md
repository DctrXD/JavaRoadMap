# Desenvolvedor Iniciante

Um desenvolvedor iniciante precisa entender o básico:

- POO básico
    - Getters, Setters e construtores (Guanabara: https://youtu.be/6i-_R5cAcEc)
    - É necessário saber pelo menos como criar um `Peixe extends Animal`, ou seja, o básico da herança.
    - Classes, métodos e campos finais (Carlos Henrique Java: https://youtu.be/Uhph07-JfZs)
    - Modificadores de acesso: `protected`, `public`, e `private`
- Métodos, classes e campos estáticos
- Estruturas de controle como If, else e else if
- Loops como Foreach (for) e While
- Tipos numéricos como Double, Float e Integer.
- Arrays
- Lançamento de exceções com `throw exception`
- Blocos de tratamento de exceções com try, catch e finally

Além disso, é importante saber o que são:
- Parâmetros dos métodos
- Tipos numéricos como Double, Float e Integer.
- O básico sobre tipos primitivos (como `int`, `float` e `double`)
- Diferentes tipos de retorno como `return null;`, `return value;`, `return;`

**NUNCA** crie campos (fields) sem definir explicitamente um modificador de acesso, como:
```java
String text = "";
```

Sempre prefira adicionar um modificador de acesso:
```java
private String text = "";
```

*E não se esqueça do `final` também, use sempre que possível.*

# Desenvolvedor Intermediário

*É aqui que muitos desistem*

**Lembrando:** Quanto mais avançado você se torna, menos `static` você utiliza no seu código. Os melhores programadores Java usam um total de ZERO `static`, você não precisa disso.

Neste nível, você já é mais avançado, mas deve aprender isso para poder se sentar na mesa dos adultos:

- Conhecimento sobre git/github
- Conhecimento em algum framework de build
    - Como Maven ou Gradle (Eu recomendo Maven, mas é uma questão de preferência)
- POO avançado:
    - Interfaces e suas utilidades (São muito mais úteis do que parecem)
    - Classes `record` e sua INUTILIDADE
    - Parâmetros finais nos métodos
    - Classes seladas (`sealed`)
    - Métodos abstratos em classes abstratas
    - Classe utilitária (classe helper)
    - `import static`
- Anotações
    - @Deprecated
    - Domínio do @Override
    - Nesta fase, você já deve parar de suprimir avisos com @SuppressWarnings ou qualquer outra anotação
- Código limpo:
    - O básico das anotações da Jetbrains (https://github.com/JetBrains/java-annotations)
        - São muito úteis, e atualmente são usadas em grande parte dos códigos open source
        - @NotNull
        - @Nullable
        - @Range
        - @Internal e @Experimental
    - Técnica `early return` ou `return early` para ifs e elses (Exemplos abaixo)
- Criar sua própria `Exception`
    - Entenda também o conceito de `Error`, `Throwable`, `RuntimeException`
    - Estude sobre as exceções que já existem, como `NullPointerException` e `IllegalStateException`
- Java Reflections
    - Saiba como acessar um método ou campo privado e tudo derivado.
    - Esse assunto é bem subestimado, mas muito útil.
- Conhecimento intermediário de MySQL e SQLite (SQL no geral)
- Bibliotecas (nativas ou não):
    - Tenha conhecimento das classes nativas do Java, para não gastar tempo criando código que já existe.
    - TUDO sobre Tipos genéricos (Generic Types), esse assunto é mais complexo do que parece, estude MUITO sobre.
        - Métodos genéricos também, tipo `public final <T> T getValue()`
        - Tipo genérico desconhecido `?`
    - Tipos de Data: Date, OffsetDateTime, Duration, Instant, ZonedDateTime, LocalDateTime, etc...
    - Json (Eu recomendo o GSON do Google)
    - File
        - Saiba usar essa classe como a palma de sua mão
    -
    - Aprenda sobre `java.util.Optional` (Fácil, mas útil)
    - Saiba usar o `java.util.function.Consumer` e suas utilidades
    - Saiba usar o `java.util.function.Predicate` e suas utilidades
    - Saiba usar o `java.util.function.Supplier` e suas utilidades
    - Entenda a diferença entre Set<T> e List<T>
    - Saiba usar o Map<K, V>
    - Aprenda a encurtar seu código:
        - `Stream` do Java
            - Saiba usar o `Stream#filter`
            - Saiba usar o `Stream#map`
            - Saiba usar o `Stream#anyMatch`
    - Serializable
        - A maioria das exceptions nativas possuem essa interface implementada, busque saber o motivo disso.
    - InputStream e OutputStream (ESTUDE MUITO SOBRE, MUITO SUBESTIMADO)
    - O básico/intermediário de Socket e Channel (do netty.io) (Complicado, mas vale a pena se tiver tempo livre)
        - O básico para estabelecer uma conexão e enviar/receber pacotes
    - UUID
- Saiba sobrescrever o `equals()` e `hashCode()` de suas classes.
    - Esses dois métodos são extremamente importantes, mas muito subestimados. Eles controlam basicamente tudo em seu objeto e você **NEM SABE**, se aprimore nisso o quanto antes e entenda exatamente o que eles fazem.
- O básico das criptografias (`MD5`, `SHA-256`, etc...)
- Matemática intermediária/avançada
    - Saiba usar seno, cosseno e tangente
    - Saiba elaborar suas próprias fórmulas para seus projetos
- Saiba o básico sobre regex

- Pratique, muita prática.
- Pratique, muita prática.
- Pratique, muita prática.

# Técnica `early return`

Basicamente, é uma forma de capturar os erros dentro dos ifs e só executar o código no último else.
Isso evita o famoso `hadouken de if`, e melhora muito a legibilidade do seu código. Aqui está um exemplo:
```java
if (!user.isAuthenticated()) { // O usuário não está autenticado
    // Erro
} else if (!user.hasPermission()) { // O usuário não tem permissão
    // Erro
} else if (!user.has...()) { // Outro possível erro
    // Erro
} else {
    // Tudo ok com o código, executar.
}
```

# Desenvolvedor Avançado (sofredor)

*Se você chegou até aqui, quero te parabenizar, você possui um conhecimento IMPRESSIONANTE e pouco encontrado por aí.*

**Você chegou ao Boss Final, e se acha que está pronto, ainda não está KKKKKKKKKKKKK**

- Domínio total sobre o ambiente de testes
    - ISSO É MUITO ÚTIL, MAS POUCO FALADO!!
    - Domínio da anotação `org.junit.Test`
- Domínio total de manipulação de Bytes
    - Saiba como manipular bytes usando os operadores correspondentes (tais como `|`, `&`, `~` e outros)
- Domínio total de criptografias úteis
    - Tais como:
        - AES/ECB
        - AES/CBC, AES/GCM e derivados
            - Entenda como funciona o `Vetor de Inicialização`
- Conhecimento para criar seu próprio repositório Maven
    - É bom ter no currículo
- Anotações
    - Domínio de todas as anotações da Jetbrains
        - @Contract também, muito subestimado 🙂
    - Criar sua própria anotação
        - Criar o seu próprio `Annotation processor`
    - `@FunctionalInterface`, 
- Domínio do uso do `volatile` em Java
- Multi-threading
    - Você precisa saber isso, é muito importante.
    - Domínio no uso de `Thread` e `Runnable`
    - Amplo conhecimento sobre `Atomic`, como `AtomicInteger` ou `AtomicBoolean`
    - Palavra-chave `synchronized`
    - CompletableFuture e ExecutorService
- Conhecimento amplo e vasto sobre matemática
- Amplo conhecimento sobre renderização e bibliotecas relacionadas
    - Tipo JPanel, JFrame, Graphics, Graphics2D, etc...
    - Saber renderizar objetos 3D complexos em uma tela 2D
    
    - Conhecimento sobre Tree Rendering
    - Conhecimento sobre Renderização Responsiva
    - Conhecimento sobre Renderização em Colunas
- Domínio total sobre APIs externas
    - Se te derem uma API (seja qual for) e uma IDE aberta, você deve saber integrar seu código nela. Seja qual API for
    - APIs Socket
    - RestAPIs
    - E outras...
- Saiba o básico de desenvolvimento Web com Java
- Mais interfaces do que classes no seu código
    - Pode parecer estranho, mas um bom código possui mais interfaces do que classes
- ZERO uso de `static` (Opcional, depende muito do projeto, mas geralmente você não usará static além da `main(String[])`)
- Código extremamente limpo com as melhores técnicas
- Carregamento e descarregamento de bibliotecas em tempo de execução (Runtime)
- Domínio da palavra-chave `native` em Java
- Conhecimento para criar seu próprio código fora do Java, mas que use a JVM (Opcional

)
- Possuir a capacidade de criar **tudo** o que o desenvolvedor intermediário faz, mas do **zero**, sem o uso de bibliotecas externas.
    - NÃO É para ser usado no dia a dia, mas para testar sua capacidade de absorção.
- Domínio da JVM e tudo relacionado
    - ClassLoader
    - Java Agent
    - Acesso aos métodos `open` e `write` na JVM
    - `sun.misc.Unsafe` (AVANÇADO e POUCO UTILIZADO, nem mesmo precisa ser aprendido)
- Domínio da Criação de Extensões e Plugins
- Conhecimento das melhores práticas de gerenciamento de Memória RAM
- Refactorização constante do seu código
    - É importante sempre revisar seu código e buscar melhorar o máximo que puder
- Domínio completo de Algoritmos e Estruturas de Dados
- Matemática Avançada com muito ênfase em Matemática Discreta
- Domínio completo sobre a arquitetura de SO
    - Isso inclui o aprendizado de como programar Drivers e criar ambientes para testes em Níveis de Kernel
- Domínio total de Redes
    - Saber configurar servidores avançados em ambientes Linux
    - Configuração de Redes Internas
    - Criação de sistemas P2P para compartilhamento de arquivos
- Conhecimento sobre Paralelismo
    - Isso inclui aprender sobre a teoria de paralelismo
    - Focar na criação de algoritmos paralelos eficientes

- Saber realizar um Pull Request em um projeto Java Open Source no Github e ser aprovado.


# Recursos para Desenvolvimento Java

## 1. Programação Orientada a Objetos (POO)
### 1.1 Introdução à POO
- [Programação Orientada a Objetos com Java | Curso em Vídeo - Gustavo Guanabara](https://youtu.be/6i-_R5cAcEc)
  - **Descrição:** Um curso completo de POO em Java, abordando desde os conceitos básicos até práticas mais avançadas.
- [Herança em Java | DevDojo](https://devdojo.academy/?p=1413)
  - **Descrição:** Tutorial sobre como implementar herança em Java, com exemplos práticos.

### 1.2 Modificadores de Acesso
- [Guia Completo de Modificadores de Acesso em Java | Baeldung](https://www.baeldung.com/java-access-modifiers)
  - **Descrição:** Um artigo detalhado que explica como e quando usar modificadores de acesso em Java.
- [Entendendo `public`, `private`, `protected` em Java | GeeksforGeeks](https://www.geeksforgeeks.org/access-modifiers-java/)
  - **Descrição:** Este artigo oferece uma visão clara dos modificadores de acesso em Java com exemplos de código.

## 2. Estruturas de Controle e Tipos de Dados
### 2.1 Estruturas Condicionais
- [Como Usar If, Else e Else If em Java | w3schools](https://www.w3schools.com/java/java_conditions.asp)
  - **Descrição:** Um guia interativo para aprender a usar estruturas condicionais em Java.
- [Vídeo: Estruturas Condicionais em Java | Código Fonte TV](https://youtu.be/D9QeTvcfP54)
  - **Descrição:** Vídeo explicativo sobre como implementar e utilizar `if`, `else` e `else if` em Java.

### 2.2 Laços de Repetição
- [Repetição com For e While em Java | DevMedia](https://www.devmedia.com.br/repeticao-com-for-e-while-em-java/25118)
  - **Descrição:** Artigo que explora a sintaxe e o uso de laços de repetição em Java.
- [Vídeo: Como Usar Foreach em Java | Oracle Learning](https://youtu.be/h2xI7JVSbJw)
  - **Descrição:** Tutorial em vídeo sobre a utilização do `foreach` em Java.

## 3. Tratamento de Exceções
### 3.1 Introdução ao Tratamento de Exceções
- [Tratamento de Exceções em Java | JavaPoint](https://www.javatpoint.com/exception-handling-in-java)
  - **Descrição:** Tutorial abrangente sobre o manejo de exceções em Java, abordando `try`, `catch`, `finally` e `throw`.
- [Vídeo: Exceções em Java | Tech With Tim](https://youtu.be/z2VnHH4Mcbg)
  - **Descrição:** Um vídeo introdutório que ensina como lidar com exceções em Java.

## 4. Bibliotecas e Ferramentas Java
### 4.1 Introdução ao Maven
- [Guia Completo do Maven | Baeldung](https://www.baeldung.com/maven)
  - **Descrição:** Uma visão geral de como usar o Maven para gerenciar dependências e construir projetos Java.
- [Vídeo: Maven para Iniciantes | Amigoscode](https://youtu.be/EqFmYo4z2SE)
  - **Descrição:** Vídeo explicativo sobre como configurar e usar o Maven em projetos Java.

### 4.2 Manipulação de JSON com GSON
- [Introdução ao GSON | Google](https://github.com/google/gson)
  - **Descrição:** Repositório oficial do GSON, uma biblioteca Java para converter objetos Java para JSON e vice-versa.
- [Artigo: Como Usar GSON em Java | Baeldung](https://www.baeldung.com/gson)
  - **Descrição:** Artigo que explica como usar a biblioteca GSON para manipular JSON em Java.

## 5. Programação Multithreaded
### 5.1 Introdução a Threads em Java
- [Java Threads: Guia Completo | JavaPoint](https://www.javatpoint.com/multithreading-in-java)
  - **Descrição:** Artigo que cobre conceitos fundamentais de multithreading em Java, com exemplos de código.
- [Vídeo: Programação Multithreaded em Java | Telusko](https://youtu.be/dQw4w9WgXcQ)
  - **Descrição:** Vídeo introdutório sobre como criar e gerenciar threads em Java.

## 6. Testes Unitários
### 6.1 JUnit para Iniciantes
- [Guia Básico de JUnit | Baeldung](https://www.baeldung.com/junit-5)
  - **Descrição:** Um guia para começar com testes unitários em Java usando o JUnit 5.
- [Vídeo: JUnit para Iniciantes | Amigoscode](https://youtu.be/cSb2NYfDA58)
  - **Descrição:** Tutorial em vídeo sobre como configurar e utilizar o JUnit em projetos Java.

## 7. Desenvolvimento Web com Java
### 7.1 Introdução ao Spring Framework
- [Spring Framework: Guia Completo | Spring.io](https://spring.io/guides)
  - **Descrição:** Documentação oficial do Spring Framework, essencial para o desenvolvimento web em Java.
- [Vídeo: Spring Framework para Iniciantes | Amigoscode](https://youtu.be/Bo0dAsFFsDQ)
  - **Descrição:** Um vídeo introdutório que explica os conceitos básicos do Spring Framework.

## 8. Outras Ferramentas e Conceitos Avançados
### 8.1 Domínio do Java Reflection
- [Java Reflection: Guia Completo | Baeldung](https://www.baeldung.com/java-reflection)
  - **Descrição:** Tutorial avançado que ensina como usar Reflection em Java para acessar e modificar campos e métodos privados.
- [Vídeo: Java Reflection | CodeAcademy](https://youtu.be/8JZiw_vHqpk)
  - **Descrição:** Vídeo que explora os fundamentos do uso de Reflection em Java.

### 8.2 Manipulação de Dados com Streams
- [Guia de Streams em Java | Baeldung](https://www.baeldung.com/java-8-streams)
  - **Descrição:** Tutorial detalhado sobre como usar Streams em Java para processar coleções de dados de forma eficiente.
- [Vídeo: Como Usar Streams em Java | Amigoscode](https://youtu.be/1OpAgZvYXLQ)
  - **Descrição:** Vídeo que explica como utilizar Streams em Java para operações como `filter`, `map` e `collect`.

## 9. Conclusão
### 9.1 Prática Contínua
- [LeetCode: Exercícios de Java](https://leetcode.com/problemset/all/)
  - **Descrição:** Plataforma para praticar algoritmos e estruturas de dados com suporte a Java.
- [HackerRank: Desafios de Programação](https://www.hackerrank.com/domains/tutorials/10-days-of-java)
  - **Descrição:** Desafios de programação em Java que cobrem desde os conceitos básicos até os mais avançados.

## 10. Repositórios Java no GitHub
### 10.1 Frameworks e Bibliotecas
- [**Spring Framework**](https://github.com/spring-projects/spring-framework)
  - **Descrição:** Framework poderoso para desenvolvimento de aplicações Java, com suporte para desenvolvimento web, gerenciamento de transações e muito mais.
- [**Apache Commons**](https://github.com/apache/commons-lang)
  - **Descrição:** Biblioteca com uma coleção de utilitários e extensões para trabalhar com Java, como manipulação de strings e coleções.
- [**JUnit 5**](https://github.com/junit-team/junit5)
  - **Descrição:** Framework de testes para Java, que oferece uma estrutura extensível para escrever testes unitários e de integração.

### 10.2 Ferramentas e Utilitários
- [**Lombok**](https://github.com/projectlombok/lombok)
  - **Descrição:** Biblioteca que ajuda a reduzir o código boilerplate em Java através da geração automática de métodos como getters e setters.
- [**Gson**](https://github.com/google/gson)
  - **Descrição:** Biblioteca do Google para a conversão entre objetos Java e JSON, simplificando o processamento de dados JSON.

### 10.3 APIs e Integrações
- [**OkHttp**](https://github.com/square/okhttp)
  - **Descrição:** Biblioteca para realizar requisições HTTP e gerenciar conexões de forma eficiente.
- [**Retrofit**](https://github.com/square/retrofit)
  - **Descrição:** Biblioteca que facilita a integração de APIs REST em aplicativos Java e Android.

### 10.4 Ferramentas de Desenvolvimento
- [**Apache Maven**](https://github.com/apache/maven)
  - **Descrição:** Ferramenta de gerenciamento de projetos e construção de aplicações Java, amplamente utilizada para controle de dependências e build automation.
- [**Gradle**](https://github.com/gradle/gradle)
  - **Descrição:** Sistema de automação de build que suporta Java e outras linguagens, oferecendo uma alternativa ao Maven.

### 10.5 Exemplos e Projetos
- [**Java Design Patterns**](https://github.com/iluwatar/java-design-patterns)
  - **Descrição:** Repositório que fornece exemplos de padrões de design em Java, com implementações práticas e explicações.
- [**Spring Boot**](https://github.com/spring-projects/spring-boot)
  - **Descrição:** Ferramenta para simplificar o desenvolvimento de aplicativos baseados em Spring, com uma configuração mínima e autoconfiguração.

### 10.6 Segurança e Criptografia
- [**Bouncy Castle**](https://github.com/bcgit/bc-java)
  - **Descrição:** Biblioteca de criptografia que oferece suporte para vários algoritmos e técnicas de criptografia em Java.
- [**Java Security**](https://github.com/java-security)
  - **Descrição:** Repositório com diversas bibliotecas e ferramentas para segurança e criptografia em Java.

### 10.7 Dados e Banco de Dados
- [**Hibernate ORM**](https://github.com/hibernate/hibernate-orm)
  - **Descrição:** Framework para mapeamento objeto-relacional (ORM) em Java, que facilita a persistência de dados em bancos de dados relacionais.
- [**MyBatis**](https://github.com/mybatis/mybatis-3)
  - **Descrição:** Framework para persistência de dados em Java que simplifica o uso de SQL, oferecendo uma abordagem alternativa ao Hibernate.

### 10.8 Desenvolvimento Web
- [**Apache Tomcat**](https://github.com/apache/tomcat)
  - **Descrição:** Servidor de aplicativos Java para rodar servlets e JSPs, amplamente utilizado em ambientes de produção.
- [**Vaadin**](https://github.com/vaadin/flow)
  - **Descrição:** Framework para desenvolvimento de interfaces de usuário modernas e interativas em Java.

### 10.9 Ferramentas de Teste
- [**AssertJ**](https://github.com/assertj/assertj-core)
  - **Descrição:** Biblioteca que fornece uma API fluente para realizar asserções em testes unitários de forma mais legível e expressiva.
- [**Mockito**](https://github.com/mockito/mockito)
  - **Descrição:** Framework para criar mocks e espiões em testes unitários, facilitando o teste de componentes isolados.

### 10.10 Outras Ferramentas
- [**JHipster**](https://github.com/jhipster/generator-jhipster)
  - **Descrição:** Gerador de código para criar aplicativos Java modernos com Spring Boot e Angular ou React.
- [**Quarkus**](https://github.com/quarkusio/quarkus)
  - **Descrição:** Framework Java para criar aplicações nativas em nuvem com desempenho otimizado e suporte a contêineres.

## 11. Vídeos sobre Java no YouTube
### 11.1 POO Básico
- [**Programação Orientada a Objetos (POO) - Aula 01**](https://www.youtube.com/watch?v=OkeB0EdW4SM)
  - **Descrição:** Introdução à POO e conceitos básicos, como classes e objetos.
- [**POO em Java - Aula 02: Herança**](https://www.youtube.com/watch?v=Y6Ti1RKi5pE)
  - **Descrição:** Explicação sobre herança em Java e criação de classes filhas.
- [**Construtores e Getters/Setters em Java**](https://www.youtube.com/watch?v=G8L_D0nCxJI)
  - **Descrição:** Como criar e utilizar construtores, getters e setters em Java.

### 11.2 Modificadores de Acesso
- [**Modificadores de Acesso em Java**](https://www.youtube.com/watch?v=I6Ic7_VXwDg)
  - **Descrição:** Detalhamento dos modificadores de acesso `private`, `protected`, e `public`.
- [**Aula 5 - Modificadores de Acesso e Encapsulamento**](https://www.youtube.com/watch?v=IVBL2wDbEfg)
  - **Descrição:** Como o encapsulamento e os modificadores de acesso funcionam em Java.

### 11.3 Métodos, Classes e Campos Estáticos
- [**Métodos e Campos Estáticos em Java**](https://www.youtube.com/watch?v=f1_MieDGvlA)
  - **Descrição:** Como declarar e utilizar métodos e campos estáticos em Java.
- [**Classes e Métodos Estáticos em Java**](https://www.youtube.com/watch?v=Y7m7owWUNw4)
  - **Descrição:** Explicação sobre a utilização de classes e métodos estáticos.

### 11.4 Estruturas de Controle
- [**Estruturas de Controle - If, Else e Switch**](https://www.youtube.com/watch?v=KktM1-SGm4M)
  - **Descrição:** Uso das estruturas de controle `if`, `else` e `switch` em Java.
- [**Loops em Java - For, While e Foreach**](https://www.youtube.com/watch?v=3eYf6s0jiP8)
  - **Descrição:** Explicação sobre os loops `for`, `while`, e `foreach` em Java.

### 11.5 Tipos Numéricos e Arrays
- [**Tipos Numéricos em Java**](https://www.youtube.com/watch?v=XvWm9L2wW3Q)
  - **Descrição:** Conceitos básicos sobre tipos numéricos como `int`, `float`, e `double`.
- [**Arrays em Java - Aula 1**](https://www.youtube.com/watch?v=Uy4lbCFFbLk)
  - **Descrição:** Introdução ao uso de arrays em Java.

### 11.6 Exceções
- [**Tratamento de Exceções em Java - Try, Catch e Finally**](https://www.youtube.com/watch?v=5ZW9td5y0Jg)
  - **Descrição:** Como usar `try`, `catch` e `finally` para tratar exceções em Java.
- [**Como Lançar Exceções em Java - Throw e Throws**](https://www.youtube.com/watch?v=1x0V4J99NiM)
  - **Descrição:** Explicação sobre o uso de `throw` e `throws` para lançar exceções.

### 11.7 Interfaces e POO Avançado
- [**Interfaces em Java - Aula 1**](https://www.youtube.com/watch?v=wJ1KpR9dp1A)
  - **Descrição:** Introdução às interfaces em Java e suas utilidades.
- [**Classes Abstratas e Métodos Abstratos**](https://www.youtube.com/watch?v=sZ2_syoWZkI)
  - **Descrição:** Conceitos sobre classes abstratas e métodos abstratos.

### 11.8 Anotações e Código Limpo
- [**Introdução às Anotações em Java**](https://www.youtube.com/watch?v=B8MmTlkeO5s)
  - **Descrição:** O que são anotações em Java e como utilizá-las.
- [**Código Limpo em Java - Boas Práticas**](https://www.youtube.com/watch?v=eSmZY8q5LlM)
  - **Descrição:** Práticas recomendadas para escrever código limpo e organizado em Java.

### 11.9 Criar Exceções e Reflections
- [**Como Criar Exceções Personalizadas em Java**](https://www.youtube.com/watch?v=1T0p8jDN2Eo)
  - **Descrição:** Passos para criar suas próprias exceções em Java.
- [**Introdução ao Java Reflection**](https://www.youtube.com/watch?v=WgXgN5Bqg0Y)
  - **Descrição:** Conceitos básicos sobre a API de Reflection em Java.

### 11.10 Banco de Dados e JSON
- [**Hibernate ORM - Introdução e Configuração**](https://www.youtube.com/watch?v=69G9oE5Ig4k)
  - **Descrição:** Como configurar e usar Hibernate ORM para persistência de dados em Java.
- [**JSON em Java com Gson - Aula 1**](https://www.youtube.com/watch?v=sDW1q6ZZlFY)
  - **Descrição:** Utilização da biblioteca Gson para trabalhar com JSON em Java.

### 11.11 Desenvolvimento Web e Frameworks
- [**Introdução ao Spring Boot**](https://www.youtube.com/watch?v=ylTzvERjTXQ)
  - **Descrição:** Guia inicial para começar a desenvolver com Spring Boot.
- [**Construindo APIs REST com Spring Boot**](https://www.youtube.com/watch?v=wICaeOrqAEs)
  - **Descrição:** Como criar APIs RESTful utilizando Spring Boot.

### 11.12 Segurança e Criptografia
- [**Criptografia em Java com Bouncy Castle**](https://www.youtube.com/watch?v=5b2G7p1yP8g)
  - **Descrição:** Utilizando a biblioteca Bouncy Castle para implementar criptografia em Java.
- [**Segurança em Java - Aula 1**](https://www.youtube.com/watch?v=cXhLnbObnS8)
  - **Descrição:** Conceitos básicos sobre segurança e criptografia em Java.

### 11.13 Desenvolvimento com Git e Maven
- [**Introdução ao Git e GitHub para Java**](https://www.youtube.com/watch?v=7G5jZmNiw_I)
  - **Descrição:** Fundamentos do uso de Git e GitHub para gerenciar projetos Java.
- [**Gerenciamento de Dependências com Maven**](https://www.youtube.com/watch?v=LMXZbVErCzI)
  - **Descrição:** Como usar Maven para gerenciar dependências e construir projetos Java.

### 11.14 Multi-threading e Concurrency
- [**Introdução à Concurrency em Java**](https://www.youtube.com/watch?v=0qTkxq2fL68)
  - **Descrição:** Conceitos básicos sobre multi-threading e concorrência em Java.
- [**Java Concurrency - Threads e Runnable**](https://www.youtube.com/watch?v=vDnvQK7Rr1w)
  - **Descrição:** Como usar `Thread` e `Runnable` para criar e gerenciar threads.

### 11.15 Ferramentas de Desenvolvimento
- [**Introdução ao Gradle para Java**](https://www.youtube.com/watch?v=ppG1Xh9t1U8)
  - **Descrição:** Configuração e uso básico do Gradle para projetos Java.
- [**Ferramentas e IDEs para Desenvolvimento Java**](https://www.youtube.com/watch?v=KnYJFn1n6dk)
  - **Descrição:** Visão geral das principais ferramentas e IDEs para desenvolvimento Java.

### 11.16 Outras Ferramentas e Técnicas
- [**Como Usar o UUID em Java**](https://www.youtube.com/watch?v=qVtFiTq7MiQ)
  - **Descrição:** Gerando e utilizando UUIDs em Java.
- [**Introdução ao Java Optional**](https://www.youtube.com/watch?v=8FTYF_KSBxU)
  - **Descrição:** Utilização da classe `Optional` para evitar `null` em Java.

### 11.17 Desenvolvimento de Jogos
- [**Desenvolvimento de Jogos em Java com LibGDX**](https://www.youtube.com/watch?v=Y6t-ANzJ2f8)
  - **Descrição:** Como usar a biblioteca LibGDX para criar jogos em Java.

### 11.18 Desenvolvimento de Aplicações Android
- [**Introdução ao Desenvolvimento Android com Java**](https://www.youtube.com/watch?v=vg71w5L8Q1I)
  - **Descrição:** Conceitos básicos para começar a desenvolver aplicações Android usando Java.

### 11.19 Métodos Genéricos e Coleções
- [**Métodos Genéricos em Java - Aula 1**](https://www.youtube.com/watch?v=q9mM8ejME0Y)
  - **Descrição:** Introdução ao uso de métodos genéricos em Java.
- [**Coleções em Java - List, Set e Map**](https://www.youtube.com/watch?v=x5G9Kzy6A44)
  - **Descrição:** Utilização das principais coleções em Java, como `List`, `Set`, e `Map`.

### 11.20 Refatoração e Boas Práticas
- [**Refatoração de Código em Java**](https://www.youtube.com/watch?v=aeYFeVfxMsc)
  - **Descrição:** Técnicas para refatorar código Java e melhorar sua manutenção e legibilidade.
- [**Boas Práticas de Programação em Java**](https://www.youtube.com/watch?v=61ExcmynMlY)
  - **Descrição:** Dicas e práticas recomendadas para escrever código Java de alta qualidade.
