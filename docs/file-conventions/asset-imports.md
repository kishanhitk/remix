---
title: Asset Imports
toc: false
---

# Asset URL Imports

Any files inside the `app` folder can be imported into your modules. Remix will:

1. Copy the file to your browser build directory
2. Fingerprint the file for long-term caching
3. Return the public URL to your module to be used while rendering

It's most common for stylesheets, but can used for anything.

```tsx filename=app/routes/root.tsx
import banner from "./images/banner.jpg";
import styles from "./styles/app.css";

export const links = () => {
  return [{ rel: "stylesheet", href: styles }];
};

export default function Page() {
  return (
    <div>
      <h1>Some Page</h1>
      <img src={banner} />
    </div>
  );
}
```
