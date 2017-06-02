---
title: "Практическое руководство. Определение установленных обновлений платформы .NET Framework | Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
caps.latest.revision: 6
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: dc1c456c71efb3cc6e60a8fdc77384e65975f110
ms.openlocfilehash: 6237bdaf1d12743bee71633acf8cef69c21b414e
ms.contentlocale: ru-ru
ms.lasthandoff: 05/15/2017

---
# <a name="how-to-determine-which-net-framework-updates-are-installed"></a>Практическое руководство.Определение установленных обновлений платформы .NET Framework
Установленные обновления для каждой версии .NET Framework на компьютере, перечислены в реестре Windows. Для просмотра этих сведений можно использовать редактор реестра (regedit.exe).  
  
 В редакторе реестра версии .NET Framework и установленные обновления для каждой версии хранятся в разных подразделах. Сведения об обнаружении номеров установленных версий см. в статье [Практическое руководство. Определение установленных версий .NET Framework](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md). Сведения об установке .NET Framework см. в [руководстве по установке](../../../docs/framework/install/guide-for-developers.md).  
  
### <a name="to-find-installed-updates"></a>Поиск установленных обновлений  
  
1.  Откройте программу **regedit.exe**. В Windows 8 и более поздних версиях откройте рабочий стол и введите имя. В более ранних версиях Windows, в меню **Пуск** щелкните **Выполнить**, а затем в поле **Открыть** введите **regedit.exe**.  
  
     Для запуска regedit.exe необходимы учетные данные администратора.  
  
2.  В редакторе реестра откройте следующий подраздел:  
  
     HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates  
  
     Установленные обновления перечислены в подразделах, соответствующих версии .NET Framework, к которой они относятся. Каждому обновлению присваивается номер базы знаний Microsoft (KB).  
  
## <a name="example"></a>Пример  
 В следующем примере кода программным образом определяются обновления .NET Framework, установленные на компьютере. Для запуска этого примера требуются права администратора.  
  
 [!code-csharp[ListUpdates#1](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs#1)] [!code-vb[ListUpdates#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb#1)]  
  
 Выходные данные этого примера выглядят примерно следующим образом:  
  
```  
  
Microsoft .NET Framework 3.5 SP1  
  KB953595  Hotfix for Microsoft .NET Framework 3.5 SP1 (KB953595)  
  SP1  
    KB2657424  Security Update for Microsoft .NET Framework 3.5 SP1 (KB2657424)  
    KB958484  Hotfix for Microsoft .NET Framework 3.5 SP1 (KB958484)  
    KB963707  Update for Microsoft .NET Framework 3.5 SP1 (KB963707)  
Microsoft .NET Framework 4 Client Profile  
  KB2160841  Security Update for Microsoft .NET Framework 4 Client Profile (KB2160841)  
  KB2446708  Security Update for Microsoft .NET Framework 4 Client Profile (KB2446708)  
  KB2468871  Update for Microsoft .NET Framework 4 Client Profile (KB2468871)  
  KB2478663  Security Update for Microsoft .NET Framework 4 Client Profile (KB2478663)  
  KB2518870  Security Update for Microsoft .NET Framework 4 Client Profile (KB2518870)  
  KB2533523  Update for Microsoft .NET Framework 4 Client Profile (KB2533523)  
  KB2539636  Security Update for Microsoft .NET Framework 4 Client Profile (KB2539636)  
  KB2572078  Security Update for Microsoft .NET Framework 4 Client Profile (KB2572078)  
  KB2633870  Security Update for Microsoft .NET Framework 4 Client Profile (KB2633870)  
  KB2656351  Security Update for Microsoft .NET Framework 4 Client Profile (KB2656351)  
Microsoft .NET Framework 4 Extended  
  KB2416472  Security Update for Microsoft .NET Framework 4 Extended (KB2416472)  
  KB2468871  Update for Microsoft .NET Framework 4 Extended (KB2468871)  
  KB2487367  Security Update for Microsoft .NET Framework 4 Extended (KB2487367)  
  KB2533523  Update for Microsoft .NET Framework 4 Extended (KB2533523)  
  KB2656351  Security Update for Microsoft .NET Framework 4 Extended (KB2656351)  
  
```  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Определение установленных версий платформы .NET Framework](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)   
 [Руководство по установке](../../../docs/framework/install/guide-for-developers.md)   
 [Версии и зависимости](../../../docs/framework/migration-guide/versions-and-dependencies.md)

