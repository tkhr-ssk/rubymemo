# Windows Tips


## 便利script


### Linuxのtimeコマンドみたいに、コマンドの実行時間を調べる

```
@Powershell -Command ^
  "$w=New-Object System.Diagnostics.StopWatch;$w.Start();Invoke-Command{%*};$w.Stop();\"Elapsed Seconds: \"+$w.Elapsed.TotalSeconds"
```

### micro sleep

```
@Powershell -Command "Start-Sleep -m %*"
```
