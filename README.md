# Bambu Unesp Bauru
Este projeto é um fork de [Tamiat headless CMS](https://github.com/tamiat/tamiat). Um projeto feito por [Mahmoud Nouman](https://github.com/mahnouman) e [contribuidores](https://github.com/tamiat/tamiat/graphs/contributors).

Tamiat é um gerenciador de conteúdo Headless feito com [Vuejs](https://vuejs.org/) e [Firebase](https://firebase.google.com/).

## Making Tamiat Your Starting Point

1. Clone the CMS repository and install the dependencies.

```bash
# clone the repo
git clone https://github.com/tamiat/tamiat.git

# install the dependencies
npm install
# or
yarn
```

2. Log in to firebase console using your google account and create a new firebase project.

3) In the authentication section, add a new user by providing an email and a password.

4. Rename `database.rules.json.tmp` file in root folder to `database.rules.json`

5) Setup your database basic security rules by going to the `database.rules.json` file in your project and fill in your UID.

```js
{
  "rules": {
    ".write": "(auth.uid === yourUID) || (auth.uid === anOtherUID)" // you can chain these together like so
```

> yourUID and anOtherUID are the uids of users with permission to write to the database. They look something like this "Lxgqp3FmcPVU6UYO6gNdkn1i0ok1". You can obtain a user uid from the authentication section in the firebase console.

6. Navigate to `/src/admin/firebase_config` and rename `config.js.tmp` to `config.js`

7) Copy your project configurations from WEB SETUP (_in Authentication section of firebase console_) and paste them in `config.js` file by replacing the existing ones.

```js
// replace the existing config object below with your configurations
const config = {
  apiKey: 'AIzaSyCnxuLX6AgMduDMLtSJVDNJhR8xuMNvs4Y',
  authDomain: 'tamiat-demo.firebaseapp.com',
  databaseURL: 'https://tamiat-demo.firebaseio.com/',
  projectId: 'tamiat-demo',
  storageBucket: '',
  messagingSenderId: '188459960333'
}
```

8. Run the `firebase init` command (if you haven't installed firebase yet, do so by `npm install -g firebase-tools`), select your firebase project from the list, use the default database rules already present `database.rules.json`, choose `dist` as your public directory and configure the project as a single-page app.

9) Make sure `.firebaserc` is created in your project root directory and the file contains the project id of firebase project you created earlier

10. You can now use `firebase deploy` to deploy the security rules you just entered (to deploy the actual web app you must first use `npm run build` or `yarn build`).

11) Run the local dev server with `npm run dev` or `yarn dev`.

12. Access the admin interface by navigating to `localhost:8080/admin`.

13) Sign in with your previous email and password.

14. (Optional) Navigate to Database menu from sidebar to add demo contents from `tamiat.config.json`

15) Enjoy!

