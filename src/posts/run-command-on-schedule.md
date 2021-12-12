---
title: Run a command on schedule (cron)
date: '2020-05-21'
tags:
  - hobbies
  - tech
  - neat stuff
---

> Install speedtest-cli prior to creating the following bash (.sh) script.
><details>
  <summary>speedtest-cli not working?</summary>
  <p>
  		<a href="https://askubuntu.com/questions/1332969/problem-with-speedtest-cli" target="_blank">https://askubuntu.com/questions/1332969/problem-with-speedtest-cli</a>
  </p>
</details>

```
#!/bin/bash
SPEEDTEST=$(speedtest-cli --simple)
message=$(echo $SPEEDTEST)
## format to parse to curl
## echo Sending message: $message
msg_content=\"$message\"

## discord webhook
url='https://discord.com/api/webhooks/PLACEHOLDER'
curl -H "Content-Type: application/json" -X POST -d "{\"content\": $msg_content}" $url
```