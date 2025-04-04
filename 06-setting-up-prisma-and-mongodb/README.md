# 06-setting-up-prisma-and-mongodb

## Setup Section

-   Feel free to skip this setup section if you have been following from previous sections, otherwise, follow these procedures to setup your development environment for this chapter.

**Install pnpm globaly**

```sh
npm install -g pnpm
```

**Create a Next.js app**

```sh
npx create-next-app@latest financial-dashboard --example "https://github.com/Damianvit/Next-js-15_financial-dashboard/tree/main/06-setting-up-prisma-and-mongodb/starter-template" --use-pnpm
```

**install project packages with**

```sh
pnpm i
```

**Start development server**

```sh
pnpm dev
```

**🔥 Run the development server**

[http://localhost:3000](http://localhost:3000)

## Main Section

-   From this chapter onwards the tutorial flow will become more different form the one on Next Learn website. The major difference will sterm from our use of Prisma and Mongodb.
-   The chapter's README.md file will be of great help.

**Create a Vercel account**

visit [vercel signup page](https://vercel.com/signup)

**Install Prisma**

```sh
pnpm add prisma @prisma/client
```

**Initialize Prisma**

```sh
pnpx prisma init
```

-   This creates a prisma/schema.prisma file and a .env file if it doesn't exist yet

**Modify prisma/schema.prisma file **

-   Open ./prisma/schema.prisma and modify the file

```prisma

generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "mongodb"
  url      = env("DATABASE_URL")
}

model User {
  id       String @id @default(auto()) @map("_id") @db.ObjectId
  name     String
  email    String @unique
  password String
}

model Invoice {
  id         String @id @default(auto()) @map("_id") @db.ObjectId
  customerId String @db.ObjectId
  amount     Int
  status     String
  date       DateTime
  customer    Customer @relation(fields: [customerId], references: [id])

}

model Customer {
  id       String @id @default(auto()) @map("_id") @db.ObjectId
  name     String
  email    String @unique
  imageUrl String
  invoices Invoice[] // Relation field
}

model Revenue {
  id      String @id @default(auto()) @map("_id") @db.ObjectId
  month   String @unique
  revenue Int
}

```

**Generate Prisma Client**

```sh
pnpx prisma generate
```

**Push changes to mongodb atlas**

```sh
pnpx prisma db push
```

```sh
pnpx prisma studio
```

