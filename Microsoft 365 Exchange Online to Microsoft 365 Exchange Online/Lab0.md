# Microsoft 365 Exchange Online to Microsoft 365 Exchange Online

## 情境說明與策略

一般遷移會最常提到的一定是來源端(Source)與目的端(Destination)兩個重要的環境，

因此本篇文章也將會模擬各一組的Source與Destination來進行細部解析，

由於是Tenant to Tenant的Migration，因此在最初的狀態之下 Destination 一定不會與 Source 的網域相同，

而 Microsoft 365 預設則會提供 xxx.onmicrosoft.com 的預設網域，因此多半 Destination 將會以此網域作為承接。

此時必須要特別留意，而在遷移的策略上，我們會將兩個環境分別設定至 BitTitan 之上、各自成為1組Endpoint，

再將2組EndPoint互相連接成一個Project之後，在Project之中進行不同使用者帳號的資料遷移(Task)。

通常遷移策略上，我們依據這個流程進行完成的遷移作業 - 

> Verify credenitial > Trial Migration > Full-Migration > Retry Error > MX Record Change > Pre-Stage Migration

這些流程代表的觀念分別是 - 

- Verify credential - 測試來源與目的的憑證是否正確
- Trial Migration - 測試遷移來評估遷移速率與正確率
- Full Migration - 完整遷移所有資料
- Retry Error - 遷移完成後的錯誤重試
- MX Record Change - 讓使用者開始使用新的One Drive，這項操作是透過Microsoft 365更換網域與MX Record
- Pre-Stage Migration - 進行階段性遷移以彌補切換期間的文件更新

> Tips. Tenant to Tenant Migration 在 Microsoft 365之中，一定會出現Down-time，因此建議離峰時間執行，同時也可預先修改DNS TTL、加速DNS的作用與更新時間。

關於上述的遷移策略，將於後續的章節之中，逐一說明遷移過程所需要執行的操作步驟與注意事項。

---

前往 [Lab1 環境與事前確認](https://github.com/MarkChang-Core/BitTitan/blob/main/Microsoft%20365%20Exchange%20Online%20to%20Microsoft%20365%20Exchange%20Online/Lab1.md)。
