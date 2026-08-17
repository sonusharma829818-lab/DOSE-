# LTX Studio — Desktop App

Ye ek **real Windows desktop app** hai (Electron-based). White background + black text theme, custom title bar (real minimize/maximize/close), aur LTX-2.3 Pro API se video generate karta hai.

## Chalane ke steps (aapke Windows PC par):

1. **Node.js install karo** (agar nahi hai): https://nodejs.org (LTS version)

2. Is folder ko kisi jagah rakho, phir Command Prompt / PowerShell yahin se kholo (folder ke andar), aur ye chalao:

   ```
   npm install
   ```

3. App ko test karne ke liye (bina .exe banaye, seedha chalane ke liye):

   ```
   npm start
   ```

4. **Real installable .exe banane ke liye:**

   ```
   npm run build:win
   ```

   Ye complete hone ke baad `dist` folder ke andar `LTX Studio Setup 1.0.0.exe` mil jayega — usko double-click karke normal Windows app ki tarah install kar sakte ho (Start Menu + Desktop shortcut ke saath).

## Files

- `main.js` — Electron main process (window banata hai, real minimize/maximize/close handle karta hai)
- `preload.js` — Secure bridge jo HTML ko window control karne deta hai
- `index.html` — Poori UI (title bar, app bar, prompt panel, preview stage)
- `package.json` — Dependencies + build config (electron-builder)

## Note

- Icon abhi default Electron icon use ho raha hai. Apna icon lagane ke liye `build/icon.ico` (256x256) daal do — `package.json` me already reference hai.
- Agar API call me CORS/401 jaisa error aaye, wo LTX ke server-side restriction ka hissa hai — key check karo aur agar zarurat pade to ek chhota local proxy add karna padega.
