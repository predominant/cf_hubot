# Hubot Adapted for Cloud Foundry

This is the version of hubot that works on Cloud Foundry.

## Installation

1\. Clone the code

```bash
git clone git://github.com/progmary/hubot.git
```

Make sure you have [node.js][nodejs] and [npm][npmjs] (npm comes with node v0.6.3+) installed.

2\. Install dependencies

```bash
cd hubot
npm install
```
3\. Deploy to Cloud Foundry as Node.js application, you can provide redis service if your hubot scripts need it.

```bash
vmc push my-hubot-app-name
```

4\. Let hubot know its application URL.

```bash
vmc env-add my-hubot-app-name APP_URL=http://my-hubot-app-name.cloudfoundry.com/
```

## Configuring for Campfire

To make it work with Campfire you need to create a [Campfire](http://campfirenow.com/) account first. This account is going to be hubot's account. Then, you need to add several environment variables.

1\. First, set Hubot adapter as campfire.

```bash
vmc env-add my-hubot-app-name HUBOT_ADAPTER=campfire
```

2\. Provide Campfire hubot's account API token. It can be found in "My info" page after logging in.

```bash
vmc env-add my-hubot-app-name HUBOT_CAMPFIRE_TOKEN="...."
```

3\. Provide Campire room IDs. Room ID is a numeric value in URL of the room.

```bash
vmc env-add my-hubot-app-name HUBOT_CAMPFIRE_ROOMS="123,345"
```

4\. Provide Campfire subdomain. The subdomain is the first domain part of Campfire URL. For example, if your Campfire URL is `hubot.campfirenow.com` your subdomain is `hubot`.

```bash
vmc env-add my-hubot-app-name HUBOT_CAMPFIRE_ACCOUNT="...."
```

5\. Join Campfire chat as another user and you should see your Hubot account there. Run `hubot help`.

## Configuring for IRC

1\. First, set Hubot adapter as irc.

```bash
vmc env-add my-hubot-app-name HUBOT_ADAPTER=irc
```

2\. Set IRC host and rooms.

```bash
vmc env-add my-hubot-app-name HUBOT_IRC_SERVER="...."
vmc env-add my-hubot-app-name HUBOT_IRC_ROOMS="#room1,#room2"
```

Other parameters can be found [here](https://github.com/github/hubot/wiki/Adapter:-IRC)

[Original Hubot](https://github.com/github/hubot)
