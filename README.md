# Fuck Microsoft Edge Game Assist

> I don’t need to be redirected to a browser to look up guides when I’m playing games. Moreover, Microsoft doesn’t give users the option to choose and force-installs Game Assist, which is very frustrating for me.

## Tutorial

1. Check Game Assist installation
<img alt="Image" src="./img/Capture1.PNG" style="height: 100%; width: auto;" />

2. Open Task Scheduler
    - Press Win + R → type taskschd.msc → press Enter.
<img alt="Image" src="./img/Capture2.PNG" style="height: 100%; width: auto;" />

3. Create a New Task
    - Click Create Task (not “Create Basic Task”) on the right-hand side.

4. General Settings
    - Name it: Run fuck-ms.ps1 at startup
    - Check Run with highest privileges.
    - Configure for: select your version of Windows.
<img alt="Image" src="./img/Capture3.PNG" style="height: 100%; width: auto;" />

5. Trigger Settings
    - Go to the Triggers tab → click New.
    - Choose At startup → click OK.
<img alt="Image" src="./img/Capture4.PNG" style="height: 100%; width: auto;" />

6. Action Settings
    - Go to the Actions tab → click New.
    - Action: Start a program.
    -  Program/script: `powershell.exe`
    - Add arguments: `-ExecutionPolicy Bypass -File "Path\to\your\script\fuck-ms.ps1"`
    - Start in (optional): `Path\to\your\script`
<img alt="Image" src="./img/Capture5.PNG" style="height: 100%; width: auto;" />

7. Conditions/Settings
    - Uncheck options like “Start the task only if the computer is on AC power” or “Start only if the computer is idle.”
<img alt="Image" src="./img/Capture6.PNG" style="height: 100%; width: auto;" />

8. Save the Task
    - Click OK
    - Restart your computer to test if the script runs at startup.
<img alt="Image" src="./img/Capture7.PNG" style="height: 100%; width: auto;" />

## Script

Just: 

```powershell
Get-AppxPackage -AllUsers -Name Microsoft.Edge.GameAssist | Remove-AppxPackage 
```