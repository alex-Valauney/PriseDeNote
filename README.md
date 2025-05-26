# PriseDeNote

## sommaire

1. Next.js
2. Shadcn
3. Zod
4. MySQL
5. Prisma
6. Remote Gitea Github

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

### 02 Shadcn

#### instalation de Shadcn pour Next.js format npm:

1. ```npx shadcn@latest init```
2. base color : neutral
3. use --force

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
3. si l'import ne marque pas d'erreur alors tout est bon

### 04 MySQL (à vérifier)

#### instalation de MySQL

``` sudo apt install mysql-server```

#### créée la base de donée

1. (entrée sur MySQL) ```sudo mysql```
2. (créée la base de donée) ```CREATE DATABASE dev;```
3. (pour sortir) ```èxit```
   
4. (dans le fichier .env) ```DATABASE_URL="mysql://root:root@localhost:3306/dev"

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

### 06 Remote Gitea Github
