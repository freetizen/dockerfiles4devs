# MailCatcher

[Mailcatcher](http://mailcatcher.me) runs a super simple SMTP server which catches any message sent to it to display in a web interface.

[![](https://images.microbadger.com/badges/image/freetizen/mailcatcher.svg)](https://microbadger.com/images/freetizen/mailcatcher "Get your own image badge on microbadger.com") [![](https://images.microbadger.com/badges/version/freetizen/mailcatcher.svg)](https://microbadger.com/images/freetizen/mailcatcher "Get your own version badge on microbadger.com")


## Usage

```
docker run -d -p 1025:1025 -p 1080:1080 --name mailcatcher freetizen/mailcatcher
```

## Configuration example with docker-compose

```
# docker-compose.yml
version: '2'

services:
  mailcatcher:
    image: freetizen/mailcatcher
    ports:
      - 1025:1025
      - 1080:1080
```
