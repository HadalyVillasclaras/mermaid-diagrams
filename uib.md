```mermaid
---
title: Diagrama de flujo
---

flowchart 
subgraph bot.js 
direction BT
  A1([start]) --> A2(tweetIt)
  A2 --> A3[["getImage(images)"]]
  A3 --> A4{"isTweeted(tweet)"}
  A4-- yes --> A1
  A4-- no --> A5[/twit.post/]
  A5 --> A6(saveTweetedImg)
  A6 --> A7([end])
  A7 -- "interval" --> A1
end

subgraph buildImages.js
direction TB
  B1([start]) --> B2[/getText/]
  B2 --> B3[["findSentences(text)"]]
  B3 --> B4("createImages(sentences)")
end


A3<-->B1


````