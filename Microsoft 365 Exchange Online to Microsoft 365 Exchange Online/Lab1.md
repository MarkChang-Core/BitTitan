# Microsoft 365 Exchange Online to Microsoft 365 Exchange Online

## Lab 1 - 環境與事前確認

如同簽章所述，為方便說明，這邊準備了一個模擬情境以進行遷移，內容如下 - 

```Source - user01@bittitan-lab.com (Microsoft 365 Business Standard)```

```Destination - user01@bittitandestination.onmicrosoft.com (Microsoft 365 Business Standard)```

首先需要先針對 Source 環境進行一些準備，詳細說明如下。

### Source 環境準備

若需要遷移大量的使用者，BitTitan可支援批量匯入的功能，因此你可以先到 Microsoft 365 Portal 之中，將使用者名單大量匯出 -

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image1.jpg)<br>

並且對應上Destinantion的資訊後，製作成一份遷移的清單 (可不填入密碼) -

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image1.jpg)<br>

由於BitTitan支援透過全域管理員的Credenitail作為驗證，因此在整理出的遷移清單中，是可以不填入密碼的。

### Destination 環境準備
