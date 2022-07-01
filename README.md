# amazon-discord-server-verifier
Discord Bot for verifying users in the Amazon Discord

**What it does:**  
Users can use the *!verify* command to request a verifier to confirm them.  
The verifier gets this notification through a specified text channel that only those with the verifier role can see and interact with. From there the verifier can choose to confirm them as a specified role or reject them. If confirmed, the user who issued the verify command will be then assigned the role that the verifier confirmed them for.  

**Other Features:**  
- The interaction message for confirmation is formatted using buttons so the verifier can quickly accept and reject applicants.  
- The interaction message for confirmation will automatically delete after 24 hours to keep the text channel spam free.  

**What it looks like:**  
What the user message has to look like in order to verify...  
![user_verifying](https://user-images.githubusercontent.com/44732960/176973115-2da8c429-d1ed-4709-93e6-52898a371ea4.PNG)  
note: the user has to do !verify and attach the proof for confirmation in the same message before sending.  
  
The verifier view...  
![verifier_view](https://user-images.githubusercontent.com/44732960/176972968-93ada79b-670e-4224-bbe2-e79a24cf3ec4.PNG)  
    
**The Setup:**  
Currently the discord bot does not have a feature to automatically set itself up for the server. This decision was made because I do not expect any other servers to have use for this bot.  
  
I currently have the bot hosted on Heroku, which will allow the bot to run 24/7. For me to use it for it's intended purposes, I will need to set up the bot in the Amazon Server. This requires information/tasks from the below instructions (from 3 onwards).  

If you want to host the bot yourself...  
1. Create a discord bot application.  
2. Download the code and push it to a hosting server (such as Heroku).  
3. You will then need to set the environment variables for:  
   - TOKEN [your discord bot api token]
   - VERIFIER_CHANNEL_ID [the channel id that you want the bot to send confirmation forms to]  
   - VERIFIER_ROLE_ID [the role id of the role that will be able to confirm new users]  
   - FULLTIME [the role id of the fulltime role]  
   - INTERN [the role id of the intern role]  
4. Invite the bot to your server with the permisions of:  
   - Manage Roles  
   - Read Messages/View Channels  
   - Send Messages  
   - Attach Files  
5. Move the bot role to the top of the role list. This is important because even if the bot has permissions to manage roles, it can only manage the roles that are below his role.  
6. Add the bot to be able to view and message in the verifier channel.  
