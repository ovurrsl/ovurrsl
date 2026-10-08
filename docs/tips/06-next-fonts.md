# Next.js Fonts

Load fonts with `next/font` instead of a `<link>` to Google Fonts.

```tsx
// app/layout.tsx
import { Inter } from 'next/font/google'

const inter = Inter({ subsets: ['latin'], display: 'swap' })

export default function RootLayout({ children }: { children: React.ReactNode }) {
  return (
    <html lang="en" className={inter.className}>
      <body>{children}</body>
    </html>
  )
}
```

**Why:** fonts are downloaded at build time and served from your own domain, so there's no extra request to Google, and fallback metrics are adjusted to avoid layout shift.
