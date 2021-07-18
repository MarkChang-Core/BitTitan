# Microsoft 365 Exchange Online to Microsoft 365 Exchange Online

## Lab3 開始進行遷移

當完成項目設定後即可開始新增遷移任務，此處的每一個Items都可視為一個使用者的遷移作業，詳細新增方式與說明如下參考。

### 新增Items 方式 -

BitTitan 提供新增Items的方式共有 4 種，但因應Tenant to Teanant的情境，因此本文中僅會說明 3 種，分別是 -<br>

#### 1. Quick Add -

此功能為快速添加，點選後可直接輸入Source與其對應的Destination，並且快速加入一組Item<br>

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/Microsoft%20365%20Exchange%20Online%20to%20Microsoft%20365%20Exchange%20Online/Image/image3-1.jpg)<br>

#### 2. 批量添加 -
 
透過此功能可一次性以CSV檔案新增大量的使用者，點選後可以下載範例的CSV檔案，接著可以利用 [Lab1](https://github.com/MarkChang-Core/BitTitan/blob/main/Microsoft%20365%20Exchange%20Online%20to%20Microsoft%20365%20Exchange%20Online/Lab1.md) 所蒐集的資料進行新增。<br>

> Tips. 此處無論是否於Source或Destination端點創建時輸入Administrastor登入資訊，此處均可不需輸入 ***Password***，但 ***Email*** 與 ***Login Name*** 是必要的。

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/Microsoft%20365%20Exchange%20Online%20to%20Microsoft%20365%20Exchange%20Online/Image/image3-2.jpg)<br>

#### 3. Autodiscover Items -

如果透過Autodiscover，會非常節省人力的方式來新增使用者帳號，但其方式主要是自動尋找Source的UPN，並對應上Destination，

換言之若你的情境中Source與Destination是完全不同的UPN，那麼這個方式將不適合你使用。

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/Microsoft%20365%20Exchange%20Online%20to%20Microsoft%20365%20Exchange%20Online/Image/image3-3.jpg)<br>

---

在依據你所需要的方式建立完任務之後，接下來就可以開始進行遷移的項目，

Step 1. 點選工具列中的 ***Add*** 以情境需要的方式新增 Items。

Step 2. 勾選(或全選)Items後，點選工具列中的 ***Apply Licenses*** 分配授權給予 Items

> Tips. 使用者授權可以置換，但主要跟隨Source，一旦Source執行過Pre-Stage Migration 或 Full Migration之後，便無法再做置換

Step 2. 等待Items建立完成後，勾選(或全選)Items後，點選工具列中 ***Start*** 並依情境需要選擇後，開始進行遷移。

關於 Items 的執行方式，可以分類為 -<br>
- Verify Credentials - 測試Source與Destination是否正確，一般若是通過此項，即代表設定完成<br>
- Trial Migration - 嘗試遷移Source當中的前10個物件(Object)或是前10MB的物件(Object)，通常用於測試遷移速率<br>
- Pre-Stage Migration - 遷移指定時間區間中的物件<br>
- Full Migration - 完整遷移所有資料<br>
- Retry Errors - 針對已執行完成一次完整遷移的Items中產生的錯誤進行重試<br>

> Tips. 在Verify Credentials 與 Trial Migration 是不需要購買License即可進行的。
