模組選擇 : XGboost  
樹的數量為1000顆，深度為8，子樹最小權重為0.4，懲罰係數為0.3，特徵採樣比例為0.8，以及為了防止訓練出來的樹與原本的太相似，所以只取80％的子樣本來訓練

特徵選擇 : 
    'date_block_num', 'shop_id', 'item_id', 'item_cnt_month', 'city_code','item_category_id', 'type_code', 'subtype_code', 'item_cnt_month_lag_1','item_cnt_month_lag_2', 'item_cnt_month_lag_3', 'item_cnt_month_lag_6','item_cnt_month_lag_12', 'date_avg_item_cnt_lag_1','date_item_avg_item_cnt_lag_1', 'date_item_avg_item_cnt_lag_2','date_item_avg_item_cnt_lag_3', 'date_item_avg_item_cnt_lag_6','date_item_avg_item_cnt_lag_12', 'date_shop_avg_item_cnt_lag_1','date_shop_avg_item_cnt_lag_2', 'date_shop_avg_item_cnt_lag_3','date_shop_avg_item_cnt_lag_6', 'date_shop_avg_item_cnt_lag_12','date_cat_avg_item_cnt_lag_1', 'date_shop_cat_avg_item_cnt_lag_1','date_shop_type_avg_item_cnt_lag_1','date_shop_subtype_avg_item_cnt_lag_1', 'date_city_avg_item_cnt_lag_1','date_item_city_avg_item_cnt_lag_1', 'date_type_avg_item_cnt_lag_1', 'date_subtype_avg_item_cnt_lag_1', 'delta_price_lag','delta_revenue_lag_1', 'month', 'days', 'item_shop_last_sale', 'item_last_sale', 'item_shop_first_sale', 'item_first_sale'    

使用的feature為先將所有Feature放入模型訓練，訓練完以後，利用 F1-score 對model的feature重要程度評分，Ｆ1分數前五高的feature依序為'item_category_id','month','date_item_avg_item_cnt_lag_1','delta_price_lag','item_cnt_month_lag_1',而比較不重要的像是'city_code','type_code',將這些比較不重要的feature去除雖然可以讓整理ＲＭＳＥ稍微減少，但是效果不佳。  
試著加入每個商店賣出物品的平均數量還有相同型態的物品平均數量也是只有使ＲＭＳＥ減少一些而已，沒辦法造成太大的效果．  

資料預處理 : 針對異常價格處理，捨棄掉價格大於1萬的值，以及捨棄掉商品數量超過1000的物品，並且其中有一項物品的價格小於0，該價格為異常價格，選擇使用train.shop_id==32)&(train.item_id==2973)&(train.date_block_num==4)&(train.item_price>0)該價格中的小四分衛數填補該空值測試結果一樣不能改善ＲＭＳＥ

