---
title: "Оператор / (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb./"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/ - оператор [Visual Basic]"
  - "арифметические операторы, деление"
  - "оператор деления, с плавающей запятой"
  - "оператор деления, синтаксис"
  - "деление, на ноль"
  - "числа с плавающей запятой, оператор деления"
  - "математические операторы"
  - "операторы [Visual Basic], арифметические"
  - "операторы [Visual Basic], деление"
  - "косая черта (/) - оператор"
  - "ноль, деление на ноль"
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор / (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Делит одно число на другое и возвращает результат с плавающей запятой.  
  
## Синтаксис  
  
```  
  
expression1 / expression2  
```  
  
## Части  
 `expression1`  
 Обязательный.  Произвольное числовое выражение.  
  
 `expression2`  
 Обязательный.  Произвольное числовое выражение.  
  
## Поддерживаемые типы  
 Все числовые типы, в том числе беззнаковые, с плавающей запятой и `Decimal`.  
  
## Результат  
 Результатом является полное частное от деления `expression1` на `expression2`, включая любой остаток.  
  
 [Оператор \\](../../../visual-basic/language-reference/operators/integer-division-operator.md) возвращает целочисленное частное, без остатка.  
  
## Заметки  
 Тип данных результата зависит от типов операндов.  В следующей таблице показано, как определяется тип данных результата.  
  
|Типы данных операндов|Тип данных результата|  
|---------------------------|---------------------------|  
|Оба выражения являются целыми \([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)\)|`Double`|  
|Одно выражение является типом данных [Single](../../../visual-basic/language-reference/data-types/single-data-type.md), а второе не является типом [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Single`|  
|Одно выражение является типом данных [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), а второе не является типом [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) или [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Decimal`|  
|Какое\-либо из выражений имеет тип данных [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
  
 Перед выполнением деления все целочисленные числовые выражения преобразуются в тип данных `Double`.  Если присвоить результат переменной целочисленного типа данных, Visual Basic попытается преобразовать результат из `Double` в этот тип.  Это может вызвать исключение, если результат не умещается в этом типе.  В частности, см. "Попытка деления на 0" на этой странице справки.  
  
 Если `expression1` или `expression2` равны [Nothing](../../../visual-basic/language-reference/nothing.md), оно интерпретируется как ноль.  
  
## Попытка деления на ноль  
 Если значением `expression2` является ноль, оператор `/` работает по\-разному для разных типов данных операнда.  В следующей таблице показаны возможные результаты.  
  
|Типы данных операндов|Поведение в случае равенства нулю `expression2`|  
|---------------------------|-----------------------------------------------------|  
|С плавающей запятой \(`Single` или `Double`\)|Возвращает бесконечность \(<xref:System.Double.PositiveInfinity> или <xref:System.Double.NegativeInfinity>\) или <xref:System.Double.NaN> \(не число\), если `expression1` также является нулем|  
|`Decimal`|Вызывает <xref:System.DivideByZeroException>|  
|Целочисленное \(знаковое или беззнаковое\)|Попытка преобразования обратно в целочисленный тип вызывает <xref:System.OverflowException>, так как целые типы не принимают <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity> и <xref:System.Double.NaN>|  
  
> [!NOTE]
>  Оператор `/` может быть *перегружен*; это означает, что класс или структура может переопределить его поведение, если операнд имеет тип соответствующего класса или структуры.  Если в коде используется этот оператор для такого класса или структуры, убедитесь, что его переопределенное поведение вам понятно.  Дополнительные сведения см. в разделе [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Пример  
 В данном примере оператор `/` используется для выполнения операции деления с плавающей запятой.  Результатом является частное двух операндов.  
  
 [!code-vb[VbVbalrOperators#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-operator_1.vb)]  
  
 Выражения в предыдущем примере возвращают значения 2,5 и 3,333333.  Следует отметить, что результат всегда имеет тип числа с плавающей запятой \(`Double`\), даже если оба операнда являются целочисленными константами.  
  
## См. также  
 [Оператор \/\=](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)   
 [Оператор \\](../../../visual-basic/language-reference/operators/integer-division-operator.md)   
 [Типы данных результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)   
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)