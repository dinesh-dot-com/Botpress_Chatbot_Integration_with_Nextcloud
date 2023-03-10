# Botpress_Chatbot_Integration_with_Nextcloud
Easy Way To Integrate Botpress Chatbot Into Nextcloud.

STEP 1:
-------
Create a chatbot using bot press https://botpress.com/ and publish it into the cloud.
If you want to self-host, then you have to purchase the enterprise version. 
![Screenshot (206)](https://user-images.githubusercontent.com/105905278/211246842-098a5031-103e-4ddc-8c8e-4d5fc9772153.png)

STEP 2:
-------
Once you created the chatbot, Open your Workspace and Click the WebChat option.
There you can find your Configured Script URL.
![Screenshot (208)](https://user-images.githubusercontent.com/105905278/211247285-c2a6599d-f1b8-4673-804f-c482d32144c6.jpg)
![Screenshot (209)](https://user-images.githubusercontent.com/105905278/211247298-3046325c-ed79-43ee-aa0a-70db631f4dff.jpg)


STEP 3:
-------
Create a separate Linux Cli and Build a Sample <html> file and name it index.html.
Paste the Script URL get from the bot press web chat into Body like 
![Screenshot (214)](https://user-images.githubusercontent.com/105905278/211250236-37f447dd-3679-423c-bbdb-7c77d2271258.jpg)


  <body> 
        <script src="https://example1/webchat/v0/inject.js"></script>
        <script src="https://example2/****-*****-*****-****config.js" defer></script>
  </body>



 Paste the path link into the apache config file and host it.

STEP 4:
------
Login to your nextcloud server and go to the path "/var/www/html/nextcloud/core/templates/layout.user.php"
![Screenshot (213)](https://user-images.githubusercontent.com/105905278/211248692-9ef8628f-7e02-45e1-a21b-7dbec99ce5ef.jpg)

and paste this code there 
![Screenshot (215)](https://user-images.githubusercontent.com/105905278/211488125-8475d295-7ede-4ea9-a489-7f447a077f5e.jpg)

STEP 5:
-------
If you want the bot icon to travel everywhere follow the [STEP:4] (or) If you want for a particular path open the "../nextcloud/apps/any_app/templates/index.php or main.php" Follow the path and paste the Script in [STEP:4].

STEP 6:
-------
Go to the HTTP-COnfigure file "/var/www/html/nextcloud/lib/public/AppFramework/Http/ContentSecurityPolicy.php"
  
![Screenshot (212)](https://user-images.githubusercontent.com/105905278/211248462-8cdc812e-2a92-4c41-b925-de3ba78dc7c7.jpg)

Paste the Url of the Bot which you Created in [STEP:3] to make it a trusted domain>
  
STEP 7:
------

Then go to the PHP config file "/var/www/html/nextcloud/config/config.php" and past the Bot URL as Trusted Domain.
  ![Screenshot (211)](https://user-images.githubusercontent.com/105905278/211247711-66e407ea-4efb-471d-999d-5285183bf659.jpg)


STEP 8:
  
Restart the nextcloud server your bot has successfully integrated with nextcloud.
