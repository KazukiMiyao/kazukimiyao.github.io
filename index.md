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
  -     {{ doc.name }}
  {% endunless %}
{% endfor %}

## site.pages
{% assign doclist = site.pages | sort: 'url'  %}
  {% for doc in doclist %}
    {% if doc.name == "style.scss" %}
    {% elsif doc.url contains '研究活動/' %}
### 研究活動
- [{{ doc.name }}]({{ site.baseurl }}{{ doc.url }})
    {% elsif doc.url contains '研究室生活/' %}
### 研究室生活
- [{{ doc.name }}]({{ site.baseurl }}{{ doc.url }})
    {% elsif doc.url contains '計算機管理情報/' %}
### 計算機管理情報
- [{{ doc.name }}]({{ site.baseurl }}{{ doc.url }})
    {% elsif doc.url contains '遊び/' %}
### 遊び
- [{{ doc.name }}]({{ site.baseurl }}{{ doc.url }})
    {% else %}
### hoge
- [{{ doc.name }}]({{ site.baseurl }}{{ doc.url }})
    {% endif %}
{% endfor %}

## site.pages ver2
{% assign doclist = site.pages | sort: 'url'  %}
{% assign range = (0..doclist.size) %}
## 研究活動
{% for i in range %}
  {% if doclist[i].url contains '%E7%A0%94%E7%A9%B6%E6%B4%BB%E5%8B%95/' %}
  {% assign dirlist = doclist[i].url | split: "/" %}
- {{dirlist[1]}}
- [{{ doclist[i].title }}]({{ site.url }}{{ doclist[i].url }})
  {% endif %}
{% endfor %}

----

{% for doc in site.docs %}
  {% if doc.category == "研究活動" %}
- [{{ doc.title }}]({{ site.url }}{{ doc.url }})
    <li><a href="{{ doc.url }}">{{ doc.title }}</a></li>
  {% endif %}
{% endfor %}

## リンク
### 東野研究室公式ページ
### サイボウズ
### オープンラボ予約ページ
### 東野研業績リスト 登録ページ
## 文献管理
### 文献一覧
