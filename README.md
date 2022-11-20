# winget Aracının Kullanımı ile Windows Terminal ve oh-my-posh Yüklemesi
[Use the winget tool to install and manage applications](https://learn.microsoft.com/en-us/windows/package-manager/winget/) \
[upgrade command (winget)](https://learn.microsoft.com/en-us/windows/package-manager/winget/upgrade)
Powershell yönetici olarak çalıştırılıp aşağıdaki komutlar uygulanır. 
```
> winget upgrade
> winget upgrade --all
> winget install -e --id Microsoft.PowerShell
> winget list powershell
> winget list --id="{7a021f60-fb27-4c6c-8ddb-a94915da9fd8}"
> winget uninstall --id="{7a021f60-fb27-4c6c-8ddb-a94915da9fd8}"
> winget install -e --id Microsoft.WindowsTerminal
```
[oh-my-posh](https://ohmyposh.dev/)
```
> winget install JanDeDobbeleer.OhMyPosh -s winget
> oh-my-posh font install
> shutdown.exe -r
```
[Customize oh-my-posh](https://ohmyposh.dev/docs/installation/customize)
```
> oh-my-posh.exe init pwsh
> code $PROFILE
```
Default Theme kullanılacak ise aşağıdaki şekilde PROFILE dosyası içerisine yazılır.
```
(@(& 'C:/Users/User/AppData/Local/Programs/oh-my-posh/bin/oh-my-posh.exe' init pwsh --config='' --print) -join "`n") | Invoke-Expression
```
Belirli bir theme seçilecek ise aşağıdaki şekilde kullanılır.
```
(@(& 'C:/Users/User/AppData/Local/Programs/oh-my-posh/bin/oh-my-posh.exe' init pwsh --config='C:\Users\User\AppData\Local\Programs\oh-my-posh\themes\powerlevel10k_rainbow.omp.json' --print) -join "`n") | Invoke-Expression
```
Daha önce kullanılan komutları önerilerde liste şeklinde sunması için kullanılır.
```
Set-PSReadLineOption -PredictionSource History
Set-PSReadLineOption -PredictionViewStyle ListView
```
[oh-my-posh Themes](https://ohmyposh.dev/docs/themes)
Varolan Theme leri görüntülemek için aşağıdaki komut kullanılır.
```
Get-PoshThemes
```
