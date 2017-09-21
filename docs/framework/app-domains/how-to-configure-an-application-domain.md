---
title: "Практическое руководство. Настройка домена приложения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application domains, configuring
- ApplicationBase property
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4f8c91a11deac63e2ad44628a609ed4ca6501e84
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-configure-an-application-domain"></a>Практическое руководство. Настройка домена приложения
Сведения о настройке нового домена приложения среде CLR можно предоставить с помощью класса <xref:System.AppDomainSetup>. При создании собственных доменов приложений наиболее важным свойством является <xref:System.AppDomainSetup.ApplicationBase%2A>. Другие свойства **AppDomainSetup** используются главным образом узлами среды выполнения для настройки определенного домена приложения.  
  
 Свойство **ApplicationBase** определяет корневой каталог приложения. Когда среде выполнения требуется разрешить запрос о типе, она выполняет поиск сборки, содержащей тип в каталоге, заданном свойством **ApplicationBase**.  
  
> [!NOTE]
>  Новый домен приложения наследует только свойство **ApplicationBase** своего создателя.  
  
 В следующем примере создается экземпляр класса **AppDomainSetup**, используемого для создания домена приложения, производится вывод данных на консоль и затем выгрузка домена приложения.  
  
## <a name="example"></a>Пример  
 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)] [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)] [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## <a name="see-also"></a>См. также  
 [Программирование с использованием доменов приложений](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [Использование доменов приложений](../../../docs/framework/app-domains/use.md)

