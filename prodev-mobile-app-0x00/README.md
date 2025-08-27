# prodev-mobile-setup

This repository documents the setup of my **first mobile application** using the **Expo Router template**. The goal of this exercise was to scaffold a React Native app with Expo, understand its file structure, and explore how the reset script manages project state. The project also includes documentation of the steps taken, challenges encountered, and observations made during the setup process.

## Objective

Set up a first mobile application using the Expo Router template. Understand the scaffolding process and the file structure of a React Native application using Expo.

---

## 🚀 Steps Followed for Scaffolding

1. Navigate to parent project directory:

   ```bash
   cd prodev-mobile-setup
   ```

2. Initialize a new Expo project with the Router template:

   ```bash
   npx create-expo-app@latest prodev-mobile-app-0x00
   ```

3. Fixed TypeScript JSX error:

   - Error: `Cannot use JSX unless the '--jsx' flag is provided.ts`
   - Solution: Updated `tsconfig.json` and added:

     ```json
     "jsx": "react-jsx"
     ```

4. Modified the Home screen:

   - File: `app/(tabs)/index.tsx`
   - Changed default text `Welcome!` → `First App Created`.

5. Started development server:

   ```bash
   npx expo start
   ```

6. Tested on iOS device:

   - Initially got version mismatch warning:

     ```
     react-native@0.79.6 - expected version: 0.79.5
     ```

     ✅ Fixed with:

     ```bash
     npx expo install react-native
     ```

   - Faced request timeout scanning QR code.

     - Switched to phone hotspot.
     - Cleared cache with:

       ```bash
       npx expo start -c
       ```

     - Copied `exp://...` URL into Safari on iPhone.
     - ✅ Successfully loaded app.

---

## 🔄 Reset Project

1. Ran:

   ```bash
   npm run reset-project
   ```

2. Prompted:

   ```
   Do you want to move existing files to /app-example instead of deleting them? (Y/n)
   ```

3. Selected `Y`. Effects:

   - Existing project files were moved into a new `/app-example` directory.
   - `/app-example` was automatically added to `.gitignore`.
   - A clean `/app` scaffold was generated.
