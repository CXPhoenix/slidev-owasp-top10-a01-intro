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

::title::
# 為什麼會發生權限控制失效？

::default::
<v-clicks>

- **只在前端檢查**
  - 就像考試時只檢查桌面有沒有作弊小抄，卻沒檢查口袋。
  - 開發者只在使用者看得到的部分設定權限檢查，但沒在伺服器端進行驗證。

- **URL參數可被修改**
  - 例如網址是 `www.購物網.com/訂單/12345`。
  - 有些系統只檢查你是否已登入，卻沒檢查訂單「12345」是否真的屬於你。

</v-clicks>

---

::title::
# 為什麼會發生權限控制失效？(續)

::default::
<v-clicks>

- **權限設定太複雜**
  - 當系統的權限規則過於複雜，開發者可能會配置錯誤。
  - 不小心給了用戶過多權限。

- **預設設定不安全**
  - 就像新手機出廠預設密碼是「0000」。
  - 許多開發者使用的工具也有不安全的預設設定。

</v-clicks>

---

::title::
# 這類漏洞的危害有多大？

::default::

<FourColsImg class="py-14">

<v-clicks>

- ![Broken Access Consequence 1](/broken-access-consequence-1.png)
- ![Broken Access Consequence 2](/broken-access-consequence-2.png)
- ![Broken Access Consequence 3](/broken-access-consequence-3.png)
- ![Broken Access Consequence 4](/broken-access-consequence-4.png)

</v-clicks>

</FourColsImg>

<v-click>

- 根據統計，高達 94% 的網站曾出現某種形式的權限控制問題。

</v-click>

---
layout: section
---

::title::
# 如何防範權限控制失效？

::subtitle::
## 保護我們的數位世界

---

::title::
# 企業和開發者的做法

::default::
**權限劃分策略**

![Minimum Access](/minimum-access.png) {.w-[85%] .mx-auto .p-0 .-m-4}

<!--
- **最小權限原則**
  - 就像學校只給老師必要的鑰匙，不會讓每位老師都能開啟所有教室。
  - 系統應該給予用戶執行任務所需的最小權限。
-->

---

::title::
# 企業和開發者的做法

::default::
**完整、可信任的驗證機制**

![Server Validates Access](/server-check-access.png) {.w-[85%] .mx-auto .p-0 .-m-20}
<!--
- **強制後端驗證**
  - 無論前端（你看得到的部分）提交什麼。
  - 伺服器端都要重新檢查你是否真的有權限。
-->

---

::title::
# 企業和開發者的做法

::default::
**設定適當的預設存取機制**

![From Deny All to Secure Access](/from-deny-to-sec-access.png) {.w-[56%] .ml-56 .-m-10}
<!--
- **預設拒絕全部存取請求**
  - 系統應該預設拒絕所有存取，只在確認有權限時才允許。
-->

---

::title::
# 一般使用者能做什麼？

::default::
<v-clicks depth="2">

- **注意URL變化**
  - 如果發現更改網址就能看到別人的資料，這可能是安全漏洞。
  - 應該向網站報告（道德駭客）。

- **定期檢查權限設定**
  - 在社群媒體和應用程式中，定期檢查你的隱私和權限設定。

</v-clicks>

---

::title::
# 一般使用者能做什麼？

::default::
<v-clicks depth="2">

- **使用強密碼和多因素認證**
  - 雖然這不能防止權限控制失效，但能增加帳號被盜後的安全層級（攻擊者無法改變你的密碼）。

- **留意異常現象**
  - 如果突然能看到本來看不到的資料或功能，可能是系統出現問題。

</v-clicks>

---
layout: image
---

::title::
# 總結：保護數位城堡的鑰匙

::default::
![Conclusion](/conclusion.png) {.w-[86%]}

<!--
- 權限控制就像是保護數位城堡的門鎖系統
  - 當它失效時，城堡的每一扇門都可能被未經授權的人開啟。
- 在日益數位化的生活中，了解這類基本的資安概念非常重要
  - 無論你未來是從事商業、法律還是其他非技術領域
  - 這些知識都能幫助你在數位世界中更安全地生活和工作
- 優秀的資安意識不需要成為程式設計師
  - 就像保護自己的家不需要成為鎖匠一樣
  - 基本的認知和警覺性就能大幅提升你的數位安全
-->
