# PriseDeNote

## sommaire

1. Next.js
2. Shadcn
3. Zod
4. MySQL
5. Prisma
6. Remote Gitea Github
7. Architecture de code
8. Criptage et Hachage
9. D3.js
10. Testeur API
---
### 01 Next.js

#### Comparaison Next.js et angular

Next.js est plus leger, facilement déployable, package disponible.
Angulard gerre mieux les moyens et grand projet

#### instalation de Next.js

1. dans le dossier a créée```npx create-next-app@latest```
2. réponse a choisir :
  - ✔ What is your project named? … graphql
  - ✔ Would you like to use TypeScript? … No / [Yes]
  - ✔ Would you like to use ESLint? … No / [Yes]
  - ✔ Would you like to use Tailwind CSS? … No / [Yes]
  - ✔ Would you like your code inside a `src/` directory? … No / [Yes]
  - ✔ Would you like to use App Router? (recommended) … No / [Yes]
  - ✔ Would you like to use Turbopack for `next dev`? … No / [Yes]
  - ✔ Would you like to customize the import alias (`@/*` by default)? … [No] / Yes

#### lancer le serveur Next.js
```npm run dev```

#### info pratique

Les nom des dossier dans app et qui on un fichier page.tsx, se retrouveron comme nom de la page HTML

mettre les crochet au nom de dossier permet de modifier la regle plus haut

---
### 02 Shadcn

#### instalation de Shadcn pour Next.js format npm:

1. ```npx shadcn@latest init```
2. base color : neutral
3. use --force
---
### 03 Zod

#### instalation de Zod

```npm install zod@canary```

pour vérifier si sa a bien fonctioner :

1. Crée un fichier zod.ts dans app/lib
2. copier dans le fichier :
  ```
import { z } from "zod/v4";
 
const User = z.object({
  name: z.string(),
});
```
3. si l'import ne marque pas d'erreur alors tout est bon.
---
### 04 MySQL (à vérifier)

#### instalation de MySQL

``` sudo apt install mysql-server```

#### créée la base de donée

1. (entrée sur MySQL) ```sudo mysql```
2. (créée la base de donée) ```CREATE DATABASE dev;```
3. (pour sortir) ```èxit```
   
4. (dans le fichier .env) ```DATABASE_URL="mysql://root:root@localhost:3306/dev"
---
### 05 Prisma (à vérifier)

#### instalation de Prisma

```npx prisma@latest init --db```

pour vérifier :
dans le fichier schema.prisma

```
model Device {
  id   Int                   @id @default(autoincrement())
  name String
}
```

#### migrée prisma

```npx prisma migrate dev```

---
### 06 Remote Gitea Github

1. clonée normalement le fichier sur Gitea
2. aller sur Github
3. créée le répo
4. si besoin crée un token classic
   1. aller dans Setting
   2. Developer Settings
   3. Tokens (classic)
   4. Generate new Token
   5. Generate new Token (classic)
   6. copier le mot de passe (token) quelle que par
6. dans le terminal ```git remote add github (lien du repo)```
7. vérifier avec : ``` git remote -v```

pour push sur github: ```git push github```

---
### 07 Architechture de code

#### A Modèle-Vue-Contrôleur (MVC)

- un Modèle (model) contien les donée à afficher
- une Vue (view) contient la présentation de l'interface graphique
- un Contrôleur (controller) contien la logic concernant les actions effectuées par l'utilisateur

##### Varient

- Model-View-Presenter (MVP)
  Dans le patron MVP, le contrôleur est remplacé par une présentation. La présentation est créée par la vue  et lui est associée par une interface. Les actions utilisateur déclenchent des événements sur la vue, et ces événements sont propagés à la présentation en utilisant l'interface
- Model-View-View-Model (MVVM)
  Dans le patron MVVM il y a une communication bidirectionnelle entre la vue et le modèle, les actions de l'utilisateur entraînent des modifications des données du modèle

##### Lien wikipedia
- [MVC](https://fr.wikipedia.org/wiki/Mod%C3%A8le-vue-contr%C3%B4leur)
- [MVP](https://fr.wikipedia.org/wiki/Mod%C3%A8le-vue-pr%C3%A9sentation)
- [MVVM](https://fr.wikipedia.org/wiki/Mod%C3%A8le-vue-vue_mod%C3%A8le)

#### B Architecture en couches (Layered Architecture)

#### C Architecture microservice

L'architecture de microservice désigne un style d'architecture utilisé dans le developement d'aplication.
Elle permet de décomposer une application volumineuse en composants indépendants, chaque élément ayant ses propres responsabilités. Pour diffuser la requête d'un utilisateur unique, une application basée sur des microservices peut appeler plusieurs microservices internes pour composer sa réponse.

---
### 08 Criptage et Hachage

#### A Bcrypt

- Définition :
Bcrypt est un algorithme de hachage basé sur le chiffrement Blowfish. Il est conçu pour être lent afin de rendre plus difficile les attaques par force brute.
- Salage :
Bcrypt intègre un mécanisme de salage, ce qui signifie qu'il ajoute des données aléatoires aux mots de passe avant de les hacher, rendant chaque hachage unique même pour des mots de passe identiques.
- Coût de calcul :
Il permet de définir un coût de calcul, ce qui signifie que vous pouvez ajuster la difficulté du hachage en fonction de la puissance de calcul disponible, rendant l'algorithme plus résistant aux attaques au fil du temps.
- Utilisation :
Scrypt est utilisé dans des contextes similaires à ceux de bcrypt, mais il est particulièrement populaire dans les systèmes où la résistance aux attaques par matériel est une priorité.

##### Lien wikipedia
[Bcript](https://fr.wikipedia.org/wiki/Bcrypt)

#### B Scrypt

- Définition :
Scrypt est également un algorithme de hachage conçu pour le stockage sécurisé des mots de passe, mais il a été spécifiquement conçu pour être résistant aux attaques par matériel (ASIC).
- Salage :
Comme bcrypt, scrypt utilise un salage pour garantir que les hachages sont uniques.
- Coût de mémoire : 
Scrypt nécessite une quantité significative de mémoire pour effectuer le hachage, ce qui le rend plus coûteux en ressources pour les attaquants qui tentent d'utiliser du matériel spécialisé pour effectuer des attaques par force brute.
- Utilisation :
Scrypt est utilisé dans des contextes similaires à ceux de bcrypt, mais il est particulièrement populaire dans les systèmes où la résistance aux attaques par matériel est une priorité.

##### Lien wikipedia
[Scrypt](https://fr.wikipedia.org/wiki/Scrypt)

---
### 09 D3.js

instalation:
npm install d3

---
### 10 Testeur d'API

#### Postman

instalation:
Dans le centre d'aplication de linux

utilisable aussi sur certain navigateur web

##### Lien wikipédia
[Postman](https://fr.wikipedia.org/wiki/Postman_(logiciel))

#### Insomnia

à la diférence de Postman, Insomnia est un projet open-source et colaboratif, il est spécialiser pour les API RESTful et GraphQL

instalation:
Dans le centre d'aplication de linux
