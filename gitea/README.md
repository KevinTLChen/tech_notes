### Gitea SonarQube Bot
https://codeberg.org/justusbunsi/gitea-sonarqube-bot

### Installation
Gitea SonarQube Dobt
```
docker save -o gitea-sonarqube-bot-v0.1.1.tar justusbunsi/gitea-sonarqube-bot:v0.1.1
```
[docker pull justusbunsi/gitea-sonarqube-bot:v0.1.1](gitea-sonarqube-bot-v0.1.1.tar.xz)

Create a directory config and place your config.yaml inside it. Open a terminal next to this directory and execute the following:
```
docker run --rm -it -p 9000:3000 -v "$(pwd)/config/:/home/bot/config/" justusbunsi/gitea-sonarqube-bot:v0.1.1
```

### Setup

#### SonarQube
- Create a user and grant permissions to "Browse on project" for the desired project
- Create a token for this user that will be used by the bot
- Create a webhook pointing to https://\<bot-url\>/hooks/sonarqube
- Consider securing it with a secret

#### Gitea

- Create a user and grant permissions to "Read project" for the desired projects including access to "Pull Requests"
- Create a token for this user that will be used by the bot
- Create a project/organization/system webhook pointing to https://\<bot-url\>/hooks/gitea
- Consider securing the webhook with a secret

#### CI system

Some CI systems may emulate a merge and therefore produce another, not yet existing commit hash that is promoted to SonarQube. This would cause the bot to fail to set the commit status in Gitea because the webhook sent by SonarQube contains that commit hash. To mitigate that situation, the bot will look inside the properties object for the key sonar.analysis.sqbot. If available, this key can contain the actual commit hash to use for updating the status in Gitea.
See [SonarQube docs](https://docs.sonarqube.org/latest/project-administration/webhooks) for details.