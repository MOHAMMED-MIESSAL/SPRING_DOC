# SPRING_DOC

## C'est quoi Spring ?
Spring est un framework Java open-source très populaire, principalement utilisé pour faciliter le développement d'applications d'entreprise .  

## Architecture de Spring
Spring est organisé en plusieurs modules au sein d'un conteneur léger et flexible, connu sous le nom de conteneur Spring IoC .  
Le conteneur IoC est au cœur de l'architecture Spring et permet la gestion des objets en injectant leurs dépendances de manière automatisée.  
L'architecture de Spring est composée de quatre couches principales :  

```Core Container``` : pour la gestion de la configuration de base  
```Data Access/Integration``` : pour les opérations de gestion des données  
```Web``` : pour la création d'applications web  
```AOP, Aspects, Instrumentation, et Messaging``` : pour les fonctionnalités avancées telles que la programmation orientée aspects (AOP) et la gestion des messages  
```Test``` : pour les fonctionnalités de test intégrées  

##  Rôle des Modules de Spring
Voici les principaux modules de chaque couche et leurs rôles :  

### A. Core Container :
1.```Spring Core``` : Contient les éléments de base de Spring, y compris le conteneur IoC. Il gère la configuration et l'injection de dépendances, ce qui permet aux développeurs de définir les beans (objets gérés par Spring) et leurs relations.  

2.```Spring Beans``` : Ce module est essentiel pour définir, configurer et gérer le cycle de vie des beans dans le conteneur IoC. C'est ici que l’injection de dépendances est réellement implémentée.  

3.```Spring Context``` : Basé sur les modules Core et Beans, le module Context offre un accès à des fonctionnalités spécifiques à l'entreprise comme la gestion des ressources, l'internationalisation (i18n), et l'enregistrement d'événements. Il est souvent utilisé pour fournir un environnement applicatif plus complet.  

4.```Spring Expression Language (SpEL)``` : Un langage d'expression puissant permettant de manipuler et d’évaluer des expressions au sein de l’application. Il peut être utilisé pour accéder aux propriétés des beans, effectuer des opérations logiques et arithmétiques, et bien plus.  

### B. Data Access/Integration (Accès aux Données et Intégration)
1.```Spring JDBC``` : Simplifie l'accès à la base de données en réduisant la complexité des opérations JDBC traditionnelles. Spring JDBC gère les ressources automatiquement, ce qui réduit le code boilerplate.  

2.```ORM (Object-Relational Mapping)``` : Ce module intègre des frameworks ORM comme Hibernate, JPA, et MyBatis. Il simplifie la gestion de la persistance des objets en les mappant aux tables d'une base de données.  

3.```Spring Transaction``` : Fournit une gestion de transactions unifiée, permettant d’assurer la cohérence des opérations critiques. Ce module permet de gérer les transactions de manière déclarative ou programmatique.  

4.```Spring Data``` : Facilite la gestion des données, en offrant des abstractions pour les accès à divers types de bases de données, y compris les bases de données NoSQL, comme MongoDB, et les bases de données relationnelles.  

### C. Web (Couche Web)
1.```Spring Web``` : Ce module est la base pour créer des applications web, en utilisant le modèle MVC (Model-View-Controller). Il gère les requêtes HTTP, les réponses, et permet de développer des applications Web en se concentrant sur la logique métier.

2.```Spring WebMVC``` : Implémente le modèle MVC en ajoutant des fonctionnalités comme les contrôleurs, la gestion des vues et des modèles, et l'internationalisation, ce qui permet de développer des applications web de manière modulaire.

3.```Spring WebFlux``` : Permet de créer des applications réactives basées sur le modèle non-bloquant et asynchrone. Idéal pour les applications nécessitant un grand nombre de requêtes simultanées, il utilise le modèle de programmation réactive.

### D. AOP, Aspects, Instrumentation et Messaging (Programmation Orientée Aspects, Instrumentation et Messagerie)
1.```Spring AOP``` : Fournit des capacités de programmation orientée aspects, permettant d'ajouter des comportements transversaux comme la gestion de la sécurité, les logs, et les transactions. Il est couramment utilisé pour gérer des préoccupations transversales dans l’application.

