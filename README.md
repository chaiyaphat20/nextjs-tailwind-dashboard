# 1.shadcn ui

```
npx create-next-app@latest
```

# 2.tailwind debug screen
https://github.com/jorenvanhee/tailwindcss-debug-screens


## 2.1 install lib
```
npm install tailwindcss-debug-screens --save-dev
```

## 2.2 config at tailwind.config.ts
```
import type { Config } from "tailwindcss"

const config = {
  ...
  theme: {
    ...
  },
  plugins: [
    require("tailwindcss-animate"),
    require("tailwindcss-debug-screens")
  ],
} satisfies Config

export default config
```

## 2.3 config in main layout.tsx

```
export default function RootLayout({
  children,
}: Readonly<{
  children: React.ReactNode;
}>) {
  return (
    <html lang="en">
      <body className={cn(inter.className,{'debug-screens':process.env.NODE_ENV === "development"})}>{children}</body>
    </html>
  );
}
```

## result
![alt text](/readme/image.png)

# 3