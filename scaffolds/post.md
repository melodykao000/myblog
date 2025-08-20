---
title: {{ title }}
date: {{ date }}
categories:
  - {{ category | default('國內旅遊') }}
tags:
  - {{ tag1 | default('旅遊') }}
  - {{ tag2 | default('攻略') }}
description: {{ description | default('這篇文章分享路線、預算與注意事項。') }}
cover: {{ cover | default('/img/post/cover.jpg') }}
---
（在這裡開始寫正文，可以放圖：`![](./photo.jpg)`；因為有 post_asset_folder，所以這篇文章資料夾裡的圖會自動連結）
