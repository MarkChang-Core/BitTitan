UseApplicationPermission=1

DestPersonalSiteIsProvisioned=1

ForceOneDriveNonGlobalAdminAuthExport=1

Connect-SPOService -Url https://bittitandestination-admin.sharepoint.com -Credential admin2@bittitandestination.onmicrosoft.com

Get-Content -path "C:\list.txt" | ForEach-Object { Set-MsolUser -UserPrincipalName $_ -BlockCredential $False }

$Credential = Get-Credential
Connect-MsolService -Credential $Credential
Connect-SPOService -Credential $Credential -Url https://bittitandestination-admin.sharepoint.com

$list = @()
#Counters
$i = 0


#Get licensed users
$users = Get-MsolUser -All | Where-Object { $_.islicensed -eq $true }
#total licensed users
$count = $users.count

foreach ($u in $users) {
    $i++
    Write-Host "$i/$count"

    $upn = $u.userprincipalname
    $list += $upn

    if ($i -eq 199) {
        #We reached the limit
        Request-SPOPersonalSite -UserEmails $list -NoWait
        Start-Sleep -Milliseconds 655
        $list = @()
        $i = 0
    }
}

if ($i -gt 0) {
    Request-SPOPersonalSite -UserEmails $list -NoWait
}
