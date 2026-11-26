<img src="src/assets/hero.png" alt="RuraLien logo" width="64" height="64" />

[Readme](README.md) | [Setup](SETUP.md) | [License](LICENSE.md)

# Application RuraLien - v0.1.0-Beta

Application de communication hors-réseau pour les zones rurales, développé par **Galaxaris**.
Couplé au Module RuraLien, utilisant un boîtier LoRa (ESP32), il permet de créer un réseau local maillé pour communiquer sans dépendre d'Internet (zones blanches, montagne, festivals, camps scouts, situations d'urgence).

---


## Télécharger !

L'application RuraLien est encore en cours de développement. Elle sera disponible sur le **Play Store** (Android), en **application Web**, **iOS** et **Desktop** (Windows/Mac/Linux).

Pour tester l'application, suivez le mini-guide dans la section [**Compilation & Test (Développeur)**](#compilation--test-développeur) ci-dessous, ou consultez le fichier **[SETUP.md](./SETUP.md)** pour les détails complets.


## Compilation & Test (Développeur)

> Ce projet utilise **Vue 3 + TypeScript + Vite + Tailwind CSS v4** pour l'interface, et **Capacitor** pour le déploiement sur Android (et iOS/Web/Desktop).
>
> 📖 Pour la documentation technique complète (setup Windows détaillé, permissions Android, Deep Links, build Play Store, déploiement Web, iOS, Electron), consultez **[SETUP.md](./SETUP.md)**.

Le projet Vue, Tailwind et le dossier natif `android/` sont déjà configurés dans ce dépôt. Vous n'avez pas à réinitialiser Vite ni Capacitor.

### Prérequis
* **Node.js v26 LTS** *(minimum v22)*
* **VS Code** avec les extensions `Vue - Official` et `Tailwind CSS IntelliSense`
* *(Uniquement pour tester/compiler sur téléphone)* **Android Studio** (avec un SDK récent, ex: API 36, et **Gradle JDK 21** — voir [SETUP.md - Section 4](./SETUP.md#4-configuration-dandroid-studio--piège-jdk-21).)

### 1. Installer les dépendances
*(Le dossier `node_modules/` n'est pas sur Git, il faut le régénérer après le clone)* :

```shell
git clone https://github.com/galaxaris/ruralien.git
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

### Scripts disponibles (`package.json`)

| Commande | Action |
| :--- | :--- |
| `npm run dev` | Lance le serveur local Vite avec rechargement instantané |
| `npm run build` | Compile l'application web de production dans `dist/` |
| `npm run android:sync` | Compile (`build`) et copie les fichiers dans `android/` |
| `npm run android:open` | Compile, synchronise et ouvre Android Studio |

---

## License

*Copyright (c) 2025-2026 Galaxaris. Tous droits réservés.*

Vous pouvez consulter le fichier **[LICENSE.md](./LICENSE.md)** pour les détails complets de la licence et des conditions d'utilisation.

Visitez notre site ou notre GitHub pour découvrir nos autres projets :
- [Galaxaris](https://galaxaris.fr)
- [Galaxaris sur GitHub](https://github.com/galaxaris)

## Contact

Si vous avez une question ou un retour à propos de RuraLien, vous pouvez nous contacter. Nous serons toujours ravis de répondre ! [Contactez-nous](mailto:contact@galaxaris.fr?subject=RuraLien%20-%20Demande%20d'information)