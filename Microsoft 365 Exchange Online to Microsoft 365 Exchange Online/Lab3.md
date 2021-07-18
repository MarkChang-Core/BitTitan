# Microsoft 365 Exchange Online to Microsoft 365 Exchange Online

## Lab3 開始進行遷移

當完成項目設定後即可開始新增遷移任務，此處的每一個Items都可視為一個使用者的遷移作業，詳細新增方式與說明如下參考。

### ***新增Items 方式 - ***

BitTitan 提供新增Items的方式共有 4 種，但因應Tenant to Teanant的情境，因此本文中僅會說明 3 種，分別是 -<br>

#### ***Quick Add - ***

此功能為快速添加，點選後可直接輸入Source與其對應的Destination，並且快速加入一組Item<br>

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/Microsoft%20365%20Exchange%20Online%20to%20Microsoft%20365%20Exchange%20Online/Image/image3-1.jpg)<br>

#### ***批量添加 - ***
 
透過此功能可一次性以CSV檔案新增大量的使用者，點選後可以下載範例的CSV檔案，接著可以利用 [Lab1](https://github.com/MarkChang-Core/BitTitan/blob/main/Microsoft%20365%20Exchange%20Online%20to%20Microsoft%20365%20Exchange%20Online/Lab1.md) 所蒐集的資料進行新增。<br>

> Tips. 此處無論是否於Source或Destination端點創建時輸入Administrastor登入資訊，此處均可不需輸入 ***Password***，但 ***Email*** 與 ***Login Name*** 是必要的。

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/Microsoft%20365%20Exchange%20Online%20to%20Microsoft%20365%20Exchange%20Online/Image/image3-2.jpg)<br>

#### ***Autodiscover Items - ***

Step 1. 點選畫面上方的 ***Add*** 以新增 Items。
