# MailCatcher

[Mailcatcher](http://mailcatcher.me) runs a super simple SMTP server which catches any message sent to it to display in a web interface.


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
