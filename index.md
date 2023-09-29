---
layout: default
title: トップページ
---

# 山口研究室 Wiki 
もしかしたら誰かの役に立つかもしれない研究生活に関する知識や知恵を自由に書き込むサイト．

新しいページを作るときは，ページ名を

研究活動/○○  
研究室生活/○○  
計算機管理情報/○○  
遊び/○○  
のどれかにすると，下のリストに自動的に追加されます．

## site.static_files
{% assign doclist = site.static_files | sort: 'title'  %}
  {% for doc in doclist %}
  {% unless doc.name == "style.scss" || doc.name == "index.md" %} 
  -     [{{ doc.name }}]({{ site.baseurl }}{{ doc.path }})
  {% endunless %}
{% endfor %}

## site.pages
{% assign doclist = site.pages | sort: 'title'  %}
  {% for doc in doclist %}
  {% unless doc.name == "style.scss" || doc.name == "index.md" %} 
  -     [{{ doc.name }}]({{ site.baseurl }}{{ doc.path }})
  {% endunless %}
{% endfor %}

## リンク
### 東野研究室公式ページ
### サイボウズ
### オープンラボ予約ページ
### 東野研業績リスト 登録ページ
## 文献管理
### 文献一覧
