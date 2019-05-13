# DSAI-Midterm-Project-Kaggle-Train
DSAI Midterm Project Kaggle Train

模組選擇 : XGboost

特徵選擇 : 
    'date_block_num', 'shop_id', 'item_id', 'item_cnt_month', 'city_code','item_category_id', 'type_code', 'subtype_code', 'item_cnt_month_lag_1','item_cnt_month_lag_2', 'item_cnt_month_lag_3', 'item_cnt_month_lag_6','item_cnt_month_lag_12', 'date_avg_item_cnt_lag_1','date_item_avg_item_cnt_lag_1', 'date_item_avg_item_cnt_lag_2','date_item_avg_item_cnt_lag_3', 'date_item_avg_item_cnt_lag_6','date_item_avg_item_cnt_lag_12', 'date_shop_avg_item_cnt_lag_1','date_shop_avg_item_cnt_lag_2', 'date_shop_avg_item_cnt_lag_3','date_shop_avg_item_cnt_lag_6', 'date_shop_avg_item_cnt_lag_12','date_cat_avg_item_cnt_lag_1', 'date_shop_cat_avg_item_cnt_lag_1','date_shop_type_avg_item_cnt_lag_1','date_shop_subtype_avg_item_cnt_lag_1', 'date_city_avg_item_cnt_lag_1','date_item_city_avg_item_cnt_lag_1', 'date_type_avg_item_cnt_lag_1', 'date_subtype_avg_item_cnt_lag_1', 'delta_price_lag','delta_revenue_lag_1', 'month', 'days', 'item_shop_last_sale', 'item_last_sale', 'item_shop_first_sale', 'item_first_sale'
 
使用的feature為利用 F1-score 對model的feature重要程度評分，刪除其中比較不重要的feature雖然可以讓整理RMSE稍微減少，但是效果不佳。
其中
資料處理 : 針對異常價格處理，捨棄掉價格大於1萬的值，其中有一項物品價格為0，我選擇使用所有價格平均的小四分衛數填補該空值

