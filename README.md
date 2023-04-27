# IFTTT-RSS-Discord-Webhook
 IFTTT Recipe and steps to take an RSS feed and integrate into a webhook to a Discord server location. 

Using IFTTT (If This Then That), here's a step-by-step guide to setting up an RSS-to-Discord integration using IFTTT:

    Create a Discord Webhook URL for your desired channel:
    a. Go to your Discord server settings.
    b. Click on "Integrations" in the left sidebar.
    c. Click on the "Create Webhook" button.
    d. Choose the desired channel where you want the RSS feed updates to be sent.
    e. Copy the "Webhook URL" as it will be used in IFTTT.

    Create an IFTTT account if you don't have one already: https://ifttt.com/join

    Create a new IFTTT Applet:
    a. Go to "My Applets" in the top right corner: https://ifttt.com/my_applets
    b. Click on "Create" in the top right corner.
    c. Click on the "+This" button.
    d. Search for "RSS" and select the "RSS Feed" service.
    e. Choose the "New feed item" trigger.
    f. Enter the RSS feed URL that you want to monitor, then click "Create trigger."

    Set up the action for the Applet:
    a. Click on the "+That" button.
    b. Search for "Webhooks" and select the "Webhooks" service.
    c. Choose the "Make a web request" action.
    d. Paste the Discord Webhook URL you copied earlier into the "URL" field.
    e. Set the "Method" to "POST."
    f. Set the "Content Type" to "application/json."
    g. In the "Body" field, enter the following JSON payload:

json

{
  "username": "RSS Bot",
  "avatar_url": "https://i.imgur.com/KMdKUvc.png",
  "embeds": [{
    "title": "{{EntryTitle}}",
    "url": "{{EntryUrl}}",
    "description": "{{EntryContent}}"
  }]
}

    Click on "Create action" and then "Finish" to complete the setup.

Now, whenever there's a new item in the RSS feed, IFTTT will trigger the Discord Webhook, and a message will be posted to the specified Discord channel. This method doesn't require any coding, and you can easily modify the appearance of the messages by adjusting the JSON payload in the "Body" field.
