# Усовершенствования отладки сценариев PowerShell

В PowerShell 5.0 было внесено несколько усовершенствований, направленных на улучшение процедуры отладки.

## Команда "Прервать все"

Консоль PowerShell и интегрированная среда сценариев Windows PowerShell теперь позволяют переходить в режим отладчика при выполнении сценариев. Это работает как в локальных, так и в удаленных сеансах.

В окне консоли нажмите клавиши **CTRL+BREAK**.

В интегрированной среде сценариев нажмите клавиши **CTRL+B** или воспользуйтесь командой меню **Отладка -> Прервать все**.

## Удаленная отладка и удаленное редактирование файлов в интегрированной среде сценариев Windows PowerShell

Теперь среда Windows PowerShell позволяет открывать и редактировать файлы в удаленном сеансе, выполнив команду PSEdit.
Например, во время удаленного сеанса можно открыть файл для редактирования из командной строки, как показано ниже:

```powershell
[RemoteComputer1]: PS C:\> PSEdit C:\DebugDemoScripts\Test-GetMutex.ps1
```

Кроме того, можно вносить изменения и сохранять их в удаленном файле, который автоматически открывается в среде Windows PowerShell при попадании в точку останова.
Теперь можно выполнить отладку файла сценария, выполняемого на удаленном компьютере, отредактировать файл, чтобы исправить ошибку, а затем снова запустить обновленный сценарий.

## Расширенная отладка сценариев

Появились новые расширенные функции отладки, которые позволяют подключиться к любому процессу локального компьютера, загруженному в Windows PowerShell, и осуществить отладку произвольных пространств выполнения в нем.

### Отладка пространств выполнения

Были добавлены новые командлеты, позволяющие вывести список текущих пространств выполнения в процессе, а также подключить консоль Windows PowerShell или отладчик интегрированной среды сценариев к такому пространству для отладки сценариев:

-   Get-Runspace
-   Debug-Runspace
-   Enable-RunspaceDebug
-   Disable-RunspaceDebug
-   Get-RunspaceDebug

### Подключение к процессу, в котором размещается PowerShell

Теперь вы можете подключиться к любому процессу на компьютере компьютера, в котором загружен Windows PowerShell. Это можно сделать, перейдя в интерактивный сеанс с процессом, по аналогии со входом в интерактивный удаленный сеанс с помощью командлета Enter-PSSession:

-   Enter-PSHostProcess
-   Exit-PSHostProcess<!--HONumber=Mar16_HO2-->