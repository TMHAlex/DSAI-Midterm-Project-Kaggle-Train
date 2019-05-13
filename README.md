# DSAI-Midterm-Project-Kaggle-Train
DSAI Midterm Project Kaggle Train

模組選擇 : XGboost
特徵選擇 : 主要使用的feature為利用 F1-score 對model的feature重要程度評分，刪除其中比較不重要的feature雖然可以讓整理RMSE稍微減少，但是效果不佳。
資料處理 : 針對異常價格處理，捨棄掉價格大於1萬的值，其中有一項物品價格為0，我選擇使用所有價格平均的小四分衛數填補該空值

