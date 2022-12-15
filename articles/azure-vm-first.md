---
title: "Azure Cloud Shell で Windows VM を作る"
emoji: "⛅"
type: "tech"
topics: ["初心者","Azure"]
published: true
---


[クイック スタート - Azure PowerShell を使用して Windows VM を作成する - Azure Virtual Machines | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/virtual-machines/windows/quick-create-powershell)

## 手順

> Cloud Shell を開くには、コード ブロックの右上隅にある [使ってみる] を選択します。

ということで、上記 Learning 記事のコード ブロックの「使ってみる」から Cloud Shell を利用してみる。

![image.png](/images/2440c29e-ca69-4a98-f965-2be3ddb7de3d.png)


```powershell
PS /home/nobuko> New-AzResourceGroup -Name 'myResourceGroup' -Location 'EastAsia'

ResourceGroupName : myResourceGroup
Location          : eastasia
ProvisioningState : Succeeded
Tags              : 
ResourceId        : /subscriptions/64802ffd-86e1-4902-95e3-3741e722
                    750c/resourceGroups/myResourceGroup
```
Location だけ East Asia にしてみた。
User とパスワードをお好みのものに決める。


```powershell
New-AzVm `
    -ResourceGroupName 'myResourceGroup' `
    -Name 'myVM' `
    -Location 'EastAsia' `
    -VirtualNetworkName 'myVnet' `
    -SubnetName 'mySubnet' `
    -SecurityGroupName 'myNetworkSecurityGroup' `
    -PublicIpAddressName 'myPublicIpAddress' `
    -OpenPorts 80,3389
```



> Supply values for the following parameters:
Credential
User: e99h2121
Password for user e99h2121: ********

![image.png](/images/2524448f-fa09-2a83-956d-181082f64fec.png)

リソースが色々できあがった。


### 起動

```powershell
Invoke-AzVMRunCommand `
    -ResourceGroupName 'myResourceGroup' `
    -VMName 'myVM' -CommandId 'RunPowerShellScript' `
    -ScriptString 'Install-WindowsFeature `
    -Name Web-Server -IncludeManagementTools'
```

以下。

```powershell

PS /home/nobuko> Invoke-AzVMRunCommand `
>>     -ResourceGroupName 'myResourceGroup' `
>>     -VMName 'myVM' -CommandId 'RunPowerShellScript' `
>>     -ScriptString 'Install-WindowsFeature `
>>     -Name Web-Server -IncludeManagementTools'


Value[0]        : 
  Code          : ComponentStatus/StdOut/succeeded
  Level         : Info
  DisplayStatus : Provisioning succeeded
  Message       : Success Restart Needed Exit Code      Feature 
Result                           
------- -------------- ---------      --------------               
            
True    No             Success        {Common HTTP Features, 
Default Documen...


Value[1]        : 
  Code          : ComponentStatus/StdErr/succeeded
  Level         : Info
  DisplayStatus : Provisioning succeeded
  Message       : 
Status          : Succeeded
Capacity        : 0
Count           : 0


PS /home/nobuko> 
```

無事起動したら、 myPublicIpAddress の Public IP を利用して以下アクセスする。


### ブラウザから

![image.png](/images/c589ebe6-e1f0-999a-5c7f-42e0ee39e3a7.png)


### リモートデスクトップ接続から

![image.png](/images/ee86d705-a2d8-ce20-2131-16805fdb32da.png)

ここまでくればお遊び放題。


### 後片付け

```powershell
PS /home/nobuko> Remove-AzResourceGroup -Name 'myResourceGroup'

Confirm
Are you sure you want to remove resource group 'myResourceGroup'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y
```


## 参考

- [Azure での仮想マシン - Azure Virtual Machines | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/virtual-machines/)
- [Azure で Windows 仮想マシンを作成する - Training | Microsoft Learn](https://learn.microsoft.com/ja-jp/training/modules/create-windows-virtual-machine-in-azure/)
