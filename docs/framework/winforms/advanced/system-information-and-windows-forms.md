---
title: Информация о системе и Windows Forms
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
ms.openlocfilehash: 2edc2e867259f8884467c3d5b0ae3d22ba391a77
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380109"
---
# <a name="system-information-and-windows-forms"></a><span data-ttu-id="18f6a-102">Информация о системе и Windows Forms</span><span class="sxs-lookup"><span data-stu-id="18f6a-102">System Information and Windows Forms</span></span>
<span data-ttu-id="18f6a-103">Иногда бывает необходимо собрать сведения о компьютере, на котором приложение выполняется на для принятия решений в коде.</span><span class="sxs-lookup"><span data-stu-id="18f6a-103">Sometimes it is necessary to gather information about the computer that your application is running on in order to make decisions in your code.</span></span> <span data-ttu-id="18f6a-104">Например возможно, функция, которая применяется только при подключении к конкретному сетевому домену; в этом случае требуется способ определения домена и отключить функцию, если домен не существует.</span><span class="sxs-lookup"><span data-stu-id="18f6a-104">For example, you might have a function that is only applicable when connected to a particular network domain; in this case you would need a way to determine the domain and disable the function if the domain is not present.</span></span>  
  
 <span data-ttu-id="18f6a-105">Можно использовать в приложениях Windows Forms <xref:System.Windows.Forms.SystemInformation> класс, чтобы определить количество сведения о компьютере во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="18f6a-105">Windows Forms applications can use the <xref:System.Windows.Forms.SystemInformation> class to determine a number of things about a computer at run time.</span></span> <span data-ttu-id="18f6a-106">В следующем примере показано использование <xref:System.Windows.Forms.SystemInformation> класса для извлечения <xref:System.Windows.Forms.SystemInformation.UserName%2A> и <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span><span class="sxs-lookup"><span data-stu-id="18f6a-106">The following example demonstrates using the <xref:System.Windows.Forms.SystemInformation> class to retrieve the <xref:System.Windows.Forms.SystemInformation.UserName%2A> and <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span></span>  
  
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
  
 <span data-ttu-id="18f6a-107">Все члены <xref:System.Windows.Forms.SystemInformation> , доступны только для чтения; невозможно изменить параметры пользователя.</span><span class="sxs-lookup"><span data-stu-id="18f6a-107">All members of the <xref:System.Windows.Forms.SystemInformation> class are read-only; you cannot modify a user's settings.</span></span> <span data-ttu-id="18f6a-108">Существует более 100 членов класса, возвращение сведений обо всем из число мониторов, подключенные к компьютеру (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) для интервала между значками в проводнике Windows (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> и <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).</span><span class="sxs-lookup"><span data-stu-id="18f6a-108">There are over 100 members of the class, returning information on everything from the number of monitors attached to the computer (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) to the spacing of icons in Windows Explorer (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> and <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).</span></span>  
  
 <span data-ttu-id="18f6a-109">Некоторые из наиболее полезными членами <xref:System.Windows.Forms.SystemInformation> класс включать <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, и <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-109">Some of the more useful members of the <xref:System.Windows.Forms.SystemInformation> class include <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, and <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18f6a-110">См. также</span><span class="sxs-lookup"><span data-stu-id="18f6a-110">See also</span></span>

- <xref:System.Windows.Forms.SystemInformation>
- [<span data-ttu-id="18f6a-111">Управление питанием в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="18f6a-111">Power Management in Windows Forms</span></span>](power-management-in-windows-forms.md)
