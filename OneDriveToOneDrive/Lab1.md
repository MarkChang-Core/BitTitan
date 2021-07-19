# Microsoft 365 One Drive to Microsoft 365 One Drive

## Lab 1 - 環境與事前確認

如同前章所述，為方便說明，這邊準備了一個模擬情境以進行遷移，內容如下 - 

```Source - user01@bittitan-lab.com (Microsoft 365 Business Standard)```

```Destination - user01@bittitandestination.onmicrosoft.com (Microsoft 365 Business Standard)```

首先需要先針對 Source 環境進行一些準備，詳細說明如下。

### Source 環境準備

#### 使用者清單準備

在遷移之中，會需要使用到全域管理員身分作為Credential，若無法索取到全域管理員，至少需是對Source信箱具有存取權限的帳號，

詳情可以參考 - [MigrationWiz – Permission Requirements](https://help.bittitan.com/hc/en-us/articles/360041202494-MigrationWiz-Permission-Requirements#office-365-exchange-online-mailbox-and-archive--0-4)

若需要遷移大量的使用者，BitTitan可支援批量匯入的功能，因此你可以先到 Microsoft 365 Portal 之中，將使用者名單大量匯出 -

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/image/image-onedrive1-1.jpg)<br>

並且對應上Destinantion的資訊後，製作成一份遷移的清單 (可不填入密碼) -

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/image/image-onedrive1-2.jpg)<br>

由於BitTitan支援透過全域管理員的Credenitail作為驗證，因此在整理出的遷移清單中，是可以不填入密碼的。

#### Source 管理者與應用程式權限準備

Step1. 請先確認管理者權限已經開啟 SharePoint System Admin 權限<br>

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/image/image-onedrive1-3.jpg)<br>

Step2. 接著請在 Source 與 Destination 的 Microsoft 365 Admin Center 中，建立一組安全性群組，並將名稱設定為 ***MigrationWiz*** <br>

設定完成後，將用來作為BitTitan驗證憑據的管理員加入成為 ***成員***<br>

Step3. 接著請以全域管理者身分，授權BitTitan API的存取權，透過全域管理員身分登入 BitTitan 所提供的授權連結，請參考 BitTitan 官方網站 -<br>

https://help.bittitan.com/hc/en-us/articles/360038153373-Using-App-based-Authentication<br>

點擊上述連結後，以管理員身分點選 ***接受*** -<br>

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/image/image-onedrive1-4.jpg)<br>

### Destination 環境準備

雖說BitTitan可以依據你的Source資訊到Destination中創建使用者帳號，但由於採用此方式過程較為繁瑣，且需設定更多權限，

因此還是建議可先到Destination中創建完成所有的使用者帳號。

#### Azure Storage Account

在BitTitan的遷移之中，針對OneDrive與SharePoint Online部分，將以Azure Storage Accont 作為暫存空間，

因此需要準備Azure Storage Account並依據以下方式進行設定。

Step 1. 登入 [Azure Portal](https://portal.azure.com/) 

Step 2. 於Azure Portal的搜尋列輸入 ***儲存體帳戶*** -

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/image/image-onedrive1-5.jpg)<br>

Step 3. 點選 ***建立*** 以開始創建 Azure Storage Account -

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/image/image-onedrive1-6.jpg)<br>

Step 4. 建立為GPv2規格的Azure Storage Account，建立規格請參考如下 - 

- 儲存體帳戶名稱 - 需要建立一個獨一無二的名稱
- 區域 - 區域建議選擇與Microsoft 365資料儲存位置相同的區域，關於Microsoft 365資料儲存位置請參考 [連結](https://docs.microsoft.com/zh-tw/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#taiwan)
- 效能 - 選擇為 ***標準: 建議用於大多數案例 (一般用途 v2 帳戶)
- 備援 - 備援層級因為屬於暫存資料，因此可選擇為 ***本地備援儲存體 (LRS)*** 即可

其餘設定選擇請保留為預設，並直接點選 ***檢閱 + 建立***，再選擇 ***建立***

> Tips. 由於屬於一次性的遷移作業，且大多數的遷移任務均會在一個月內完成，因此若控制得宜，此作業將僅會產生極少數的費用。
> Tips. 若您有未申請過試用的信用卡，也可以選擇建立[Azure Free Trial](https://azure.microsoft.com/zh-tw/free/) 同樣可以達到這個效果

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/image/image-onedrive1-7.jpg)<br>

Step 5. 創建完成Azure Storage Account後，請對應於Blade中找到 ***存取金鑰***，並點擊顯示金鑰後，保存好 ***儲存體帳戶名稱*** 與 ***機碼***，在後續的遷移過程中將會需要

> Tips. 儲存體帳戶名稱則通常會長得像是 ***accountname***<br>
> Tips. 機碼通常會長得像是 ***W1RrDfkPNkfYfdVqizMNJjn5mXchwMP5uYBY8MsMqWTA7EubG911+4fZlki0Gag==***<br>
> Tips. 你不需要為了這個遷移任務而建立任何Blob Container，這些操作均會由BitTitan在取得授權後，以API型式完成<br>

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/image/image-onedrive1-8.jpg)<br>

#### Destination 管理者與應用程式權限準備

Step1. 請先確認管理者權限已經開啟 SharePoint System Admin 權限<br>

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/image/image-onedrive1-3.jpg)<br>

Step2. 接著請在 Source 與 Destination 的 Microsoft 365 Admin Center 中，建立一組安全性群組，並將名稱設定為 ***MigrationWiz*** <br>

設定完成後，將用來作為BitTitan驗證憑據的管理員加入成為 ***成員***<br>

Step3. 接著請以全域管理者身分，授權BitTitan API的存取權，透過全域管理員身分登入 BitTitan 所提供的授權連結，請參考 BitTitan 官方網站 -<br>

https://help.bittitan.com/hc/en-us/articles/360038153373-Using-App-based-Authentication<br>

點擊上述連結後，以管理員身分點選 ***接受*** -<br>

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/image/image-onedrive1-9.jpg)<br>

---

