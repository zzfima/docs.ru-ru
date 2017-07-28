---
title: "System Information and Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "domain names, retrieving"
  - "SystemInformation class [Windows Forms]"
  - "user names, retrieving"
  - "system information [Windows Forms]"
ms.assetid: 30cf43a3-8cb2-4ff3-862b-6c34576616a8
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# System Information and Windows Forms
Иногда бывает необходимо собрать сведения о компьютере, на котором выполняется приложение, чтобы принять решения в коде.  Например, программа может содержать функцию, которая работает только при подключении к конкретному сетевому домену; в этом случае необходим способ определить наличие домена и отключить функцию, если домен отсутствует.  
  
 Приложения Windows Forms позволяют получить сведения о компьютере во время выполнения с помощью класса <xref:System.Windows.Forms.SystemInformation>.  В следующем примере показано использование класса <xref:System.Windows.Forms.SystemInformation> для получения свойств <xref:System.Windows.Forms.SystemInformation.UserName%2A> и <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:  
  
```vb  
Dim User As String = Windows.Forms.SystemInformation.UserName  
Dim Domain As String = Windows.Forms.SystemInformation.UserDomainName  
  
MessageBox.Show("Good morning " & User & ". You are connected to " _  
& Domain)  
  
```  
  
```csharp  
string User = SystemInformation.UserName;  
string Domain = SystemInformation.UserDomainName;  
  
MessageBox.Show("Good morning " + User + ". You are connected to " _  
+ Domain)  
```  
  
 Все члены класса <xref:System.Windows.Forms.SystemInformation> доступны только для чтения; параметры пользователя изменить нельзя.  В классе определено более 100 членов, возвращающих самые разнообразные сведения — от числа мониторов, подключенного к компьютеру \(<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>\) до интервала между значками в проводнике Windows \(<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> и <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>\).  
  
 Наиболее полезными членами класса <xref:System.Windows.Forms.SystemInformation> являются <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> и <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.  
  
## См. также  
 <xref:System.Windows.Forms.SystemInformation>   
 [Power Management in Windows Forms](../../../../docs/framework/winforms/advanced/power-management-in-windows-forms.md)