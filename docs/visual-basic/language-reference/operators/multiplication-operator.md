---
title: "Оператор * (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.*"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "* - оператор [Visual Basic]"
  - "арифметические операторы, умножение"
  - "математические операторы"
  - "оператор умножения, синтаксис"
  - "операторы [Visual Basic], умножение"
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Оператор * (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Выполняет умножение двух чисел.  
  
## Синтаксис  
  
```  
  
number1 * number2  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`number1`|Обязательный.  Произвольное числовое выражение.|  
|`number2`|Обязательный.  Произвольное числовое выражение.|  
  
## Результат  
 В результате получается произведение `number1` и `number2`.  
  
## Поддерживаемые типы  
 Все числовые типы, в том числе беззнаковые, с плавающей запятой и `Decimal`.  
  
## Заметки  
 Тип данных результата зависит от типов операндов.  В следующей таблице показано, как определяется тип данных результата.  
  
|||  
|-|-|  
|Типы данных операндов|Тип данных результата|  
|Оба выражения являются целыми \([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)\)|Тип данных результата является числовым типом, соответствующим типам данных `number1` и `number2`.  См. таблицы "Целочисленные арифметические операции" в разделе [Типы данных результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Оба выражения имеют тип [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`|  
|Оба выражения имеют [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`|  
|Одно выражение имеет тип данных с плавающей запятой \(`Single` или [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)\), но не оба `Single` \(следует отметить, что `Decimal` не является типом данных с плавающей запятой\)|`Double`|  
  
 Если выражение имеет значение [Nothing](../../../visual-basic/language-reference/nothing.md), оно интерпретируется как ноль.  
  
## Перегрузка  
 Оператор `*` может быть *перегружен*. Это означает, что класс или структура может переопределить его поведение, если операнд имеет тип соответствующего класса или структуры.  Если в коде используется этот оператор для такого класса или структуры, убедитесь, что его переопределенное поведение вам понятно.  Дополнительные сведения см. в разделе [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Пример  
 В данном примере оператор `*` используется для перемножения двух чисел.  Результатом является произведение двух операндов.  
  
 [!code-vb[VbVbalrOperators#4](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/multiplication-operator_1.vb)]  
  
## См. также  
 [Оператор \*\=](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)   
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)