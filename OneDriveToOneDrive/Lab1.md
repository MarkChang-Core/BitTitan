# Microsoft 365 One Drive to Microsoft 365 One Drive

## Lab 1 - Source 環境準備

如同前章所述，為方便說明，這邊準備了一個模擬情境以進行遷移，內容如下 - 

```Source - user01@bittitan-lab.com (Microsoft 365 Business Standard)```

```Destination - user01@bittitandestination.onmicrosoft.com (Microsoft 365 Business Standard)```

首先需要先針對 Source 環境進行一些準備，詳細說明如下。

### 使用者清單準備

在遷移之中，會需要使用到全域管理員身分作為Credential，若無法索取到全域管理員，至少需是對Source信箱具有存取權限的帳號，

詳情可以參考 - [MigrationWiz – Permission Requirements](https://help.bittitan.com/hc/en-us/articles/360041202494-MigrationWiz-Permission-Requirements#office-365-exchange-online-mailbox-and-archive--0-4)

若需要遷移大量的使用者，BitTitan可支援批量匯入的功能，因此你可以先到 Microsoft 365 Portal 之中，將使用者名單大量匯出 -

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/image/image-onedrive1-1.jpg)<br>

並且對應上Destinantion的資訊後，製作成一份遷移的清單 (可不填入密碼) -

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/image/image-onedrive1-2.jpg)<br>

由於BitTitan支援透過全域管理員的Credenitail作為驗證，因此在整理出的遷移清單中，是可以不填入密碼的。

### Source 管理者與應用程式權限準備

Step1. 請先確認管理者權限已經開啟 SharePoint System Admin 權限<br>

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/image/image-onedrive1-3.jpg)<br>

Step2. 接著請在 Source 與 Destination 的 Microsoft 365 Admin Center 中，建立一組安全性群組，並將名稱設定為 ***MigrationWiz*** <br>

設定完成後，將用來作為BitTitan驗證憑據的管理員加入成為 ***成員***<br>

Step3. 接著請以全域管理者身分，授權BitTitan API的存取權，透過全域管理員身分登入 BitTitan 所提供的授權連結 -<br>

https://login.microsoftonline.com/common/adminconsent?client_id=0173390d-c130-431b-bd6b-f096a2ccad4e&state=12345<br>

點擊上述連結後，以管理員身分點選 ***接受*** -<br>

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/image/image-onedrive1-4.jpg)<br>

---

當這些資訊與環境都準備完成後，可前往 [Lab2 Destination 環境準備](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/Lab2.md)

