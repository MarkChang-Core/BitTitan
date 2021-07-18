# Microsoft 365 Exchange Online to Microsoft 365 Exchange Online

## Lab 1 - 環境與事前確認

如同簽章所述，為方便說明，這邊準備了一個模擬情境以進行遷移，內容如下 - 

```Source - user01@bittitan-lab.com (Microsoft 365 Business Standard)```

```Destination - user01@bittitandestination.onmicrosoft.com (Microsoft 365 Business Standard)```

首先需要先針對 Source 環境進行一些準備，詳細說明如下。

### Source 環境準備

在遷移之中，會需要使用到全域管理員身分作為Credential，若無法索取到全域管理員，至少需是對Source信箱具有存取權限的帳號，

詳情可以參考 - [MigrationWiz – Permission Requirements](https://help.bittitan.com/hc/en-us/articles/360041202494-MigrationWiz-Permission-Requirements#office-365-exchange-online-mailbox-and-archive--0-4)

若需要遷移大量的使用者，BitTitan可支援批量匯入的功能，因此你可以先到 Microsoft 365 Portal 之中，將使用者名單大量匯出 -

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/Microsoft%20365%20Exchange%20Online%20to%20Microsoft%20365%20Exchange%20Online/Image/image1-1.jpg)<br>

並且對應上Destinantion的資訊後，製作成一份遷移的清單 (可不填入密碼) -

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/Microsoft%20365%20Exchange%20Online%20to%20Microsoft%20365%20Exchange%20Online/Image/image1-2.jpg)<br>

由於BitTitan支援透過全域管理員的Credenitail作為驗證，因此在整理出的遷移清單中，是可以不填入密碼的。

### Destination 環境準備

雖說BitTitan可以依據你的Source資訊到Destination中創建使用者帳號，但由於這樣做的過程比較繁瑣，

因此我們還是建議你可以先到Destination中創建完成所有的使用者帳號。

---

當這些資訊與環境都準備完成後，您可前往 [Lab2 開始遷移](https://github.com/MarkChang-Core/BitTitan/blob/main/Microsoft%20365%20Exchange%20Online%20to%20Microsoft%20365%20Exchange%20Online/Lab2.md)
