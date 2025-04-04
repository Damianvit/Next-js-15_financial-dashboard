# 03-optimizing-fonts-and-images

## Setup Section

-   Feel free to skip this setup section if you have been following from previous sections, otherwise, follow these procedures to setup your development environment for this chapter.

**Install pnpm globaly**

```sh
npm install -g pnpm
```

**Create a Next.js app**

```sh
npx create-next-app@latest financial-dashboard --example "https://github.com/Damianvit/Next-js-15_financial-dashboard/tree/main/03-optimizing-fonts-and-images/starter-template" --use-pnpm
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

**Edit the /app/layout.tsx**

```tsx
import '@/app/ui/global.css';
import { inter } from '@/app/ui/fonts';
 
export default function RootLayout({
  children,
}: {
  children: React.ReactNode;
}) {
  return (
    <html lang="en">
      <body className={`${inter.className} antialiased`}>{children}</body>
    </html>
  );
}

```

