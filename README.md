<h2 align="center">
  <br>
  <p align="center"><img width=20% src="https://raw.githubusercontent.com/kha7iq/pingme/master/.github/img/logo.png"></p>
</h2>

<p align="center">
  <a href="#supported-services">Supported Services</a> •
  <a href="#telegram">Telegram</a> •
  <a href="#pushover">Pushover</a> •
  <a href="#slack">Slack</a> •
  <a href="#rocketchat">RocketChat</a> •
  <a href="#discord">Discord</a> •
  <a href="#email">Email</a> •
  <a href="#microsoft-teams">Microsoft Teams</a> •
</p>

---

## PingMe Github Action

**PingMe Github Action** is based on the utility  [**PingMe**](https://github.com/kha7iq/pingme). It provides the ability to send messages or alerts to multiple messaging platforms and also email.

You can view the [**PingMe**](https://github.com/kha7iq/pingme) repository on github for complete documentation and configuration.

## Supported services
- *Discord*
- *Email*
- *Microsoft Teams*
- *RocketChat*
- *Slack*
- *Telegram*
- *Pushover*


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
          TELEGRAM_TITLE: 'Refrence: ${{ github.ref }}'
          TELEGRAM_MESSAGE: 'Event is triggerd by ${{ github.event_name }}'
        
        with:
          # Chose the messaging platform. 
          # slack / telegram / rocketchat / teams / pushover / discord / email
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
          PUSHOVER_TITLE: 'Refrence: ${{ github.ref }}'
          PUSHOVER_MESSAGE: 'Event is triggerd by ${{ github.event_name }}'
        
        with:
          # Chose the messaging platform. 
          # slack / telegram / rocketchat / teams / pushover / discord / email
          service: pushover
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
          PUSHOVER_TOKEN: ${{ secrets.SLACK_TOKEN }}
          SLACK_CHANNELS: ${{ secrets.SLACK_CHANNELS }}
          SLACK_MSG_TITLE: 'Refrence: ${{ github.ref }}'
          SLACK_MESSAGE: 'Event is triggerd by ${{ github.event_name }}'
        with:
          # Chose the messaging platform. 
          # slack / telegram / rocketchat / teams / pushover / discord / email
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
          ROCKETCHAT_USERID: ${{ secrets.ROCKETCHAT_USERID }}
          ROCKETCHAT_CHANNELS: ${{ secrets.ROCKETCHAT_CHANNELS }}
          ROCKETCHAT_URL_SCHEME: "https"
          ROCKETCHAT_TITLE: 'Refrence: ${{ github.ref }}'
          ROCKETCHAT_MESSAGE: 'Event is triggerd by ${{ github.event_name }}'
        with:
          # Chose the messaging platform. 
          # slack / telegram / rocketchat / teams / pushover / discord / email
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
          DISCORD_MSG_TITLE: 'Refrence: ${{ github.ref }}'
          DISCORD_MESSAGE: 'Event is triggerd by ${{ github.event_name }}'
        with:
          # Chose the messaging platform. 
          # slack / telegram / rocketchat / teams / pushover / discord / email
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
          ROCKETCHAT_CHANNELS: ${{ secrets.ROCKETCHAT_CHANNELS }}
          EMAIL_HOST: 'smtp.gmail.com'
          EMAIL_PORT: '587'
          ROCKETCHAT_URL_SCHEME: "https"
          EMAIL_SUBJECT: 'Refrence: ${{ github.ref }}'
          EMAIL_MESSAGE: 'Event is triggerd by ${{ github.event_name }}'
        with:
          # Chose the messaging platform. 
          # slack / telegram / rocketchat / teams / pushover / discord / email
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
          TELEGRAM_CHANNELS: ${{ secrets.TELEGRAM_CHANNELS }}
          TEAMS_MSG_TITLE: 'Refrence: ${{ github.ref }}'
          TEAMS_MESSAGE: 'Event is triggerd by ${{ github.event_name }}'
        
        with:
          # Chose the messaging platform. 
          # slack / telegram / rocketchat / teams / pushover / discord / email
          service: teams
```