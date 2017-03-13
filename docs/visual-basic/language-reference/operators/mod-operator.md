---
title: "Оператор Mod (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Mod"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "остаток (оператор Mod)"
  - "оператор деления, оператор Mod"
  - "оператор модуля, Visual Basic"
  - "Mod - оператор [Visual Basic]"
  - "операторы [Visual Basic], деление"
  - "арифметические операторы, Mod"
  - "математические операторы"
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Оператор Mod (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Делит два числа и возвращает только остаток.  
  
## Синтаксис  
  
```  
  
number1 Mod number2  
```  
  
## Части  
 `number1`  
 Обязательное.  Произвольное числовое выражение.  
  
 `number2`  
 Обязательное.  Произвольное числовое выражение.  
  
## Поддерживаемые типы  
 Все числовые типы.  К ним относятся типы чисел с плавающей запятой и без знака и тип `Decimal`.  
  
## Результат  
 В результате получается остаток после деления `number1` на `number2`.  Например выражение `14 Mod 4` равно 2.  
  
## Заметки  
 Если `number1` или `number2` является значением с плавающей запятой, то возвращается остаток от деления с плавающей запятой.  Тип данных результата является наименьшим типом данных, который может содержать все возможные значения результатов деления с участием типов данных `number1` и `number2`.  
  
 Если `number1` или `number2` равны [Nothing](../../../visual-basic/language-reference/nothing.md), оно интерпретируется как ноль.  
  
 Связанные операторы включают:  
  
-   [Оператор \\](../Topic/-%20Operator%20\(Visual%20Basic\)2.md) возвращает целочисленное частное от деления.  Например выражение `14 \ 4` равно 3.  
  
-   [Оператор \/](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) возвращает полное частное, включая остаток, как число с плавающей запятой.  Например выражение `14 / 4` равно 3,5.  
  
## Попытка деления на ноль  
 Если значением `number2` является ноль, поведение оператора `Mod` зависит от типа данных операндов.  Целочисленное деление вызывает <xref:System.DivideByZeroException> исключение.  Деление с плавающей запятой возвращает <xref:System.Double.NaN>.  
  
## Эквивалентная формула  
 Выражение `a Mod b` является эквивалентом для любой из следующих формул:  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## Погрешность чисел с плавающей запятой  
 Используя числа с плавающей запятой, следует учитывать, что они не всегда имеют точное представление в памяти.  Это может привести к непредвиденным результатам для определенных операций, таких как сравнение значений и `Mod`.  Для получения дополнительной информации см. [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## Перегрузка  
 Оператор `Mod` может быть *overloaded*. Это означает, что класс или структура может переопределить его поведение.  Если код применяет `Mod` к экземпляру класса или структуры, включающей такие перегрузки, обязательно убедитесь в том, что их переопределенное поведение понятно.  Для получения дополнительной информации см. [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Пример  
 В следующем примере оператор `Mod` используется для деление одного числа на другое и возврата только остатка.  Если оба числа являются числами с плавающей запятой, результат является числом с плавающей запятой, представляющим остаток.  
  
 [!code-vb[VbVbalrOperators#31](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_1.vb)]  
  
## Пример  
 В следующем примере показана возможная неточность операндов с плавающей запятой.  В первом операторе операнды относятся к типу `Double`, и 0,2 является периодической бесконечной двоичной дробью, которая хранится в виде значения 0,20000000000000001.  Во втором операторе символ типа литерала `D` указывает, что оба операнда относятся к типу `Decimal`, и 0,2 имеет точное представление.  
  
 [!code-vb[VbVbalrOperators#32](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_2.vb)]  
  
## См. также  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>   
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>   
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Оператор \\](../Topic/-%20Operator%20\(Visual%20Basic\)2.md)