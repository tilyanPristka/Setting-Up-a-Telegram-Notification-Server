# Setting Up a Telegram Notification Server

#### Hello, TagUI enthusiasts! 👋

As part of my commitment to supporting the community, I’ve set up a Telegram Notification server to enhance productivity and streamline updates for everyone. This server is designed to help automate notifications and make your workflows even smoother.

I’m excited to share this with all of you and would love to hear your thoughts. If there’s anything specific you’d like to see added or any features you think could be helpful, feel free to let me know!

-------------

#### How to Use the Telegram Notification Server

To integrate the Telegram Notification server into your TagUI setup, follow these simple steps:

##### - Locate the File:
Open the file `tagui/src/tagui_header.js` in your TagUI installation directory.
##### - Modify the Endpoint:
Look for the line defining the Telegram endpoint. Update it to point to the new server:

```
var telegram_endpoint = 'https://tilyanpristka.id/taguibot';
```

-------------

#### Using Your Own Telegram Bot with TagUI

If you’d prefer to use your own Telegram bot for notifications, follow these steps to set it up:

##### - Locate the File:

Open the file `tagui/src/tagui_header.js` in your TagUI installation directory.

##### - Add Your Telegram Token:

Find the line defining telegram_endpoint and add the following code directly beneath it:

```
var telegram_token = ''; // Replace with your bot's token
```

##### - Update the Telegram Intent Function:

Look for the `function telegram_intent($raw_intent)` in the same file and `tagui/src/tagui_parse.php`. In the function, replace `telegram_result` with the following code:

```
telegram_result = call_api(telegram_endpoint+'/sendMessage.php?chat_id='+telegram_chat_id+'&text='+telegram_message+'&token='+telegram_token);
```

##### - Save Your Changes:

Save the file after making these updates.

##### - Test Your Bot:

Run a TagUI workflow that includes Telegram notifications to confirm everything is working as expected.

-------------

Let’s collaborate to make automation even more accessible and efficient! 🚀

Feel free to leave your feedback and ideas in the comments. 😊

