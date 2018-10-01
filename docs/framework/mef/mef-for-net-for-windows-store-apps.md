---
title: 'Managed Extensibility Framework для .NET: приложения из магазина Windows Store'
ms.date: 03/30/2017
ms.assetid: 7667770e-d163-4ad6-a303-085cf73db2f2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9cb7807fbfc1fbaf039fd7aef04331210dfa7cfa
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47089939"
---
# <a name="mef-for-net-for-windows-store-apps"></a>Managed Extensibility Framework для .NET: приложения из магазина Windows Store
Пространство имен <xref:System.Composition?displayProperty=nameWithType> и его дочерние пространства содержат типы для разработки расширяемых приложений для [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] с использованием Managed Extensibility Framework (MEF). Эти пространства имен являются частью подмножества [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] для операционной системы [!INCLUDE[win8](../../../includes/win8-md.md)].  
  
 Они не входят в состав основной библиотеки классов, распространяемой с платформой .NET Framework. Чтобы установить эти пространства имен, откройте проект в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], выберите в меню **Проект** пункт **Управление пакетами NuGet** и найдите в Интернете пакет Microsoft.Composition.  
  
-   <xref:System.Composition?displayProperty=nameWithType> предоставляет классы, которые составляют ядро MEF для приложений [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)].  
  
-   <xref:System.Composition.Convention?displayProperty=nameWithType> предоставляет типы, поддерживающие использование MEF с моделью конфигурации на основе соглашений.  
  
-   <xref:System.Composition.Hosting?displayProperty=nameWithType> предоставляет типы MEF, которые могут пригодиться разработчикам ведущих приложений.  
  
-   <xref:System.Composition.Hosting.Core?displayProperty=nameWithType> предоставляет типы MEF, которые использует обработчик композиции.  
  
 Дополнительные сведения о платформе [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] и список входящих в нее пространств имен и типов см. в статье [Обзор приложений .NET для Магазина Windows](https://go.microsoft.com/fwlink/p/?LinkID=238312) в Центре разработки для Windows.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о платформе .NET для приложений Магазина Windows](https://go.microsoft.com/fwlink/p/?LinkID=238312)  
 [Поддерживаемые API .NET для приложений Магазина Windows](https://go.microsoft.com/fwlink/p/?LinkID=247912)  
 [Managed Extensibility Framework (MEF)](../../../docs/framework/mef/index.md)
