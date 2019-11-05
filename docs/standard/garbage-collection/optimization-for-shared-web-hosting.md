---
title: Оптимизация совместного размещения веб-сайтов
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- garbage collection, Web hosting
- garbage collection, optimizing
- garbage collection, shared Web hosting
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
ms.openlocfilehash: 07a100e2cd6aaff2b54b99144c9d762c8979fb47
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140267"
---
# <a name="optimization-for-shared-web-hosting"></a>Оптимизация совместного размещения веб-сайтов
Если вы являетесь администратором сервера, на котором совместно размещены несколько небольших веб-сайтов, производительность и емкость такого сайта можно увеличить, добавив следующий параметр `gcTrimCommitOnLowMemory` в узел `runtime` файла Aspnet.config, расположенного в каталоге .NET.  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
> Этот параметр рекомендуется применять только в сценариях совместного размещения веб-сайтов.  
  
 Так как сборщик мусора сохраняет память для будущих распределений, он может выделять для них больше памяти, чем строго необходимо. Вы можете уменьшить этот объем, чтобы снизить нагрузку на системную память. Уменьшение выделяемого объема повышает производительность и емкость, позволяя разместить большее количество узлов.  
  
 Если включен параметр `gcTrimCommitOnLowMemory`, сборщик мусора оценивает загрузку системной памяти и переходит в режим обрезки, если нагрузка достигает 90 %. Режим обрезки сохраняется, пока загрузка не опустится ниже 85 %.  
  
 В некоторых условиях сборщик мусора полагает, что параметр `gcTrimCommitOnLowMemory` не может помочь работающему приложению, и тогда игнорирует его.  
  
## <a name="example"></a>Пример  
 В следующем фрагменте XML показано, как включить параметр `gcTrimCommitOnLowMemory`. Многоточие обозначает все другие параметры, которые находятся в узле `runtime`.  
  
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

- [Сборка мусора](../../../docs/standard/garbage-collection/index.md)
