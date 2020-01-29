---
title: Сведения о системе
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- domain names [Windows Forms], retrieving
- SystemInformation class [Windows Forms]
- user names [Windows Forms], retrieving
- system information [Windows Forms]
ms.assetid: 30cf43a3-8cb2-4ff3-862b-6c34576616a8
ms.openlocfilehash: a91e2fd8db0ef338ce30f89f11869f1b6698af3b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732589"
---
# <a name="system-information-and-windows-forms"></a>Информация о системе и Windows Forms
Иногда необходимо собрать сведения о компьютере, на котором выполняется приложение, чтобы принимать решения в коде. Например, у вас может быть функция, применимая только при подключении к определенному сетевому домену. в этом случае необходим способ определения домена и отключения функции, если домен отсутствует.  
  
 Windows Forms приложения могут использовать класс <xref:System.Windows.Forms.SystemInformation> для определения ряда вещей о компьютере во время выполнения. В следующем примере демонстрируется использование класса <xref:System.Windows.Forms.SystemInformation> для получения <xref:System.Windows.Forms.SystemInformation.UserName%2A> и <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:  
  
```vb  
Dim User As String = Windows.Forms.SystemInformation.UserName  
Dim Domain As String = Windows.Forms.SystemInformation.UserDomainName  
  
MessageBox.Show("Good morning " & User & ". You are connected to " _  
& Domain)  
```  
  
```csharp  
string User = SystemInformation.UserName;  
string Domain = SystemInformation.UserDomainName;  
  
MessageBox.Show("Good morning " + User + ". You are connected to "
+ Domain);
```  
  
 Все члены класса <xref:System.Windows.Forms.SystemInformation> доступны только для чтения; изменить параметры пользователя нельзя. Существует свыше 100 членов класса, возвращающая сведения обо всех мониторах, подключенных к компьютеру (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>), на расстояния значков в проводнике Windows (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> и <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).  
  
 Некоторые из наиболее полезных членов класса <xref:System.Windows.Forms.SystemInformation> включают <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>и <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.SystemInformation>
- [Управление питанием в Windows Forms](power-management-in-windows-forms.md)
