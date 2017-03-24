---
title: "Narrowing (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.narrowing"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "преобразования, тип данных"
  - "преобразования, тип"
  - "преобразование типов данных"
  - "Narrowing - ключевое слово"
  - "преобразование типов"
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Narrowing (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает, что оператор преобразования \(`CType`\) преобразует класс или структуру в тип, у которого может отсутствовать возможность хранения некоторых из возможных значений исходного класса или структуры.  
  
## Преобразование с ключевым словом "Narrowing"  
 Процедура преобразования должна указать `Public Shared` в дополнение к `Narrowing`.  
  
 Сужающие преобразования не всегда успешны во время выполнения и могут привести к ошибке или потере данных.  Примерами являются преобразования `Long` в `Integer`, `String` в `Date` и базового типа в производный тип.  Это последнее преобразование является сужающим, поскольку базовый тип может не содержать всех членов производного типа и таким образом не является экземпляром производного типа.  
  
 Если `Option Strict` установлен в значение `On`, потребляющий код должен использовать `CType` для всех сужающих преобразований.  
  
 Ключевое слово `Narrowing` можно использовать в следующем контексте:  
  
 [Оператор Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## См. также  
 [Оператор Operator](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)   
 [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md)   
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)