2.```Spring Aspects``` : Basé sur Spring AOP, ce module permet d'intégrer des aspects de manière plus avancée, en offrant une syntaxe et des fonctionnalités plus flexibles pour la gestion des aspects.

3.```Spring Instrumentation``` : Fournit une assistance pour la gestion des outils et de l'instrumentation dans un environnement applicatif, en particulier pour les applications Java EE.

4.```Spring Messaging``` : Supporte l'intégration avec les systèmes de messagerie, y compris JMS (Java Message Service), pour les applications qui nécessitent une communication asynchrone entre les composants.

### E. Test (Couche de Test)
1.```Spring Test``` : Facilite le test des applications Spring en fournissant des classes et des annotations pour configurer l'application dans un environnement de test. Il permet d’effectuer des tests unitaires, d’intégration et de mock dans un contexte Spring.  

## C'est quoi IoC & DI ?

### 1. Qu'est-ce que le principe de l'Inversion of Control (IoC) ?
L'Inversion of Control (IoC) est un principe où le contrôle de la création et de la gestion des objets est inversé, c'est-à-dire transféré du programmeur vers un framework ou un conteneur.  
Au lieu de créer manuellement des objets et de les assembler dans le code, un conteneur IoC (comme celui de Spring) est chargé de créer et de gérer les objets nécessaires.  

Dans une application traditionnelle, le code de l’application décide quand et comment les objets sont créés et leurs dépendances sont gérées. Avec l’IoC, c’est le conteneur qui prend cette responsabilité, ce qui permet un code plus modulaire, plus flexible, et plus facile à tester.  

```En résumé :```

Avec IoC, le programme ne contrôle plus directement la gestion des objets et de leurs dépendances ; c’est le framework (Spring, par exemple) qui s’en charge.  


### 2. Qu'est-ce que l'Injection de Dépendances (DI) ?
L'injection de dépendances (DI) est une technique pour mettre en œuvre l'IoC. C'est le processus par lequel un objet reçoit (ou "injecte") ses dépendances d'un conteneur externe plutôt que de les instancier lui-même. En d’autres termes, les objets nécessaires à l’exécution d’un autre objet lui sont fournis par un conteneur ou un framework.  

Les dépendances peuvent être injectées de différentes manières :

```Injection par constructeur``` : Les dépendances sont fournies via le constructeur de l'objet.  
```Injection par setter``` : Les dépendances sont injectées via des méthodes setter.  
```Injection par field``` : Les dépendances sont injectées directement dans les attributs de la classe.  

### @Autowired :
@Autowired est utilisée dans le framework Spring pour effectuer l'injection de dépendances de manière automatique .  
En ajoutant cette annotation à un constructeur, un champ, ou un setter, Spring injecte automatiquement l’instance appropriée dans la dépendance, en gérant lui-même le cycle de vie des objets.  

## Fonctionnement de @Autowired
Lorsqu'une classe contient une dépendance annotée avec @Autowired, Spring va rechercher une instance correspondante dans le contexte IoC (Inversion of Control) et l'injecter. Voici les principaux points à connaître :  

```Détection des dépendances``` : Spring scanne les classes et détecte les dépendances marquées avec @Autowired.  
```Injection par type``` : Par défaut, @Autowired fonctionne par type. Spring cherche dans le contexte une instance du type spécifié pour l’injecter.  
```Injection dans trois emplacements``` :  
```Constructeur``` : Injection au niveau du constructeur pour assurer que les dépendances sont initialisées dès la création de l'objet.  
```Setter``` : Injection via des méthodes setter pour initier les dépendances après la création de l’objet.
```Champ``` : Injection directement dans les attributs, aussi appelée field injection.


## Quelle est la difference entre couplage fort et couplage faible ?

Le couplage est une mesure de la dépendance entre deux classes ou modules dans un programme. Il existe deux principaux types  :  

