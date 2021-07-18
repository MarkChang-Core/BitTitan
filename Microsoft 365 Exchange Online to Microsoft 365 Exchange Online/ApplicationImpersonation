#### ApplicationImpersonation 設定

```Install-Module -Name ExchangeOnlineManagement```

```Import-Module ExchangeOnlineManagement```

```Set-ExecutionPolicy Unrestricted```

```$LiveCred = Get-Credential```

```$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell/ -Credential $LiveCred -Authentication Basic -AllowRedirection```

```Import-PSSession $Session```

```Enable-OrganizationCustomization```

```New-ManagementRoleAssignment -Role "ApplicationImpersonation" -User admin2@bittitan-lab.com```

```New-ManagementRoleAssignment -Role "ApplicationImpersonation" -User admin@bittitansource.onmicrosoft.com```
