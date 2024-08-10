# custom-spotify-client

Step Zero

In this step you decide which programming language and IDE you’re going to use and you get yourself setup with a nice new project: disdaccbot.

After that you’ll need to visit the Discord Developer Portal and [Create an Application](https://discord.com/developers/applications?new_application=true):

![img1](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F1ba3caa6-18c1-47a0-92c8-9f0baf132621_469x392.png)

Next you need to configure a bot user.

![img2](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F847a29aa-cd23-45c3-bb68-b5e4addf05d5_762x558.png)

Grab your token and save it somewhere safe. Find the “MESSAGE CONTENT INTENT” setting and enable it.

Then set the permissions for your bot:

![img3](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fae7831f7-da37-42ad-b138-10ecb4bb07f5_876x832.png)

Then head to the OAuth2 / URL Generator and the scopes and permissions as so:

![img4](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb528c8da-1686-4fb7-a3f5-ad7c67cb978e_1271x1295.png)

After that, copy the generated URL that’s just off the screen at the bottom. Pop it in your browser and give your bot permission - ideally to a private test server.

Once all that’s done you should be ready to start coding up your bot! You can dive right in, or you can take some time and go through Discord’s tutorial on building a Discord App.

Step 1 - Hello, World!

In this step your goal is to create you bot and have it connect to the server. Once you’ve done that have it listen for messages and respond to the greeting “Hello” with it’s own greeting that include the person’s name:

![img5](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F292f9d74-c95f-4887-ac53-5c1e16a9f5cb_457x147.png)

Step 2

In this step your goal is to provide a random quote when someone asks for one. We can get some test quotes from the API at dummyJSON.

We’re going to have our bot respond to the message !quote with a random quote. To make it more interesting we’re going to fetch the quote from an external API. We’ll use https://dummyjson.com/ for that.

Check the documentation there for how to use the /quotes endpoint to fetch just one random quote from the 100 that are available.

Once you have it working, it should look something like this:

![img6](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F93911c20-a389-4bad-a388-76111cdb45bd_644x135.png)

Your quote may vary - it’s random after all! 😇

Step 3

In this step your goal is to have the bot provide a list of challenges from the Coding Challenges back catalogue. You can download a JSON document of the past challenges from my Dropbox here.

Then extend you bot to respond to the command !challenge with a random challenge as so:

![img7](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F76dc6a41-8276-42f8-adb2-4cb96604b229_715x220.png)

Again, your challenge may vary - it’s random after all!

Step 4

In this step your goal is to allow new challenges to be added to the catalogue of challenges. To do that you’ll add the command !add <challenge> and the command !list to list all the available challenges.

Once complete it should look like this for the first !list:

![img8](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fc20f7785-b5f2-48c7-b6bb-7ed4f59256b6_835x495.png)

Then you should be able to add this Discord challenge and see it listed. The command to add a challenge should look like !add <challenge URL> and the bot should check the URL is a valid URL and that it refers to a valid challenge on the codingchallenges.fyi website. If so it should read the title of the challenge from the title tag of the HTML.

That should look like this for an invalid URL:

![img9](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F81736698-f61a-4900-99e2-77b2565cac59_610x130.png)

And like this for a valid URL:

![img10](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F7449f091-2078-4033-baf9-64b7a370adf7_748x140.png)

Extra points for making the bot save the newly added challenge to your local copy of the catalogue so new additions are retained when the bot is restarted.

Step 5

In this step your goal is to host your bot somewhere where it can run 24/7/365 as if it were a production system. No this does not count:

![img11](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fef63ccb5-ee18-4183-86f3-e403f579d4b9_640x471.png)

I would suggest using the AWS Free Tier, you can setup a tiny EC2 instance for free. If you’re new to AWS I suggest checking out Guille Ojeda’s guide to creating a Self-healing, Single-instance Environment with AWS EC2.

You can then run your bot as a daemon, ensuring it continues to run is the terminal is closed and is automatically started on startup.
