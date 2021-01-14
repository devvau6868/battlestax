# ⚒️ Verify and Deploy in Netlify

[![License Apache2](https://img.shields.io/hexpm/l/plug.svg)](http://www.apache.org/licenses/LICENSE-2.0)
[![Discord](https://img.shields.io/discord/685554030159593522)](https://discord.com/widget?id=685554030159593522&theme=dark)
[![Actions Status](https://github.com/DataStax-Academy/battlestax/workflows/BattleStax%20Tests/badge.svg)](https://github.com/DataStax-Academy/battlestax/actions) 
[![Netlify Status](https://api.netlify.com/api/v1/badges/e265340f-c6a6-4d7b-b24c-438b87c67876/deploy-status)](https://app.netlify.com/sites/battlestax-tutorial/deploys)

🏠 [Table of Contents](./README.md#%EF%B8%8F-table-of-contents) > 📚 [Connect to your Astra database](./README_step02.md) > ⚒️ **[Verify and Deploy in Netlify](#)**

**Objectives** 

In this **step 3** we will:
- Merge our changes back to master and kick off CI/CD
- Verify and deploy our changes to production with Netlify

**We will cover:**
1. [Merge back to master](#1-merge-back-to-master)
2. [Verify your deployment in Netlify](#2-verify-your-deployment-in-netlify)


## 1. Merge back to master

Now it's time to merge ALL of the changes from the last 3 sections back to master.  This will kick off an automated deploy to Netlify and get our changes ready for production.

📘 **Commands to execute**

```bash
git add functions/insertGame.js src/store/gameSlice.js src/pages/Lobby/NewGame/NewGame.js
git commit -m "Merging insertGame, gameSlice, and NewGame into master"
git push
```

✔️  Once you've completed the **`push`** command above go back to **YOUR** battlestax repository in **Github** and create a Pull Request to merge the changes into master. Use the same exact process we used in Step01 to do this. If you need a refresher go [HERE](./README_step01.md#3-merge-back-to-master) and then come back here to finsih your deployment.

## 2. Verify your deployment in Netlify

✔️  When your new site is ready, you will be able to go to: `<your_url>.netlify.app` to see your game. To find your URL, navigate to **`Deploys`** in **Netlify** and click on the link provided via the UI.

![Netlify final deploy](./tutorial/netlify-final-deploy.png?raw=true)


✔️  Once clicked you should see a display like the following:
![Netlify Setup Example](./tutorial/netlify-createsite-8.png?raw=true)

If you start new games it will create a new record in the database. If you want to validate this behavirour click on `START NEW GAME`.

✔️  Open Astra UI, show the `CQL Console` and execute the following command (here *battlestax* is your keyspace and *games* your collection name - if you chose another names adapt the query accordingly).

📘 **Command to execute**

`SELECT key, text_value FROM battlestax.games;`

You should have a result that looks like the following image. If you see the game you just created in this list you know your application is properly hooked up to your database via the document API.

![Netlify Setup Example](./tutorial/netlify-createsite-9.png?raw=true)

### [🔝](#)

Alrighty, let's sum all this up. If you got to this point you have now deployed an application through a **CI/CD** pipeline with **GitHub Actions** using **serverless** functions that are globally available via **Netlify** all backed by the top NoSQL distributed database Apache Cassandra on **DataStax Astra** without ever touching a server, deploying back-end code, or needing to talk to your IT folks _(no harm meant to my IT friends)_. And if your app goes viral this tech stack will scale with you.

You did this completely from front-end, fullstack knowledge. Awe...some!

Now go take this knowledge and go create the next disruptive application.

---
🏠 **Back** to [Table of Contents](./README.md#%EF%B8%8F-table-of-contents) or **move** to the next section =>[Extra Resources and certifications](./README_Resources.md)