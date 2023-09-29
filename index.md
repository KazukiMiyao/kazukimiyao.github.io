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

<div>
{% if site.data.samplelist.toc %}
  {% for item in site.data.samplelist.toc2 %}
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


## リンク
### 東野研究室公式ページ
### サイボウズ
### オープンラボ予約ページ
### 東野研業績リスト 登録ページ
## 文献管理
### 文献一覧
