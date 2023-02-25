# winget Aracının Kullanımı ile Windows Terminal ve oh-my-posh Yüklemesi

## Windows için
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

`Get-PSReadLineOption` komut çıktısının `HistorySavePath` özelliği girilen komutların hangi log dosyası içerisinde tutulduğunun yol (path) bilgisini verir.

[oh-my-posh Themes](https://ohmyposh.dev/docs/themes)
Varolan Theme leri görüntülemek için aşağıdaki komut kullanılır.
```
Get-PoshThemes
```

Windows Terminal `CTRL + SHIFT + Mouse Scroll Wheel` (Farenin kaydırma tekerleği) Windows Terminal ekranının arka planını transparan yapmak için kullanılabilir.

## Linux için
[Set up your terminal on Linux](https://ohmyposh.dev/docs/installation/linux)
```
$ sudo wget https://github.com/JanDeDobbeleer/oh-my-posh/releases/latest/download/posh-linux-amd64 -O /usr/local/bin/oh-my-posh
$ sudo chmod +x /usr/local/bin/oh-my-posh
```

Teheme için
```
$ mkdir ~/.poshthemes
$ wget https://github.com/JanDeDobbeleer/oh-my-posh/releases/latest/download/themes.zip -O ~/.poshthemes/themes.zip
$ unzip ~/.poshthemes/themes.zip -d ~/.poshthemes
$ chmod u+rw ~/.poshthemes/*.omp.*
$ rm ~/.poshthemes/themes.zip
```
```
$ eval "$(oh-my-posh init bash --config ~~/.poshthemes/jandedobbeleer.omp.json)"
$ eval "$(oh-my-posh init bash --config ~/.poshthemes/powerlevel10k_rainbow.omp.json)"
$ exec bash
```
# Tutorial: Set up a custom prompt for PowerShell or WSL with Oh My Posh
[Tutorial: Set up a custom prompt for PowerShell or WSL with Oh My Posh](https://learn.microsoft.com/en-us/windows/terminal/tutorials/custom-prompt-setup)

[Terminal-Icons github repo](https://github.com/devblackops/Terminal-Icons)
```
> Install-Module -Name Terminal-Icons -Repository PSGallery
> Import-Module -Name Terminal-Icons
> code $PROFILE

Import-Module -Name Terminal-Icons
```

#
[Appearance settings in Windows Terminal](https://learn.microsoft.com/en-us/windows/terminal/customize-settings/appearance)

```
eval "$(oh-my-posh init bash --config ~/jandedobbeleer.omp.json)"

```