```Couplage fort (tight coupling)``` : Lorsque deux classes sont fortement dépendantes l'une de l'autre, elles sont dites "fortement couplées". Cela signifie qu’une modification dans une classe impactera directement l’autre classe. Le couplage fort réduit la flexibilité, rend les classes moins réutilisables, et complique les tests unitaires.  

```Couplage faible (loose coupling)``` : Lorsque deux classes ont des dépendances minimales entre elles, elles sont faiblement couplées. Cela permet une plus grande flexibilité et maintenabilité, car chaque classe peut évoluer indépendamment. Les tests unitaires sont aussi facilités.  

```Example de Couplage Fort:```
Supposons que nous avons deux classes, Service et Repository. Dans le cas d'un couplage fort, Service crée une instance de Repository directement dans son code.  
```
public class Repository {
    public void getData() {
        System.out.println("Fetching data...");
    }
}

public class Service {
    private Repository repository;

    public Service() {
        this.repository = new Repository(); // Couplage fort : Service dépend directement de Repository
    }

    public void doSomething() {
        repository.getData();
    }
}

```

```Example de Couplage Faible:```
Supposons que nous avons deux classes, Service et Repository. Dans le cas d'un couplage fort, Service crée une instance de Repository directement dans son code.   

```
public class Repository {
    public void getData() {
        System.out.println("Fetching data...");
    }
}

public class Service {
    private Repository repository;

    public Service() {
        this.repository = new Repository(); // Couplage fort : Service dépend directement de Repository
    }

    public void doSomething() {
        repository.getData();
    }
}

```

## Spring Beans 

### 1. C'est quoi Spring Beans ?
Dans le framework Spring, un Bean est un objet qui est instancié, configuré et géré par le conteneur Spring IoC (ApplicationContext). Les beans sont les éléments de base dans Spring, car ils représentent les objets qui constituent l'application et sont gérés par Spring pour permettre une injection de dépendances et d'autres fonctionnalités.  

### 2. Cycle de Vie d'un Bean
Le cycle de vie d'un bean inclut plusieurs étapes, gérées automatiquement par le conteneur Spring :  

1.```Instanciation``` : Le conteneur crée une instance de la classe (bean).  
2.```Injection des dépendances``` : Spring injecte les dépendances définies dans la classe via le constructeur, les setters ou les annotations comme @Autowired.  
3.```Initialisation``` : Spring appelle une méthode d'initialisation, si elle est définie (par exemple @PostConstruct ou une méthode configurée par XML).  
4.```Utilisation``` : L'application utilise le bean.  
5.```Destruction``` : Spring appelle une méthode de destruction, si elle est définie (par exemple @PreDestroy), avant de supprimer le bean du conteneur.  

### 3. Définir un Bean dans Spring
Il existe plusieurs manières de définir des beans dans Spring :  
A.```Avec l'annotation @Component```: La façon la plus courante est d'annoter une classe avec @Component, ce qui permet à Spring de détecter automatiquement cette classe comme un bean lors du scan de classes.  
```
import org.springframework.stereotype.Component;

@Component
public class Service {
    public void serve() {
        System.out.println("Service is serving...");
    }
}

```
B.```Avec l'annotation @Bean dans une classe de configuration```: @Bean est utilisée pour déclarer un bean au sein d'une classe de configuration annotée avec @Configuration. Cette approche est souvent utilisée pour des configurations plus précises.  
```
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

@Configuration
public class AppConfig {

    @Bean
    public Service service() {
        return new Service();
    }
}

```

### 4. Portée des Beans (Scopes)
Le scope d'un bean détermine son cycle de vie dans le conteneur Spring. Les scopes les plus utilisés sont :  

```Singleton (par défaut)``` : Un seul et unique instance de bean est créé dans le conteneur et partagé partout dans l'application.  
```Prototype``` : Une nouvelle instance de bean est créée chaque fois que le bean est demandé.  
```Request``` : Une instance de bean est créée pour chaque requête HTTP (dans une application web).  
```Session``` : Une instance de bean est créée pour chaque session utilisateur.  

```Example :```

```
import org.springframework.context.annotation.Scope;
import org.springframework.stereotype.Component;

@Component
@Scope("prototype")
public class PrototypeService {
    // Code de la classe
}


```
