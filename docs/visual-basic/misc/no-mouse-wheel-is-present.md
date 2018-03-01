---
title: "Не обнаружено колесо мыши"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrMouse_NoWheelIsPresent
ms.assetid: e924ffba-4af1-4247-9a6f-d19a03738f62
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7caf2e24bcbd86ad2b6175d593bd218a9bb4689d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="no-mouse-wheel-is-present"></a>Не обнаружено колесо мыши
Было вызвано свойство `My.Computer.Mouse.WheelScrollLines` , но у мыши отсутствует колесо прокрутки.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Проверьте свойство `My.Computer.Mouse.WheelExists` , чтобы увидеть, имеется ли колесо прокрутки мыши, перед вызовом свойства `My.Computer.Mouse.WheelScrollLines` .  
  
     - или -  
  
-   Установите на компьютере мышь с колесом прокрутки.  
  
## <a name="see-also"></a>См. также  
 [My.Computer.Mouse.WheelScrollLines](xref:Microsoft.VisualBasic.Devices.Mouse.WheelScrollLines)  
 [My.Computer.Mouse.WheelExists](xref:Microsoft.VisualBasic.Devices.Mouse.WheelExists)  
 [Исключения и обработка ошибок в Visual Basic](http://msdn.microsoft.com/library/3e351e73-cf23-40ab-8b60-05794160529e)
