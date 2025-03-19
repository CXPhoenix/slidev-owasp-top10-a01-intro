---
theme: "@cxphoenix/slidev-theme-isip.hs"
author: CXPh03n1x
---

::title::
# OWASP A01:2021 權限控制失效 {.pt-5}

::subtitle::


---
layout: image
---

::title::
# 什麼是OWASP？

::default::
![OWASP Intro](/owasp-intro.png) {.w-[80%]}

---

::title::
# 什麼是 OWASP？(續)

::default::
- 就像疫情時每日的記者會
  - 告訴大家目前危險相關的統計數據。
  - 提醒大家目前的安全風險危害。
  - 定時發布「十大最危險的安全風險排行榜」。

<div class="flex justify-end align-center">
  <v-click>
    <img class="w-[40%]" src="/owasp-realworld-link.jpg" alt="OWASP Real world Link" />
  </v-click>
</div>

---
layout: section
---

::title::
# OWASP Top 10

::subtitle::
## 網路應用程式的十大安全風險

---
layout: image
---

::title::
# OWASP Top10 的重要性

::default::
![OWASP Top10 Intro](/owasp-top10-intro.png) {.w-[55%]}

---
layout: image
---

::title::
# OWASP Top 10 分類

::default::
![OWASP Top10 2021 Category](/owasp-top10-categories.png) {.pb-8}

---
layout: section
---

::title::
# A01:2021 權限控制失效

::subtitle::
## Broken Access Control

---

::title::
# 什麼是權限控制？

::default::
- 權限控制就像是網站或應用程式的門鎖系統

  <v-clicks>

  - 決定誰可以進入哪些區域。
  - 誰能看到哪些資料。
  - 誰能執行哪些操作。

  </v-clicks>

---
layout: image
---

::title::
# 什麼是權限控制？

::default::
![Access Components Intro](/access-components-intro.png) {.w-[95%]}

---

::title::
# 什麼是權限控制失效？

::default::
- 當這個系統出問題時，就是「權限控制失效」：
  - 用戶可能看到別人的私人資料。
  - 普通會員可能擁有管理員權限。
  - 未登入的訪客可存取需要授權的功能。

---
layout: image
---

::title::
# 什麼是權限控制失效？

::default::
![Broken Access Consquence](/broken-access.png) {.w-[90%] .pb-10}

---

::title::
# 生活中的權限控制失效

::default::

<v-clicks>

- **學校成績系統**
  - 修改網址中的學號，就能看到其他同學的成績單。

- **社群媒體**
  - 「只限好友可見」的照片，實際上任何人都能通過特定方法看到。

- **線上購物**
  - 改變網址中的訂單編號，就能看到別人的訂單詳情，包含地址和電話。

</v-clicks>

---
layout: section
---

::title::
# 權限控制失效的原因

---

::title::
# 為什麼會發生權限控制失效？

::default::
<v-clicks depth=3>

- **只在前端檢查**
  - 舉例來說，就像是大考時，都會安排每個考生的位置
    監考官在監考時應該要：
    - 確認座位是否有考生
    - 核對座位跟考生的身分是否一致
  - 開發者只在使用者端（也就是前端）設定權限檢查，但沒在伺服器端（也就是後端）進行驗證。

</v-clicks>

---

::title::
# IDOR 權限控制失效案例

::default::
- **URL參數可被修改**
  - 例如網址是 `www.e-comerse.com/orders/12345`。
  - 有些系統只檢查你是否已登入，卻沒檢查訂單「12345」是否真的屬於你。

---
layout: section
---

::title::
# 權限控制失效可實行的防護

---

::title::
# 可實行的防護措施

::default::
<v-clicks depth=1>

- 強制後端驗證
  - 可連結至 Zero Trust 零信任網路
- 預設存取為全部拒絕
  - 針對每一個角色身分個別設定存取權
  - 最小權限原則 (Principle of least privilege)

</v-clicks>

---
layout: section
---

::title::
# 總結

::subtitle::
## 知識回顧

---

::title::
# 總結：權限控制是數位安全的基石

::default::
<v-clicks depth=1>

- OWASP 提供了許多風險的統計資料
  - 每間隔一定時間會提供風險排名 Top 10
  - 目前最近期的應用程式安全風險，來源於 2021 年發布的內容
- 權限控制失效是最嚴重的安全風險
  - OWASP Top 10 的榜首（A01:2021）
  - 高達94%的網站曾出現某種形式的權限控制問題

</v-clicks>

---

::title::
# 總結（續）

::default::
<v-clicks depth=1>

- 權限控制失效可能原因
  - 未進行適當的驗證
  - 未妥善設定存取權限
- 可實施的防護措施
  - 強制後端驗證
  - 預設拒絕存取

</v-clicks>

---
layout: section
---

::title::
# 謝謝大家的觀看

::subtitle::
## 請持續觀看，了解更多資安知識