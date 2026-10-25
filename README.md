# Our Fiesta Prep — Family Checklist

A mobile-friendly, interactive fiesta preparation checklist. Family members can:
- Check off tasks and see the progress bar update.
- Assign tasks to family members and change the owner later.
- Add/edit/delete tasks and add/remove family members.
- See an activity feed showing who did what.
- Filter by family member, completion status, or search text.

## Important: enable shared updates

GitHub Pages only hosts the website. To make changes sync between different family members' phones, this starter uses **Firebase Realtime Database**. Until Firebase is configured, changes are saved only in the current browser/device.

### 1. Create a Firebase project
1. Open https://console.firebase.google.com/ and sign in with a Google account.
2. Select **Create a project** and name it `fiesta-family-checklist`.
3. In the project overview, click the web icon `</>` to register a web app. Give it a name such as `Fiesta Prep Website`.
4. Firebase shows a web configuration object. Copy the values for `apiKey`, `authDomain`, `databaseURL`, `projectId`, and `appId`.

### 2. Create the Realtime Database
1. In Firebase, open **Build → Realtime Database**.
2. Click **Create Database** and choose a nearby location.
3. For a simple family checklist, choose **Start in test mode** only while setting up and testing.
4. Copy the database URL shown by Firebase. It usually looks like `https://PROJECT-ID-default-rtdb.firebaseio.com` (some newer projects use a different regional URL).

### 3. Add the Firebase configuration to the website
1. Open `index.html` in the GitHub repository.
2. Find `const FIREBASE_CONFIG = {`.
3. Replace every `PASTE_..._HERE` value with the matching value from your Firebase web app settings. Make sure `databaseURL` is the exact URL shown for your database.
4. Commit the change.

### 4. Database access warning — read before sharing
The included starter is intended as a low-sensitivity family checklist, not a secure private system. **Do not use unrestricted public database rules for anything sensitive.** Anyone who can access a publicly writable database may be able to read, change, or delete its contents. Firebase's temporary test rules expire; do not assume test mode is a safe permanent setting.

For a private, properly secured version, add Firebase Authentication and database rules that require authenticated family members. This starter does not yet implement sign-in or role-based permissions. If you need a link where only invited relatives can edit, configure authentication and rules before sharing it.

### 5. Publish with GitHub Pages
1. Create a **new public repository** named `fiesta-family-checklist` in your GitHub account. Keep it separate from your christening invitation repository.
2. Upload `index.html` and `README.md` to the repository's root.
3. Open repository **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then Save.
5. Wait a minute or two. GitHub will show the published website URL. It will usually be:
   `https://YOUR-GITHUB-USERNAME.github.io/fiesta-family-checklist/`

## How to use it
- The first time someone opens the page, they can enter the name to show in the activity feed.
- Use **Assigned to** under a task to change its owner at any time.
- Tick a checkbox when a task is complete. The completion count, progress bar, and activity feed update.
- Use **Add a task** for extra jobs and **Family members** to maintain the assignment list.
- Share the published GitHub Pages website link with the family.

## Notes
- Firebase web configuration values are identifiers, not server secrets. Never put a service-account private key or admin credentials in browser code.
- A plain GitHub Pages site cannot safely keep shared data by itself. Firebase (or another backend) is what makes cross-device synchronization possible.


## Sound effects
The checklist includes optional sound feedback generated in the browser (no extra audio files needed):
- A soft pop/click for buttons
- A cheerful two-tone sound when a task is completed
- A short ascending chime when progress first reaches 50%
- A victory fanfare when all tasks are complete
- A **Sounds: ON/OFF** button so each device can choose its own preference

Some mobile browsers only allow audio after the user taps the page. Sound settings are saved separately on each device.
