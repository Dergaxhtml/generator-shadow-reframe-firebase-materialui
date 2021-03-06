# Template Frontend

## Here's the most basic template for ClojureScript: 
- Shadow-Cljs
- Re-frame
- Reagent
- Material UI (http://www.material-ui.com/)
- Firebase
    - Realtime Database
    - Storage
    - Auth (Google for now)

All without any wrappers. Working.

### Before you start playing

1. Sign in to https://firebase.google.com/ and add a Realtime Database.
2. Setup rules for the Realtime Database. Initially it's free 4 all.
3. Enable Google login method in Authentication module.
4. Go and have fun.

### Running the project locally for development

- yarn install
- yarn dev
- after a moment you can go to http://localhost:3000/
- in this environment you have `CTRL + H` for debugging FE events + DB

### Build & Deploy to firebase
- init your firebase with `(optional, needed for the first deploy)` 
    - firebase login
    - firebase use --add
- yarn deploy

### Run REPL and take a look at the state
- `yarn repl`
- `(shadow/repl :dev)`
- looking at the current state: `@re-frame.db/app-db`

### Caveats

#### Node and Mac
Tested with node `v11.15.0`. 
Version `v12.7.0` is known to misbehave on Mac OS/X. Try downgrading if you bump into compilation problem, with:
```bash
nvm install v11.15.0
nvm use v11.15.0
```

#### main.js not found
Upon first `yarn dev` there will be following problem:
```bash
FileNotFoundException: public/js/main.js (No such file or directory)
	java.io.FileOutputStream.open0 (FileOutputStream.java:-2)
	java.io.FileOutputStream.open (FileOutputStream.java:270)
	java.io.FileOutputStream.<init> (FileOutputStream.java:213)
```
Running the command again fixes the problem of the missing file:
```bash
yarn dev
```
