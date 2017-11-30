---
title: "Извлечение сведений о настройке из домена приложения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- AppDomainSetup object
- retrieving setup information
- application domains, retrieving setup information
ms.assetid: 5cdb12ae-1e37-4a62-8ec7-93d6dcc6e8d9
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ed6674580649e645ea3e647fa00682f2545255e9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-setup-information-from-an-application-domain"></a>Извлечение сведений о настройке из домена приложения
Каждый экземпляр домена приложения содержит свойства и сведения <xref:System.AppDomainSetup>. Сведения о настройке можно получить из домена приложения с помощью класса <xref:System.AppDomain?displayProperty=nameWithType>. Этот класс предоставляет несколько членов, извлекающих сведения конфигурации домена приложения.  
  
 Кроме того, для получения сведений о настройке домена приложения можно выполнить запрос объекта **AppDomainSetup**, который был передан в домен при его создании.  
  
 В следующем примере создается домен приложения и выполняется вывод значений нескольких его членов на консоль.  
  
 [!code-cpp[AppDomain_Setup#2](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source2.cpp#2)]
 [!code-csharp[AppDomain_Setup#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source2.cs#2)]
 [!code-vb[AppDomain_Setup#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source2.vb#2)]  
  
 В следующем примере для домена приложения задаются и извлекаются сведения о настройке. Обратите внимание, что `AppDomain.SetupInformation.ApplicationBase` получает сведения о конфигурации.  
  
 [!code-cpp[AppDomain_Setup#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source3.cpp#3)]
 [!code-csharp[AppDomain_Setup#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source3.cs#3)]
 [!code-vb[AppDomain_Setup#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source3.vb#3)]  
  
## <a name="see-also"></a>См. также  
 [Программирование с использованием доменов приложений](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131)  
 [Использование доменов приложений](../../../docs/framework/app-domains/use.md)
