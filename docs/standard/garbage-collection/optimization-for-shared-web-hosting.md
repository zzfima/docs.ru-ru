---
title: "Оптимизация совместного размещения веб-сайтов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- garbage collection, Web hosting
- garbage collection, optimizing
- garbage collection, shared Web hosting
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1f423d867d4fada075800650627c94f9d09e9e7a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="optimization-for-shared-web-hosting"></a>Оптимизация совместного размещения веб-сайтов
Если вы являетесь администратором сервера, совместно размещены несколько небольших веб-сайтов, можно оптимизировать производительность и увеличить емкость узла, добавив следующий код `gcTrimCommitOnLowMemory` параметру `runtime` узла в файле Aspnet.config в .NET каталог:  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
>  Данный параметр рекомендуется только для общих веб-сайта, в сценариях размещения.  
  
 Так как сборщик мусора оставляет память для будущих распределений, память может быть больше, чем минимально необходимые. Можно уменьшить этот объем, чтобы облегчить при высокую нагрузку на системную память. Уменьшение этого предоставленного объема улучшает производительность и увеличивает емкость для размещения большего количества узлов.  
  
 Если `gcTrimCommitOnLowMemory` параметр включен, сборщик мусора оценивает загрузку системной памяти и переходит в режим обрезки когда нагрузка достигает 90%. Это обеспечивает режим обрезки, пока загрузка не опустится ниже 85%.  
  
 Если позволяют условия, сборщик мусора может решить, что `gcTrimCommitOnLowMemory` параметр будет справки текущего приложения и не смогут его пропустить.  
  
## <a name="example"></a>Пример  
 В следующем фрагменте XML показано, как включить `gcTrimCommitOnLowMemory` параметр. Многоточие указывает на другие параметры, которые будут находиться в `runtime` узла.  
  
```xml  
<?xml version="1.0" encoding="UTF-8"?>  
<configuration>  
    <runtime>  
    . . .  
    <gcTrimCommitOnLowMemory enabled="true"/>  
    </runtime>  
    . . .  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 [Сборка мусора](../../../docs/standard/garbage-collection/index.md)
