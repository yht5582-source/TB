# 結核病臨床導航 TB Clinical Navigator

繁體中文、單檔、無外部套件的臨床教學及決策輔助工具。

網站：https://yht5582-source.github.io/TB/

## 功能

- 四步驟：病人與警訊 → 病原與診斷 → 治療選擇 → 預後與追蹤。
- 區分病原支持、臨床診斷、疑似活動性結核與潛伏感染；資料衝突時阻止進入預防治療。
- 6個月標準、成人17週候選、兒童非重症短療程、INH抗藥與RR/MDR/pre-XDR專家路徑。
- 成人體重劑量、CrCl／HD調整；PD明確提示個別化，未完成腎功能欄位不顯示成人劑量。
- 急症、ALT門檻、EMB視力警訊、交互作用、第2月與第4月後培養反應。
- 8例基本＋4例複雜病例，每例附教學重點。
- 20題考題：10題基礎、10題高階；逐題解析、來源與分項成績。
- 10主分支、多層次、超過60個知識節點的可收合心智圖。
- 列印／另存PDF評估摘要；響應式介面、鍵盤操作及對話框。

## 使用與限制

僅作臨床決策輔助，需由合格醫師核對病況、報告、指引與藥物供應。不是處方系統，並非經驗證的個人死亡率或預後計分模型。未知資料不視為陰性或正常。短療程採保守候選篩選，未通過不必然代表絕對禁忌。

二線藥、兒童劑量、孕婦、複雜肺外病灶、HIV、移植與PD須由相關專科確認。國際方案不等同台灣公費適用，應核對疾管署現行規範。

本頁不收集姓名／病歷號，不使用追蹤、外部API、localStorage或cookie，不自動儲存表單；重整即清除。點選來源連結會前往官方外站。列印檔由使用者自行保管。

## 開發

完整原始碼與測試檔收於 `TB-source.zip`，解壓縮後使用下列目錄與指令。網站本身使用根目錄單一 `index.html`。

- `src/engine.js`：純規則引擎。
- `src/ui.js`：四步表單、12例病例、摘要列印。
- `src/learning.js`：20題測驗及可收合心智圖。
- `src/template.html`：介面與樣式。
- `build.py`：將原始碼嵌入根目錄及dist/index.html；根目錄單檔可直接部署GitHub Pages。
- `tests/clinical.test.cjs`：診療規則與內容檢查。

```sh
python3 build.py
node tests/clinical.test.cjs
```

GitHub Pages：Settings → Pages → Deploy from a branch → main → /(root)。

## 主要依據

查核日期：2026-11-10；實作版本：2026-11-11。

1. [WHO 2025 Diagnosis](https://www.who.int/publications/i/item/9789240107984)
2. [WHO 2026 Treatment and care, 2nd edition](https://www.who.int/publications/i/item/9789240125124)
3. [WHO 2026 drug-resistant update](https://www.who.int/news/item/30-09-2026-who-updates-guidelines-on-drug-resistant-tuberculosis-and-palliative-care)
4. [ATS/CDC/ERS/IDSA 2025](https://www.idsociety.org/practice-guideline/treatment-of-drug-susceptible-tb/treatment-of-drug-resistant-and-drug-susceptible-tb-2025-update/)
5. [ATS/CDC/IDSA diagnosis](https://www.idsociety.org/practice-guideline/diagnosis-of-tb-in-adults-and-children/)
6. [ATS/CDC/IDSA treatment](https://www.idsociety.org/practice-guideline/treatment-of-drug-susceptible-tb/)
7. [CDC 17-week regimen](https://www.cdc.gov/mmwr/volumes/71/wr/mm7108a1.htm)
8. [CDC latent TB treatment](https://www.cdc.gov/tb/hcp/treatment/latent-tuberculosis-infection.html)
9. [Taiwan CDC guidance](https://www.cdc.gov.tw/Category/MPage/YpPM4PxFx3b_6FKuMDYjew)
10. [CDC clinical and laboratory diagnosis](https://www.cdc.gov/tb/hcp/testing-diagnosis/clinical-and-laboratory-diagnosis.html)
11. [WHO 2025 operational handbook](https://www.who.int/publications/i/item/9789240108141)
12. [WHO 2025 consolidated treatment guidance](https://www.who.int/publications/i/item/9789240107243)
