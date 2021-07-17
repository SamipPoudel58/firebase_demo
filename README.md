# 🔥 Firebase Tutorial

1. Create a project in firebase console, copy the script that you get.

2. Paste it in your project(index.html if you are not using any frameworks)

3. Also add the script tags for services that you will integrate like auth,firestore etc.

4. Login using firebase cli

   ```bash
   firebase login
   ```

5. Now, initialize firebase in your project and follow the instructions carefully

   ```bash
   firebase init
   ```

6. Run your project using this command

   ```bash
   firebase emulators:start
   ```

   or

   ```bash
   firebase serve
   ```

7. Deploy your app
   ```bash
   firebase deploy
   ```

# 🔐 Firebase Security

1. Secure the entire DB by preventing read and write across the DB

```js
match /{document=**} {
      allow read, write: if false;
    }
```

2. Secure the collections

```js
match /your_collection/{docId} {
   allow read,write: if request.auth.uid == request.resource.data.uid;
   allow read: if request.auth.uid == resource.data.uid;
}
```

# 💡 Troubleshooting common errors

1. **Unable to list firebase projects in the CLI**
   It might me a login issue, try to re-login
   ```bash
   firebase login --reauth
   ```
2. **Unable to login/signup**
   Make sure authentication service is enabled in the project console

3. **Error in snapshot listener: FirebaseError: no matching index found.**
   For compound queries,you need to add a composite index. In firestore, go to the index tab and create a composite index, add the collection, query scope=collection, and the fields

# ✅ Useful Tips

1. Use Firebase Explorer extension in VS code to manage your projects.
