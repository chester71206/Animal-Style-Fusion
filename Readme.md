# 動物風格融合程式

## 專案簡介
本專案利用生成式AI模型 **Stable Diffusion**，實現將兩種動物風格進行融合的功能，生成具有兩種動物特徵的新奇生物圖像。該程式結合了爬蟲技術、自定義下拉式選單和AI模型，讓使用者可以輕鬆選擇動物並生成融合結果。

---

## 功能特色
1. **動物數據收集**
   - 使用爬蟲技術從 [PNGIMG 動物圖片網站](https://pngimg.com/images/animals) 獲取各種動物名稱及其圖片。

2. **自定義下拉選單**
   - 使用者可選擇兩種動物，系統自動獲取相關圖片並融合生成新動物。

3. **Stable Diffusion 模型生成**
   - 基於用戶選擇的動物，生成帶有兩種動物特徵的圖像。
   - Prompt 示例：`A fusion of goat and bear, featuring the body parts and distinct traits of both animals in a harmonious blend.`

4. **視覺化與輸出**
   - 提供動物圖片的融合示例，支持用戶保存生成結果。

---

## 技術細節

### 1. 技術架構
- **爬蟲技術**：抓取動物圖片與名稱，建立數據庫。
- **Stable Diffusion**：使用 `CompVis/stable-diffusion-v1-4` 模型進行圖像生成。
- **ipywidgets**：提供互動式下拉選單，方便用戶選擇動物。
- **生成圖像處理**：
  - 將兩張動物圖片進行初步融合，模糊邊界，輸出到Stable Diffusion進行細節生成。

### 2. Prompt 與生成參數
- **Prompt**:
  - 正向描述：`A fusion of {animal1} and {animal2}, featuring the body parts and distinct traits of both animals in a harmonious blend.`
  - 負向描述：`A split image with a clear line in the middle, disjointed features, two separate animals, a bad fusion of animals, unclear features, distorted image.`
- **生成參數**：
  - 圖片尺寸：512x512
  - 推理步驟：60
  - 引導比例：7.5
 
### 3. 範例照片
**dog + deer**
- <img src="https://github.com/user-attachments/assets/fbefcc8a-8990-4a9b-b74e-701381b7db35" alt="dog+deer" width="400"/>

**turtle + shark**
- <img src="https://github.com/user-attachments/assets/7ab19be2-e695-492d-84ba-2359eea8b836" alt="turtle+shark" width="400"/>
