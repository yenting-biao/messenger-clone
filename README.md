# Messenger Clone
It is a simplified version of messenger. Users can create an account or log in, and then start messaging with your friends!

## Run the project

1. Install dependencies

   ```bash
   $ yarn
   ```
2. Check `.env.example`, and copy it as `.env.local` and fill in the following content:

   ```text
   PUSHER_ID=
   NEXT_PUBLIC_PUSHER_KEY=
   PUSHER_SECRET=
   NEXT_PUBLIC_PUSHER_CLUSTER=

   AUTH_SECRET=<this can be any random string>
   AUTH_GITHUB_ID=
   AUTH_GITHUB_SECRET=
   ```
3. Start the database by docker, or you can use other method to set up the postgresql database, just make sure that your set up is correct.
   **Note that my database name is `messenger-clone`!**

   ```bash
   $ docker compose up -d
   ```
4. Run migrations

   ```bash
   $ yarn migrate
   ```
5. Start the development server

   ```bash
   $ yarn dev
   ```
6. Open <http://localhost:3000> in your browser.   
   Note that when you enter this page first time, it is likely that you have to refresh once to sign in or sign up if your action is too fast.

## Note

* The two perfect requests I implemented are:
  * **傳送連結** ：自動辨識訊息中文字是否為連結。若是連結，則可以透過該連結開啟新視窗。
  * **自動滾動** ：當出現新訊息時，聊天紀錄需自動滾動至最下方。
* Please make sure your Internet is ok. Pusher may have some problems if your Internet is not stable.
* To delete a chatroom, click the more info icon on the chatroom page and it will show a dialog.
