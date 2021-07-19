# Microsoft 365 Exchange Online to Microsoft 365 Exchange Online

## Lab3 - 建立遷移專案

### 1. 建立遷移專案

當完成Source與Destination的遷移準備之後，接下來就需要開始進行遷移了，你可以按照以下步驟進行 - 

Step 1. 創建專案(Project)，登入BitTitan的 [MigrationWiz](https://migrationwiz.bittitan.com/app/) 後，點選畫面中的 ***創建項目(Create Project)***

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/Microsoft%20365%20Exchange%20Online%20to%20Microsoft%20365%20Exchange%20Online/Image/image2-1.jpg)<br>

Step 2. 在項目類型之中，選擇需要建立的項目類型，選擇 ***Create a Document Project*** -

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/image/image-onedrive3-1.jpg)<br>

Step 3. 在項目信息中，幫接下來要進行的遷移項目建立一個好記名稱，並且給定客戶名稱後，點擊 下一步驟

> Tips. 若你的身分是系統整合商，且正協助客戶進行遷移，未來也可能長期使用BitTitan，建議你可以針對不同客戶建立客戶名稱，<br>
> 但若是你的身分為終端客戶，那麼選擇Default也是可以的選項。 

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/image/image-onedrive3-0.jpg)<br>

Step 4. 在Source Endpoint建立頁面，選擇 ***新建(Create)***，接著給定Source Endpoint一個好記名稱，<br>

並將端點類型選擇為 ***OneDrive for Business***，並輸入Administrator登入資訊，輸入完成後，點擊下一步驟 -

> Tips. 於此處可以選擇 ***Provide Credentials*** 或 ***Do not provide credentials*** 兩者的差異如下 - <br>
> ***Provide Credentials*** - 往後於此項目的遷移任務中，均依據您當前提供的管理者登入資訊作為驗證憑據。<br>
> ***Do not provide credentials*** - 往後於此項目的遷移任務中，均需要額外提供每一個使用者帳號的登入資訊作為驗證。<br>

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/image/image-onedrive3-2.jpg)<br>

Step 5. 在Destination Endpoint建立頁面，選擇 ***新建(Create)***，接著給定Source Endpoint好記名稱，並將端點選擇為 ***OneDrive for Business***，<br>

並輸入Administrator登入資訊後，需要輸入在 [Lab2](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/Lab2.md#1-azure-storage-account) 中建立的Azure Storage Account資訊 -

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/image/image-onedrive3-3.jpg)<br>

完成後點擊 ***保存項目*** 即完成設 項目建置。

---

###  2. 進階選項設定

完成項目建立之後，接著需要額外進行幾項必要參數的添加，方可開始進行遷移，操作步驟與參數如下 - 

Step 1. 進入方才建立完成的項目後，點擊畫面左上角的 ***編輯項目 > Advanced Options*** -

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/image/image-onedrive3-4.jpg)<br>

Step 2. 於 ***Support頁籤*** 中，逐一輸入以下參數後，點選 ***Save*** -<br>

```DestPersonalSiteIsProvisioned=1```<br>

```UseApplicationPermission=1```<br>

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/image/image-onedrive3-5.jpg)<br>

---

當前述設定完成後，點選保存項目即創建完成，可前往 [Lab4 開始遷移](https://github.com/MarkChang-Core/BitTitan/blob/main/OneDriveToOneDrive/Lab4.md)。
