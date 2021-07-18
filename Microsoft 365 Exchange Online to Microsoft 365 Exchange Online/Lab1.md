# Microsoft 365 Exchange Online to Microsoft 365 Exchange Online

## 情境說明與策略

一般遷移會最常提到的一定是來源端(Source)與目的端(Destination)兩個重要的環境，

因此本篇文章也將會模擬各一組的Source與Destination來進行細部解析，資訊如下 - 

```Source - user01@bittitan-lab.com```

```Destination - user01@bittitandestination.onmicrosoft.com```

由於是Tenant to Tenant的Migration，因此在最初的狀態之下 Destination 一定不會與 Source 的網域相同，

而 Microsoft 365 預設則會提供 xxx.onmicrosoft.com 的預設網域，因此多半 Destination 將會以此網域作為承接。

此時必須要特別留意，而在遷移的策略上，我們會將兩個環境分別設定至 BitTitan 之上、各自成為1組Endpoint，

再將2組EndPoint互相連接成一個Project之後，在Project之中進行不同使用者帳號的資料遷移(Task)。

通常遷移策略上，我們依據這個流程進行完成的遷移作業 - 

```Verify credenitial > Trial Migration > Full-Migration > Retry Error > MX Record Change > Pre-Stage Migration```

## 環境與事前確認

## 準備Source環境

## 準備Desination 環境

## 開始遷移

## 遷移完成後
