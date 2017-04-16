---
title: "Уменьшение. Макет WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
caps.latest.revision: 3
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 3
---
# Уменьшение. Макет WPF
Макет элементов управления WPF может немного измениться.  
  
## Последствия  
 В результате этого изменения:  
  
-   ширина или высота элементов может увеличиться или уменьшиться максимум на один пиксель;  
  
-   расположение объекта может измениться максимум на один пиксель;  
  
-   выровненные по центру элементы могут сместиться по вертикали или горизонтали максимум на один пиксель.  
  
 По умолчанию новый макет включен только для приложений, предназначенных для .NET Framework 4.6.  
  
## Уменьшение  
 Поскольку это изменение, как правило, приводит к устранению обрезки правых или нижних элементов управления WPF при высоком разрешении, для приложений, предназначенных для более ранних версий .NET Framework, но выполняющихся в .NET Framework 4.6, можно выбрать это новое поведение, добавив следующую строку в раздел `<runtime>` файла app.config.  
  
```  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 Для приложений, предназначенных для .NET Framework 4.6, для которых требуется задать отрисовку элементов управления WPF с помощью прежнего алгоритма макета, можно добавить следующую строку в раздел `<runtime>` файла app.config.  
  
```  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## См. также  
 [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)