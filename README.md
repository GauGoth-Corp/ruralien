<img src="src/assets/hero.png" alt="RuraLien logo" width="64" height="64" />

# RuraLien

Module de communication hors-réseau pour les zones rurales, développé par **Galaxaris**.
Couplé au boîtier LoRa (ESP32), il permet de créer un réseau local maillé pour communiquer sans dépendre d'Internet (zones blanches, montagne, festivals, camps scouts, situations d'urgence).

> Ce projet utilise **Vue 3 + TypeScript + Vite + Tailwind CSS v4** pour l'interface, et **Capacitor** pour le déploiement sur Android (et iOS/Web/Desktop).
>
> 📖 Pour la documentation technique complète (setup Windows détaillé, permissions Android, Deep Links, build Play Store, déploiement Web, iOS, Electron), consultez **[SETUP.md](./SETUP.md)**.

---

## Démarrage rapide (après `git clone`)

Le projet Vue, Tailwind et le dossier natif `android/` sont déjà configurés dans ce dépôt. Vous n'avez pas à réinitialiser Vite ni Capacitor.

### Prérequis
* **Node.js v26 LTS** *(minimum v22)*
* **VS Code** avec les extensions `Vue - Official` et `Tailwind CSS IntelliSense`
* *(Uniquement pour tester/compiler sur téléphone)* **Android Studio** (avec un SDK récent, ex: API 36, et **Gradle JDK 21** — voir section 4 de `SETUP.md`).

### 1. Installer les dépendances
*(Le dossier `node_modules/` n'est pas sur Git, il faut le régénérer après le clone)* :

```shell
git clone <URL_DU_REPO>
cd ruralien
npm install
```

### 2. Lancer le serveur de développement (Web / Navigateur)
Idéal pour développer et tester l'interface rapidement (`http://localhost:5173`) :

```shell
npm run dev
```

### 3. Tester sur Android (Téléphone USB ou Émulateur)
*(Le dossier `dist/` n'étant pas versionné sur Git, il faut compiler au moins une fois avant de synchroniser Android)* :

```shell
npm run build          # Compile le projet Vue dans dist/
npx cap sync android   # Copie dist/ et les plugins natifs dans android/
npx cap open android   # Ouvre Android Studio
```
*(Raccourci équivalent déjà configuré dans `package.json` : `npm run android:open`)*.

Dans **Android Studio**, attendez la fin de la synchronisation Gradle en bas à droite, puis cliquez sur **▶ Run 'app'**.

> **Astuce Debug :** Avec le téléphone branché en USB (débogage USB activé), ouvrez `chrome://inspect/#devices` dans Google Chrome sur votre PC pour accéder à la console JS et à l'inspecteur en direct sur l'app Android.

---

## Scripts disponibles (`package.json`)

| Commande | Action |
| :--- | :--- |
| `npm run dev` | Lance le serveur local Vite avec rechargement instantané |
| `npm run build` | Compile l'application web de production dans `dist/` |
| `npm run android:sync` | Compile (`build`) et copie les fichiers dans `android/` |
| `npm run android:open` | Compile, synchronise et ouvre Android Studio |

---

*Copyright (c) 2024-2026 Galaxaris. All rights reserved.*