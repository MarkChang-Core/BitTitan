# Microsoft 365 Exchange Online to Microsoft 365 Exchange Online

## Lab 2 - 建立遷移項目

當完成Source與Destination的遷移準備之後，接下來就需要開始進行遷移了，你可以按照以下步驟進行 - 

Step 1. 創建專案(Project)，登入BitTitan的 [MigrationWiz](https://migrationwiz.bittitan.com/app/) 後，點選畫面中的 ***創建項目(Create Project)***

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/Microsoft%20365%20Exchange%20Online%20to%20Microsoft%20365%20Exchange%20Online/Image/image2-1.jpg)<br>

Step 2. 在項目類型之中，選擇需要建立的項目類型，選擇 ***Create a Mailbox Project*** -

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/Microsoft%20365%20Exchange%20Online%20to%20Microsoft%20365%20Exchange%20Online/Image/image2-2.jpg)<br>

Step 3. 在項目信息中，幫接下來要進行的遷移項目建立一個好記名稱，並且給定客戶名稱

> Tips. 若你的身分是系統整合商，且正協助客戶進行遷移，未來也可能長期使用BitTitan，建議你可以針對不同客戶建立客戶名稱，
但若是你的身分為終端客戶，那麼選擇Default也是可以的選項。 

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/Microsoft%20365%20Exchange%20Online%20to%20Microsoft%20365%20Exchange%20Online/Image/image2-3.jpg)<br>

Step 4. 在Source建立頁面，選擇 ***新建(Create)***，接著給定Source Endpoint一個好記名稱，並將端點類型選擇為 ***Microsoft 365***，並輸入Administrator登入資訊 -

> Tips. 於此處可以選擇 ***Provide Credentials*** 或 ***Do not provide credentials*** 兩者的差異如下 - <br>
> ***Provide Credentials*** - 往後於此項目的遷移任務中，均依據您當前提供的管理者登入資訊。<br>
> ***Do not provide credentials*** - 往後於此項目的遷移任務中，均需要額外提供每一個使用者帳號的登入資訊作為驗證。<br>

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/Microsoft%20365%20Exchange%20Online%20to%20Microsoft%20365%20Exchange%20Online/Image/image2-4.jpg)<br>

Step 5. 在Destination的設定與Source相同，唯一差別在於這時的Administrator更改為Destination了 -

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/Microsoft%20365%20Exchange%20Online%20to%20Microsoft%20365%20Exchange%20Online/Image/image2-5.jpg)<br>

Step 6. Source與Destination均設定完成後，由於當前情境是Tenant to Tenant的Migration，因此會出現 ***TENANT TO TENANT MIGRATION***的頁面，可以選擇是否開啟。

> Tips. 建議謹慎評估這項功能是否開啟，當開啟之後Source與Destination將共存，信件路由、Free/Busy狀態等均可透過BitTitan於兩個端點間流通，
> 但，原先已創建完成的Destination將遭到移除並重新創建<br>
> 此外，這個功能僅可提供給 Source 與 Destination 網域 ***不相同*** 的情境適用。

![GITHUB](https://github.com/MarkChang-Core/BitTitan/blob/main/Microsoft%20365%20Exchange%20Online%20to%20Microsoft%20365%20Exchange%20Online/Image/image2-6.jpg)<br>

---

當前述設定完成後，點選保存項目即創建完成，可前往 [Lab3 開始進行遷移](https://github.com/MarkChang-Core/BitTitan/blob/main/Microsoft%20365%20Exchange%20Online%20to%20Microsoft%20365%20Exchange%20Online/Lab3.md)。
