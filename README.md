# Artale 裝備效益計算機

根據角色屬性與武器係數，計算 **最大/最小表攻**、**換裝後表攻**、**最大表攻成長**、以及 **1 攻擊 ≒ 幾主屬性**。支援「雪花（攻擊力 +20）」切換與本機儲存。

**線上頁面**：[jeremyabcd.github.io/ArtaleCalculate](https://jeremyabcd.github.io/ArtaleCalculate/)

---

## 功能特色

- 根據選擇的 **武器類型** 自動填入武器最大/最小係數
- 即時顯示：
  - 提升前表攻（最小~最大）
  - 換裝後表攻（最小~最大）
  - 最大表攻成長與總增幅（%）
  - 1 攻擊 ≒ 幾主屬性
- **雪花** 勾選：將自動套用攻擊力 +20（再次點擊取消）
- 本機儲存：保留左側主要輸入

---

## 儲存機制

會儲存的鍵（key）：
- main-attr（主屬性）, sub-attr（副屬性）, attack-power（攻擊力）, proficiency（熟練度）
- weapon-type（武器類型）
- snowflake-check（雪花勾選）

> 右側提升區（原/新/差）**不會儲存**。

---

## 使用方式

1. 直接開啟 index.html或 'https://jeremyabcd.github.io/ArtaleCalculate/' 即可使用。
2. 輸入左側欄位（主屬性、副屬性、攻擊力、熟練度），選擇武器類型。
3. 右側「屬性提升計算」可填 **原值 + 新值** 後會自動計算差值或直接填 **差值**（都會即時帶入計算）。
4. 需要時勾選 **使用雪花（攻擊力 +20）**。
5. 若要把提升量直接套用回左側欄位，按下 **「套用新數據」**。

> **注意**：右側「屬性提升計算」的 9 個欄位不會被儲存，左側主要欄位與武器、雪花勾選會被儲存。

---

## 計算公式
### 公式來源
[YT: 快樂甘蔗人](https://www.youtube.com/@%E5%BF%AB%E6%A8%82%E7%94%98%E8%94%97%E4%BA%BA)
（表攻向下取整模擬 Excel ROUNDDOWN)

**最大表攻**


$$
\text{最大表攻}
= \left\lfloor
\frac{\left(\text{主屬}\times \text{武器最大係數} + \text{副屬}\right)\times \text{攻擊}}{100}
\right\rfloor
$$

**最小表攻**

$$
\text{最小表攻}
= \left\lfloor
\frac{\left(\text{主屬}\times \text{武器最小係數}\times 0.9\times \text{熟練度} + \text{副屬}\right)\times \text{攻擊}}{100}
\right\rfloor
$$

**1 攻擊 ≒ 幾主屬性**

$$
\text{比率} = \frac{\Delta(\text{攻擊}+1)}{\Delta(\text{主屬}+1)}
$$

其中 Δ 皆以「未捨去小數」的最大表攻原式計算，最後四捨五入顯示到小數兩位。

---


## 版權與授權
 **MIT License**

**Copyright (c) 2025 Jeremy**。
