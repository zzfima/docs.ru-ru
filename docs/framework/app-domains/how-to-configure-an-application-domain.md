---
title: Практическое руководство. Настройка домена приложения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, configuring
- ApplicationBase property
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 012f0220afa0e444d68af5998fb2492a03a371d8
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2018
ms.locfileid: "50183169"
---
# <a name="how-to-configure-an-application-domain"></a>Практическое руководство. Настройка домена приложения
Сведения о настройке нового домена приложения среде CLR можно предоставить с помощью класса <xref:System.AppDomainSetup>. При создании собственных доменов приложений наиболее важным свойством является <xref:System.AppDomainSetup.ApplicationBase%2A>. Другие свойства **AppDomainSetup** используются главным образом узлами среды выполнения для настройки определенного домена приложения.  
  
 Свойство **ApplicationBase** определяет корневой каталог приложения. Когда среде выполнения требуется разрешить запрос о типе, она выполняет поиск сборки, содержащей тип в каталоге, заданном свойством **ApplicationBase**.  
  
> [!NOTE]
>  Новый домен приложения наследует только свойство **ApplicationBase** своего создателя.  
  
 В следующем примере создается экземпляр класса **AppDomainSetup**, используемого для создания домена приложения, производится вывод данных на консоль и затем выгрузка домена приложения.  
  
## <a name="example"></a>Пример  
 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## <a name="see-also"></a>См. также  
- [Программирование с использованием доменов приложений](application-domains.md#programming-with-application-domains)  
- [Использование доменов приложений](../../../docs/framework/app-domains/use.md)
