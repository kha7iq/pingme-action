# pingme-cli

GitHub Action to send notifications or messages to multiple platforms.

Example use:

```
on: [push]

jobs:
  pingme-on:
    runs-on: self-hosted
    name: PingMe
    steps:
      - name: Checkout
        uses: actions/checkout@v2
      - name: Run pingme cli
        env:
          PUSHOVER_TOKEN: ${{ secrets.PUSHOVER_TOKEN }}
          PUSHOVER_USER: ${{ secrets.PUSHOVER_USER }}
          PUSHOVER_TITLE: 'Refrence: ${{ github.ref }}'
          PUSHOVER_MESSAGE: 'Event is triggerd by ${{ github.event_name }}'
        uses: ./ # Uses an action in the root directory
        with:
          service: | # Chose the messaging platform. slack / telegram / rocketchat / teams / pushover / discord / email
            pushover 
```