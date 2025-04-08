# 04-structuring-layouts-and-pages

## Setup Section

-   Feel free to skip this setup section if you have been following from previous sections, otherwise, follow these procedures to setup your development environment for this chapter.

**Install pnpm globaly**

```sh
npm install -g pnpm
```

**Create a Next.js app**

```sh
npx create-next-app@latest financial-dashboard --example "https://github.com/Damianvit/Next-js-15_financial-dashboard/tree/main/04-structuring-layouts-and-pages/starter-template" --use-pnpm
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

**/app/dashboard/layout.tsx**
```tsx
import SideNav from '@/app/ui/dashboard/sidenav';
 
export default function Layout({ children }: { children: React.ReactNode }) {
  return (
    <div className="flex h-screen flex-col md:flex-row md:overflow-hidden">
      <div className="w-full flex-none md:w-64">
        <SideNav />
      </div>
      <div className="flex-grow p-6 md:overflow-y-auto md:p-12">{children}</div>
    </div>
  );
}
```
