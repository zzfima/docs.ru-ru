---
title: "Информация о системе и Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- domain names [Windows Forms], retrieving
- SystemInformation class [Windows Forms]
- user names [Windows Forms], retrieving
- system information [Windows Forms]
ms.assetid: 30cf43a3-8cb2-4ff3-862b-6c34576616a8
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6657556ffb49c19e6ffc3ef5462de341a93112b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="system-information-and-windows-forms"></a>Информация о системе и Windows Forms
Иногда бывает необходимо собрать сведения о компьютере, на котором приложение выполняется на для принятия решений в коде. Например возможно, функция, которая применяется только при подключении к конкретному сетевому домену; в этом случае необходим способ для определения домена и отключить функцию, если домен не существует.  
  
 Можно использовать в приложениях Windows Forms <xref:System.Windows.Forms.SystemInformation> класс, чтобы определить количество сведения о компьютере во время выполнения. В следующем примере показано использование <xref:System.Windows.Forms.SystemInformation> класса для извлечения <xref:System.Windows.Forms.SystemInformation.UserName%2A> и <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:  
  
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
  
 Все члены <xref:System.Windows.Forms.SystemInformation> класса доступны только для чтения; невозможно изменить параметры пользователя. Существует более 100 членов класса, возвращение сведений в любом из числа мониторов, подключенного к компьютеру (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) для интервала между значками в проводнике Windows (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> и <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).  
  
 Некоторые из наиболее полезными членами <xref:System.Windows.Forms.SystemInformation> класс включать <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, и <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.SystemInformation>  
 [Управление питанием в Windows Forms](../../../../docs/framework/winforms/advanced/power-management-in-windows-forms.md)
