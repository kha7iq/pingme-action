<h2 align="center">
  <br>
  <p align="center"><img width=20% src="https://raw.githubusercontent.com/kha7iq/pingme/master/.github/img/logo.png"></p>
</h2>


<p align="center">
   <a href="https://github.com/kha7iq/pingme-action/releases">
   <img alt="Release" src="https://img.shields.io/github/v/release/kha7iq/pingme-action">
   <a href="https://hub.docker.com/r/khaliq/pingme">
   <img alt="Docker Image Size (latest by date)" src="https://img.shields.io/docker/image-size/khaliq/pingme">
   <a href="#">
   <img alt="GitHub repo size" src="https://img.shields.io/github/repo-size/kha7iq/pingme-action">
   <a href="https://github.com/kha7iq/pingme-action/issues">
   <img alt="GitHub issues" src="https://img.shields.io/github/issues/kha7iq/pingme-action?style=flat-square&logo=github&logoColor=white">
   <a href="https://github.com/kha7iq/pingme-action/blob/master/LICENSE.md">
   <img alt="License" src="https://img.shields.io/github/license/kha7iq/pingme-action">
</a>
</p>

---

## PingMe Github Action

**PingMe Github Action** is based on the utility  [**PingMe**](https://github.com/kha7iq/pingme). It provides the ability to send messages or alerts to multiple messaging platforms and also email.

You can view the [**PingMe Documentation**](https://pingme.lmno.pk) for complete configurations.

## Supported services

  - [Telegram](#telegram)
  - [Pushover](#pushover)
  - [PushBullet](#pushbullet)
  - [Slack](#slack)
  - [RocketChat](#rocketchat)
  - [Discord](#discord)
  - [Email](#email)
  - [Microsoft Teams](#microsoft-teams)
  - [Mattermost](#mattermost)
  - [Twillio](#twillio)
  - [Gotify](#gotify)
  - [Line](#line)
  - [Mattermost](#mattermost-1)
  - [Mastodon](#mastodon)
  - [Textmagic](#textmagic)
  - [WeChat](#wechat)
  - [Zulip](#zulip)


# Usage Example

## Telegram
```yaml
on: [push]

jobs:
  pingme-job:
    runs-on: ubuntu-latest
    name: PingMe
    steps:
      - name: Checkout
        uses: actions/checkout@v2

      - name: Ping me On
        uses: kha7iq/pingme-action@v1
        env:
          TELEGRAM_TOKEN: ${{ secrets.TELEGRAM_TOKEN }}
          TELEGRAM_CHANNELS: ${{ secrets.TELEGRAM_CHANNELS }}
          TELEGRAM_TITLE: 'Reference: ${{ github.ref }}'
          TELEGRAM_MESSAGE: 'Event is triggered by ${{ github.event_name }}'
        
        with:
          # Chose the messaging platform. 
          # slack / telegram / rocketchat / teams / pushover / discord / email / pushbullet / twillio
          service: telegram
```

## Pushover
```yaml
on: [push]

jobs:
  pingme-job:
    runs-on: ubuntu-latest
    name: PingMe
    steps:
      - name: Checkout
        uses: actions/checkout@v2

      - name: Ping me On
        uses: kha7iq/pingme-action@v1
        env:
          PUSHOVER_TOKEN: ${{ secrets.PUSHOVER_TOKEN }}
          PUSHOVER_USER: ${{ secrets.PUSHOVER_USER }}
          PUSHOVER_TITLE: 'Reference: ${{ github.ref }}'
          PUSHOVER_MESSAGE: 'Event is triggered by ${{ github.event_name }}'
        
        with:
          service: pushover
```

## PushBullet

```yaml
on: [push]

jobs:
  pingme-job:
    runs-on: ubuntu-latest
    name: PingMe
    steps:
      - name: Checkout
        uses: actions/checkout@v2

      - name: Ping me On
        uses: kha7iq/pingme-action@v1
        env:
          PUSHBULLET_TOKEN: ${{ secrets.PUSHBULLET_TOKEN }}
          PUSHBULLET_DEVICE: ${{ secrets.PUSHBULLET_DEVICE }}
          PUSHBULLET_TITLE: 'Reference: ${{ github.ref }}'
          PUSHBULLET_MESSAGE: 'Event is triggered by ${{ github.event_name }}'
        with:
          service: pushbullet
```

## Slack
```yaml
on:
  release:
    types: [published]
jobs:
  pingme-job:
    runs-on: ubuntu-latest
    name: PingMe
    steps:
      - name: Checkout
        uses: actions/checkout@v2
      
      - name: Ping me On
        uses: kha7iq/pingme-action@v1
        env:
          SLACK_TOKEN: ${{ secrets.SLACK_TOKEN }}
          SLACK_CHANNELS: ${{ secrets.SLACK_CHANNELS }}
          SLACK_MSG_TITLE: 'Reference: ${{ github.ref }}'
          SLACK_MESSAGE: 'Event is triggered by ${{ github.event_name }}'
        with:
          service: slack
```

## RocketChat
```yaml
on:
  release:
    types: [published]
jobs:
  pingme-job:
    runs-on: ubuntu-latest
    name: PingMe
    steps:
      - name: Checkout
        uses: actions/checkout@v2
      
      - name: Ping me On
        uses: kha7iq/pingme-action@v1
        env:
          ROCKETCHAT_USERID: ${{ secrets.ROCKETCHAT_USERID }}
          ROCKETCHAT_TOKEN: ${{ secrets.ROCKETCHAT_TOKEN }}
          ROCKETCHAT_SERVER_URL: ${{ secrets.ROCKETCHAT_SERVER_URL }}
          ROCKETCHAT_CHANNELS: ${{ secrets.ROCKETCHAT_CHANNELS }}
          ROCKETCHAT_TITLE: 'Reference: ${{ github.ref }}'
          ROCKETCHAT_MESSAGE: 'Event is triggered by ${{ github.event_name }}'
        with:
          service: rocketchat
```
## Discord
```yaml
on:
  release:
    types: [published]
jobs:
  pingme-job:
    runs-on: ubuntu-latest
    name: PingMe
    steps:
      - name: Checkout
        uses: actions/checkout@v2
      
      - name: Ping me On
        uses: kha7iq/pingme-action@v1
        env:
          DISCORD_TOKEN: ${{ secrets.DISCORD_TOKEN }}
          DISCORD_CHANNELS: ${{ secrets.DISCORD_CHANNELS }}
          DISCORD_MSG_TITLE: 'Reference: ${{ github.ref }}'
          DISCORD_MESSAGE: 'Event is triggered by ${{ github.event_name }}'
        with:
          service: discord
```

## Email
```yaml
on:
  release:
    types: [published]
jobs:
  pingme-job:
    runs-on: ubuntu-latest
    name: PingMe
    steps:
      - name: Checkout
        uses: actions/checkout@v2
      
      - name: Ping me On
        uses: kha7iq/pingme-action@v1
        env:
          EMAIL_SENDER: ${{ secrets.EMAIL_SENDER }}
          EMAIL_PASSWORD: ${{ secrets.EMAIL_PASSWORD }}
          EMAIL_RECEIVER: ${{ secrets.EMAIL_RECEIVER }}
          EMAIL_HOST: 'smtp.gmail.com'
          EMAIL_PORT: '587'
          EMAIL_SUBJECT: 'Reference: ${{ github.ref }}'
          EMAIL_MESSAGE: 'Event is triggered by ${{ github.event_name }}'
        with:
          service: email
```

## Microsoft Teams
```yaml
on: [push]

jobs:
  pingme-job:
    runs-on: ubuntu-latest
    name: PingMe
    steps:
      - name: Checkout
        uses: actions/checkout@v2

      - name: Ping me On
        uses: kha7iq/pingme-action@v1
        env:
          TEAMS_WEBHOOK: ${{ secrets.TEAMS_WEBHOOK }}
          TEAMS_MSG_TITLE: 'Reference: ${{ github.ref }}'
          TEAMS_MESSAGE: 'Event is triggered by ${{ github.event_name }}'   
        with:
          service: teams
```

## Mattermost

```yaml
on:
  release:
    types: [published]
jobs:
  pingme-job:
    runs-on: ubuntu-latest
    name: PingMe
    steps:
      - name: Checkout
        uses: actions/checkout@v2

      - name: Ping me On
        uses: kha7iq/pingme-action@v1
        env:
          MATTERMOST_TOKEN: ${{ secrets.MATTERMOST_TOKEN }}
          MATTERMOST_SERVER_URL: ${{ secrets.MATTERMOST_SERVER_URL }}
          MATTERMOST_CHANNELS: ${{ secrets.MATTERMOST_CHANNELS }}
          MATTERMOST_TITLE: 'Reference: ${{ github.ref }}'
          MATTERMOST_MESSAGE: 'Event is triggered by ${{ github.event_name }}'
        with:
          service: mattermost
```

## Twillio

```yaml
on:
  release:
    types: [published]
jobs:
  pingme-job:
    runs-on: ubuntu-latest
    name: PingMe
    steps:
      - name: Checkout
        uses: actions/checkout@v2

      - name: Ping me On
        uses: kha7iq/pingme-action@v1
        env:
          TWILLIO_TOKEN: ${{ secrets.TWILLIO_TOKEN }}
          TWILLIO_ACCOUNT_SID: ${{ secrets.TWILLIO_ACCOUNT_SID }}
          TWILLIO_SENDER: ${{ secrets.TWILLIO_SENDER }}
          TWILLIO_RECEIVER: ${{ secrets.TWILLIO_RECEIVER }}
          TWILLIO_TITLE: 'Reference: ${{ github.ref }}'
          TWILLIO_MESSAGE: 'Event is triggered by ${{ github.event_name }}'
        with:
          service: twillio
```

## Gotify

```yaml
on: [push]

jobs:
  pingme-job:
    runs-on: ubuntu-latest
    name: PingMe
    steps:
      - name: Checkout
        uses: actions/checkout@v2

      - name: Ping me On
        uses: kha7iq/pingme-action@v1
        env:
          GOTIFY_TOKEN: ${{ secrets.GOTIFY_TOKEN }}
          GOTIFY_URL: 'example.com'
          GOTIFY_TITLE: 'Reference: ${{ github.ref }}'
          GOTIFY_MESSAGE: 'Event is triggered by ${{ github.event_name }}'
        
        with:
          # Chose the messaging platform. 
          # slack / telegram / rocketchat / teams / pushover / discord / email
          service: gotify
```

## Line

```yaml
on: [push]

jobs:
  pingme-job:
    runs-on: ubuntu-latest
    name: PingMe
    steps:
      - name: Checkout
        uses: actions/checkout@v2

      - name: Ping me On
        uses: kha7iq/pingme-action@v1
        env:
          LINE_SECRET: ${{ secrets.LINE_SECRET }}
          LINE_TOKEN: ${{ secrets.LINE_TOKEN }}
          LINE_RECEIVER_IDS: 'ab1235xxx8'
          LINE_MSG_TITLE: 'Reference: ${{ github.ref }}'
          LINE_MESSAGE: 'Event is triggered by ${{ github.event_name }}'
        with:
          service: line
```

## Mattermost

```yaml
on:
  release:
    types: [published]
jobs:
  pingme-job:
    runs-on: ubuntu-latest
    name: PingMe
    steps:
      - name: Checkout
        uses: actions/checkout@v2
      
      - name: Ping me On
        uses: kha7iq/pingme-action@v1
        env:
          MATTERMOST_TOKEN: ${{ secrets.MATTERMOST_TOKEN }}
          MATTERMOST_SERVER_URL: ${{ secrets.MATTERMOST_SERVER_URL }}
          MATTERMOST_CHANNELS: ${{ secrets.MATTERMOST_CHANNELS }}
          MATTERMOST_TITLE: 'Reference: ${{ github.ref }}'
          MATTERMOST_MESSAGE: 'Event is triggered by ${{ github.event_name }}'
        with:
          service: mattermost
```

## Mastodon

```yaml
on: [push]

jobs:
  pingme-job:
    runs-on: ubuntu-latest
    name: PingMe
    steps:
      - name: Checkout
        uses: actions/checkout@v2

      - name: Ping me On
        uses: kha7iq/pingme-action@v1
        env:
          MASTODON_TOKEN: ${{ secrets.MASTODON_TOKEN }}
          MASTODON_SERVER: 'mastodon.social'
          MASTODON_TITLE: 'Reference: ${{ github.ref }}'
          MASTODON_MESSAGE: 'Event is triggered by ${{ github.event_name }}'
        
        with:
          service: mastodon
```

## Textmagic

```yaml
on: [push]

jobs:
  pingme-job:
    runs-on: ubuntu-latest
    name: PingMe
    steps:
      - name: Checkout
        uses: actions/checkout@v2

      - name: Ping me On
        uses: kha7iq/pingme-action@v1
        env:
          TEXTMAGIC_USER: ${{ secrets.TEXTMAGIC_USER }}
          TEXTMAGIC_TOKEN: ${{ secrets.TEXTMAGIC_TOKEN }}
          TEXTMAGIC_TITLE: 'Reference: ${{ github.ref }}'
          TEXTMAGIC_MESSAGE: 'Event is triggered by ${{ github.event_name }}'
          TEXTMAGIC_RECEIVER:  ${{ secrets.TEXTMAGIC_RECEIVER }}
        with:
          service: textmagic
```

## WeChat

```yaml
on: [push]

jobs:
  pingme-job:
    runs-on: ubuntu-latest
    name: PingMe
    steps:
      - name: Checkout
        uses: actions/checkout@v2

      - name: Ping me On
        uses: kha7iq/pingme-action@v1
        env:
          WECHAT_APPID: ${{ secrets.WECHAT_APPID }}
          WECHAT_APPSECRET: ${{ secrets.WECHAT_APPSECRET }}
          WECHAT_TOKEN: ${{ secrets.WECHAT_TOKEN }}
          WECHAT_ENCODINGAESKEY: ${{ secrets.WECHAT_ENCODINGAESKEY }}
          WECHAT_RECEIVER_IDS: ${{ secrets.WECHAT_RECEIVER_IDS }}
          WECHAT_MSG_TITLE: 'Reference: ${{ github.ref }}'
          WECHAT_MESSAGE: 'Event is triggered by ${{ github.event_name }}'
        
        with:
          service: wechat

```

## Zulip

```yaml
on: [push]

jobs:
  pingme-job:
    runs-on: ubuntu-latest
    name: PingMe
    steps:
      - name: Checkout
        uses: actions/checkout@v2

      - name: Ping me On
        uses: kha7iq/pingme-action@v1
        env:
          ZULIP_DOMAIN: ${{ secrets.ZULIP_DOMAIN }}
          ZULIP_BOT_EMAIL_ADDRESS: ${{ secrets.ZULIP_BOT_EMAIL_ADDRESS }}
          ZULIP_BOT_API_KEY: ${{ secrets.ZULIP_BOT_API_KEY }}
          ZULIP_MSG_TYPE: 'stream'
          ZULIP_STREAM_NAME: 'general'
          ZULIP_TOPIC: 'Reference: ${{ github.ref }}'
          ZULIP_MESSAGE: 'Event is triggered by ${{ github.event_name }}'
        with:
          service: zulip
```