# AUD/USD 雙邊匯率分析與時間序列預測

國際金融課程的個人分析專案，針對 AUD/USD（澳幣/美元）雙邊匯率進行歷史資料分析與未來走勢預測。

## 專案內容

1. **雙邊匯率資料分析**：讀取每週匯率資料（WK4–WK13），計算漲跌幅、波動區間（High-Low Range）與趨勢標籤（升值/貶值/持平），並繪製收盤價、最高價、最低價的走勢圖。

2. **時間序列預測模型比較**：使用 2000 年至今的月頻匯率資料，比較四種預測方法：
   - ARIMA（透過 `pmdarima.auto_arima` 自動選擇最佳參數）
   - ETS 指數平滑（Exponential Smoothing）
   - Naive（隨機漫步）
   - Seasonal Naive（去年同月）

   以 2025 年為驗證集，用 RMSE 評估各模型表現，並用 ACF/PACF 圖檢視匯率序列的自相關性質（非平穩、長記憶等特徵），選出最佳模型後進行未來 12 個月的預測，並與實際預測值（分析師預測資料）進行比較。

3. **經常帳與匯率關聯分析**：整理 2000–2025 年澳洲經常帳占 GDP 比重資料，與同期 AUD/USD 年均匯率並列繪圖，觀察兩者長期走勢的關聯性。

## 使用工具

pandas、numpy、matplotlib、statsmodels（ARIMA、Exponential Smoothing、ACF/PACF）、pmdarima（auto_arima）、scikit-learn（RMSE 計算）

## 檔案

- `aud_usd_exchange_rate_forecasting.ipynb`：完整分析程式碼

> 註：原始資料檔（週資料、月資料、經常帳資料等 CSV）為課程作業提供的練習資料，未包含在此 repo 中；若要重新執行，需自備相同格式的 CSV 檔案並放入 Colab 的 `/content/` 目錄。

## 作者

鍾嬡 (Audrey)

