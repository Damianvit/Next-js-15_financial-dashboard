# 02-css-styling-best-practices

## Setup Section

-   Feel free to skip this setup section if you have been following from previous sections, otherwise, follow these procedures to setup your development environment for this chapter.

**Install pnpm globaly**

```sh
npm install -g pnpm
```

**Create a Next.js app**

```sh
npx create-next-app@latest financial-dashboard --example "https://github.com/Damianvit/Next-js-15_financial-dashboard/tree/main/02-css-styling-best-practices/starter-template" --use-pnpm
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
import "@/app/ui/global.css"; // 🔥 Add this

export default function RootLayout({
    children,
}: {
    children: React.ReactNode;
}) {
    return (
        <html lang="en">
            <body>{children}</body>
        </html>
    );
}
```

### [Tailwind class](https://www.tailwindcss.com)

**Paste it above the p element in /app/page.tsx**

```tsx
<div className="relative w-0 h-0 border-l-[15px] border-r-[15px] border-b-[26px] border-l-transparent border-r-transparent border-b-black" />
```

### [CSS Modules](https://nextjs.org/docs/app/getting-started/css#css-modules)

**/app/ui/home.module.css**

```css
.shape {
    height: 0;
    width: 0;
    border-bottom: 30px solid black;
    border-left: 20px solid transparent;
    border-right: 20px solid transparent;
}
```

**/app/page.tsx**

```tsx
import AcmeLogo from '@/app/ui/acme-logo';
import { ArrowRightIcon } from '@heroicons/react/24/outline';
import Link from 'next/link';
import styles from '@/app/ui/home.module.css'; // <<<<< Add this >>>>>

export default function Page() {
  return (
    <main className="flex min-h-screen flex-col p-6">
  {/* Add this >>>>>>>   */}
       <div className={styles.shape} />
  {/* <<<<<<<<<<<<<   */}
    // ...
  )
}
```
