# Microsoft 365 Exchange Online to Microsoft 365 Exchange Online Strategy
針對Tenant to Tenant 的郵件遷移，會是最常出現的需求之一，郵件遷移至今已經是相當成熟的技術，<br>
因此多數執行者都在致力將遷移流程更加平滑、對使用者的影響也要降到最低，因此通常遷移上可分類為 - <br>

> **Speed Migration**
> Speed Migration的觀念是快速先遷移小部分的信件(例如近一個月)，由於遷移的速度會非常快，<br>
> 因此在初次遷移完成後，即可切換MX Record，讓使用者恢復正常使用，後續信件則再緩慢地進行遷移。<br>

> **Big Band Migration**
> Big Band Migration的觀念是一次性的大量遷移所有的使用者信件，雖說遷移時間較長，但設定上較為單純，<br>
> 缺點則是當單次遷移的數據量過大時容易出現較多的錯誤需要修復，通常會在遷移完成後再次執行，以確保無遺漏信件。<br>
<br>
綜上所述，一般信件遷移流程會對應MX Record切換的時間進行流程的操作，但至少都需要進行兩次的遷移，<br>
<br>
至多則可視遷移規劃耗費的時間進行估計。<br>
