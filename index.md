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

## site.pages
<div>
{% if site.config.toc[0] %}
  {% for item in site.config.toc %}
    <h3>{{ item.title }}</h3>
      {% if item.subfolderitems[0] %}
        <ul>
          {% for entry in item.subfolderitems %}
              <li><a href="{{ entry.url }}">{{ entry.page }}</a>
                {% if entry.subsubfolderitems[0] %}
                  <ul>
                  {% for subentry in entry.subsubfolderitems %}
                      <li><a href="{{ subentry.url }}">{{ subentry.page }}</a></li>
                  {% endfor %}
                  </ul>
                {% endif %}
              </li>
          {% endfor %}
        </ul>
      {% endif %}
    {% endfor %}
{% endif %}
</div>

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
{% assign flag1 = true %}
{% for doc in site.pages %}
{% if flag1%}
## 研究活動
{% assign flag1 = false %}
{% endif %}
  {% if doc.category == "研究活動" %}
- [{{ doc.title }}]({{ site.url }}{{ doc.url }})
  {% endif %}
{% endfor %}

## リンク
### 東野研究室公式ページ
### サイボウズ
### オープンラボ予約ページ
### 東野研業績リスト 登録ページ
## 文献管理
### 文献一覧
