---
title: "ParamArray (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ParamArray"
  - "ParamArray"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ParamArray - ключевое слово"
  - "ParamArray - ключевое слово, синтаксис"
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# ParamArray (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает, что параметр процедуры принимает дополнительный массив элементов заданного типа.  `ParamArray` может использоваться только в последнем параметре списка параметров.  
  
## Заметки  
 С помощью `ParamArray` в процедуру можно передать произвольное число аргументов.  Параметр `ParamArray` всегда объявляется с помощью [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).  
  
 Можно указать один или несколько аргументов параметра `ParamArray`, передав массив из соответствующего типа данных, список с разделенными запятыми значениями или не передав ничего.  Подробные сведения см. в разделе "Вызов ParamArray" в [Массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
> [!IMPORTANT]
>  При работе с неограниченно большим массивом есть риск переполнения некоторой внутренней емкости приложения.  Если массив параметров принимается из вызываемого кода, следует проверить его длину и предпринять соответствующие действия в случае, если она слишком велика для приложения.  
  
 Модификатор `ParamArray` можно использовать в следующих контекстах:  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## См. также  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)   
 [Массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)