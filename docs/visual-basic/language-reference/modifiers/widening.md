---
title: "Widening (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.widening"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "преобразования, тип данных"
  - "преобразования, тип"
  - "преобразование типов данных"
  - "преобразование типов"
  - "Widening - ключевое слово"
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Widening (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает, что оператор преобразования \(`CType`\) преобразует класс или структуру к типу, который может содержать все возможные значения исходного класса или структуры.  
  
## Преобразование с использованием ключевого слова Widening  
 Процедура преобразования должна указать `Public Shared` в дополнение к `Widening`.  
  
 Расширяющие преобразования всегда успешны во время выполнения и никогда не приводят к потере данных.  Примерами являются преобразования `Single` в `Double`, `Char` в `String` и производного типа в базовой тип.  Последнее преобразование является расширяющим, так как производный тип содержит все элементы базового типа и поэтому является экземпляром базового типа.  
  
 Рассматриваемый код не может использовать `CType` для расширяющих преобразований, даже если `Option Strict` имеет значение `On`.  
  
 Ключевое слово `Widening` можно использовать в следующем контексте:  
  
 [Оператор Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 Примеры определений расширения и сужения операторов преобразования см. в разделе [Практическое руководство. Определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## См. также  
 [Оператор Operator](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md)   
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Практическое руководство. Определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)