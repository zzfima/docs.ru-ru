---
title: Устранение рисков. Макет WPF
ms.date: 03/30/2017
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a9bc9e14621b22cad6491f6f5132ef302e7ef06
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="mitigation-wpf-layout"></a>Устранение рисков. Макет WPF
Макет элементов управления WPF может немного изменяться.  
  
## <a name="impact"></a>Последствия  
 В результате этого изменения:  
  
-   ширина или высота элементов может увеличиться или уменьшиться максимум на один пиксель;  
  
-   расположение объекта может измениться максимум на один пиксель;  
  
-   выровненные по центру элементы могут сместиться по вертикали или горизонтали максимум на один пиксель.  
  
 По умолчанию новый макет включен только для приложений, предназначенных для .NET Framework 4.6.  
  
## <a name="mitigation"></a>Устранение рисков  
 Поскольку это изменение, как правило, приводит к устранению обрезки правых или нижних элементов управления WPF при высоком разрешении, для приложений, предназначенных для более ранних версий .NET Framework, но выполняющихся в .NET Framework 4.6, можно выбрать это новое поведение, добавив следующую строку в раздел `<runtime>` файла app.config.  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 Для приложений, предназначенных для .NET Framework 4.6, для которых требуется задать отрисовку элементов управления WPF с помощью прежнего алгоритма макета, можно добавить следующую строку в раздел `<runtime>` файла app.config.  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a>См. также  
 [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
