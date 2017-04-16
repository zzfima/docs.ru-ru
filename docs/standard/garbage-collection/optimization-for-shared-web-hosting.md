---
title: "Optimization for Shared Web Hosting | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "garbage collection, Web hosting"
  - "garbage collection, optimizing"
  - "garbage collection, shared Web hosting"
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Optimization for Shared Web Hosting
Администратор сервера, на котором совместно размещены несколько небольших веб\-узлов, может оптимизировать производительность и увеличить емкость узла посредством добавления параметра `gcTrimCommitOnLowMemory` в узел `runtime` файла Aspnet.config в каталоге .NET Framework:  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
>  Этот параметр рекомендуется использовать только в сценариях с совместным размещением веб\-узлов.  
  
 Так как сборщик мусора оставляет память для выделения в будущем, задействованная им память может превышать минимально необходимые объемы.  Можно уменьшить этот объем, чтобы облегчить работу системы при высоких нагрузках на системную память.  Уменьшение этого предоставленного объема улучшает производительность и увеличивает емкость для размещения большего количества узлов.  
  
 Если включен параметр `gcTrimCommitOnLowMemory`, сборщик мусора оценивает загрузку системной памяти и переходит в режим обрезки, если загрузка достигла 90%.  Сборщик мусора пребывает в режиме обрезки до тех пор, пока загрузка не опустится ниже 85%.  
  
 Если позволяют условия, сборщик мусора может решить, что параметр `gcTrimCommitOnLowMemory` не будет оказывать помощь текущему приложению, и начнет его игнорировать.  
  
## Пример  
 В следующем фрагменте XML показано, как включить параметр `gcTrimCommitOnLowMemory`.  Многоточие указывает на другие параметры, которые могут содержаться в узле `runtime`.  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
<configuration>  
    <runtime>  
    . . .  
    <gcTrimCommitOnLowMemory enabled="true"/>  
    </runtime>  
    . . .  
</configuration>  
```  
  
## См. также  
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)