# Taichung-Air-Quality

## 動機
台灣死亡率前10名中肺炎位居第三名，慢性下呼吸道疾病位居第八名，而十大癌症死亡率之首是氣管、支氣管和肺癌。PM2.5懸浮微粒易附著戴奧辛、 多環芳香烴以及重金屬等有毒物質， 長期吸入會引起過敏、氣喘、肺氣腫、肺癌、心血管疾病、肝癌、血液 疾病等。
不管國內外，有許多研究證實PM2.5的濃度增加會增加我們死亡率，比較常採用的研究數據是每增加10 μg/m3 的PM2.5濃度會增加8%的肺癌死亡率、6%的心肺疾病死亡率與4%的總死亡率。
因此我利用台中近十年的PM2.5的濃度數據，建構出圖表來幫助台中市民有效防範PM2.5。
我欲探討以下兩個問題

1.	利用月平均來建議四季出門在外是否應該戴口罩

2.	利用年平均來判斷十年來空氣汙染是否日趨嚴重

## 背景知識
PM2.5是一種細懸浮微粒為飄散在空氣中的極微小的顆粒物質，PM為英文名稱 particulate matter的簡寫。 PM2.5的定義為粒徑範圍在2.5微米或以下的細懸浮微粒，而粒徑範圍在2.5μm ~10μm稱為粗懸浮微粒，單位以微克/立方公尺(μg/m3 )表示之。
懸浮粒子的成分很複雜，主要的來源是從地表揚起的塵土，含有氧化物礦物和其他成分。一部分懸浮粒子是自然過程產生的，源自火山爆發、沙塵暴、森林火災、浪花等。PM2.5還可以由硫和氮的氧化物轉化而成。而這些氣體污染物往往是人類對化石燃料（煤、石油等）和垃圾的燃燒造成的。
因此世界各國各自制定PM2.5濃度的指標，臺灣依照PM2.5濃度分成十個等級，且給出活動建議，如以下圖片所示

<div class="MyTable AQI">
    <p class="MyCaption">空氣品質指標 (AQI)</p>
    <div class="AQIlegend">
        <table>
            <tbody>
                <tr>
                    <td>
                        <span class="bor-top-green">良好<br>
                            0~50</span>
                        </td>
                        <td>
                            <span class="bor-top-yellow">普通<br>
                            51~100</span>
                        </td>
                        <td>
                            <span class="bor-top-orange">對敏感族群不健康<br>
                            101~150</span>
                        </td>
                        <td>
                            <span class="bor-top-red">對所有族群不健康<br>
                            151~200</span>
                        </td>
                        <td>
                            <span class="bor-top-purple">非常不健康<br>
                            201~300</span>
                        </td>
                        <td>
                            <span class="bor-top-brown">危害<br>
                            301~500</span>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</div>

## 資料處理步驟

先從網路上下載台灣近十年空氣品質數據， 並且先做資料清理，列的處理留下SiteName、ItemName、MonitorDate、MonitorVlaue00~23。欄的處理把SiteName進行篩選在台中的五個觀測站，豐原、沙鹿、大里、忠明、西屯，並且把ItemName鎖定在細懸浮微粒PM2.5上，MonitorValue如果遇缺失值使用Nan填補。

平均值計算從2011年1月1號開始到2020年12月31日，會有18170筆資料，先計算出各區每日0時到23時的每小時平均，再利用24個小時平均繪製出日平均圖。日平均由10年裡每月1號到31號的日平均，用31個日平均繪製出月平均圖。年平均圖是用每年12個月的月平均繪製出來。十年平均是用2011到2020的年平均所繪製的。


## 輸出成果

![日平均](https://github.com/leeeating/Taichung-Air-Quality/blob/main/%E6%97%A5%E5%B9%B3%E5%9D%87.png)

![月平均](https://github.com/leeeating/Taichung-Air-Quality/blob/main/%E6%9C%88%E5%B9%B3%E5%9D%87.png)

![年平均](https://github.com/leeeating/Taichung-Air-Quality/blob/main/%E5%B9%B4%E5%B9%B3%E5%9D%87.png)

![十年平均](https://github.com/leeeating/Taichung-Air-Quality/blob/main/%E5%8D%81%E5%B9%B4%E5%B9%B3%E5%9D%87.png)


## 結論

　　從日平均圖可以看出，早上六點之後大家陸續起床準備開始一天的行程，這時的PM2.5濃度逐漸開始上升，直到中午以後濃度會漸趨平穩呈現近似水平線，此時的濃度依照地區不同落在44 μg/m3 ~ 53 μg/m3之間，直到十點左右PM2.5濃度開始下降到低點。

　　從月平均可以看出，PM2.5濃度每月有兩次的大規模減少，大約在6號、20號開始下降，三天後再次逐漸上升，應該是主要製造PM2.5的活動在這幾天例行性的休息，另外10年來30號到31號的濃度也是下降的，不排除是樣本數所影響，這部分要再去看31號的箱型圖分布。

　　從年平均圖可以看出，6到8月的夏季是PM2.5濃度最小的時候，主要原因應該是雨季跟季風的影響，而最嚴重的時候是冬天跨春天的2、3、4月，主要是這三個月大陸冷氣團減弱跟太平洋海洋氣團勢均力敵，無大型季風經過台灣，台灣上方的空氣污染物質很難被帶走，導致PM2.5濃度是全年之最，10月、11月也是因為大陸氣團跟海洋氣團此消彼長，導致季風減弱，難以帶走汙染物質。造成這幾個月PM2.5濃度在53 μg/m3以上，非常不建議從事戶外活動。

　　從十年平均可以看出，十年前立法院制定空氣品質相關的法規後，PM2.5的濃度是逐年下降，直到去年台中全區的年平均值都在35 μg/m3以下，屬於可以放心在戶外活動的標準，不過還是建議看季節跟地區從事戶外活動。

　　在台中五個測站中，空氣品質最差的地區是大里，可能是測站附近工業區比較多，忠明測站附近人口稠密但附近無工業區，所以PM2.5濃度表現較好，而豐原測站雖然人口較少，但附近還是有設立工業區，因此表現時好時壞。

　　總體下來，主要影響空氣品質的兩個因素是季節跟工業活動，季節轉換時因為大陸跟海洋氣團此消彼長，無大型季風出現，導致空氣汙染物質留在地表附近。地區性的差異主要是看附近工業區數量。最後建議在入冬、轉春時盡量減少戶外活動，如果要出門建議配戴口罩，通勤時會經過工業繁忙的地區，也建議配戴口罩。此外如果去醫院進行大型健檢時，也建議多做“低劑量肺部電腦斷層”這個項目，檢測是否有早期的肺腺癌。
