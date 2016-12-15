---
title: "Возвращаемые значения функции CStr (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "CStr - функция"
  - "Date - тип данных, преобразование"
  - "даты [Visual Basic]"
  - "даты [Visual Basic], возвращаемые значения функции CStr"
  - "String - тип данных, преобразование"
  - "строки [Visual Basic], возвращаемое значение"
  - "значения времени, возвращаемые значения функции CStr"
  - "преобразование типов"
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Возвращаемые значения функции CStr (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В следующей таблице описаны возвращаемые значения `CStr` для различных типов данных параметра `expression`.  
  
|Если тип `expression`,|возвращается `CStr`:|  
|----------------------------|--------------------------|  
|[Тип данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Строка, содержащая "True" или "False".|  
|[Тип данных Date](../../../visual-basic/language-reference/data-types/date-data-type.md)|Строка, содержащая значение типа `Date` \(дата и время\) в кратком формате даты для данной системы.|  
|[Числовые типы данных](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|Строка, представляющая число.|  
  
## CStr и Date  
 Тип данных `Date` всегда включает сведения о дате и времени.  При преобразовании типов в Visual Basic *нейтральным значением* даты считается 1\/1\/1 \(1 января 1 года\), а нейтральным значением времени — 00:00:00 \(полночь\).  `CStr` не включает нейтральные значения в результирующую строку.  Например, при преобразовании значения `#January 1, 0001 9:30:00#` в строку, будет возвращен результат "9:30:00"; дата отбрасывается.  При этом сведения о дате останутся в исходном значении `Date` и могут быть извлечены с помощью таких функций, как <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.  
  
> [!NOTE]
>  Функция `CStr` выполняет преобразование на основе настроек текущей языковой среды для приложения.  Чтобы получить строковое представление числа для определенного языка, используйте метод `ToString(IFormatProvider)` этого числа.  Например, используйте <xref:System.Double.ToString%2A?displayProperty=fullName> при преобразовании значения типа `Double` к `String`.  
  
## См. также  
 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Тип данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)   
 [Тип данных Date](../../../visual-basic/language-reference/data-types/date-data-type.md)