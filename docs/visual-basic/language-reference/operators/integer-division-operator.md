---
title: "Оператор \ (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.\"
  - "\"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "\ - оператор [Visual Basic]"
  - "арифметические операторы, деление"
  - "обратная косая черта (\) [Visual Basic]"
  - "оператор деления, целочисленный"
  - "деление, на ноль"
  - "оператор целочисленного деления"
  - "частное целого числа"
  - "математические операторы"
  - "частные, целочисленный"
  - "усечение, целочисленное деление"
  - "ноль, деление на ноль"
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Оператор \ (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Делит одно число на другое и возвращает целочисленный результат.  
  
## Синтаксис  
  
```  
  
expression1 \ expression2  
```  
  
## Части  
 `expression1`  
 Обязательный.  Произвольное числовое выражение.  
  
 `expression2`  
 Обязательный.  Произвольное числовое выражение.  
  
## Поддерживаемые типы  
 Все числовые типы, в том числе беззнаковые, с плавающей запятой и `Decimal`.  
  
## Результат  
 Результатом является целочисленное частное от деления `expression1` на `expression2`, в котором отбрасывается остаток и остается только целая часть числа.  Это называется *усечением*.  
  
 Тип данных результата является числовым типом, соответствующим типам данных выражений `expression1` и `expression2`.  См. таблицы "Целочисленные арифметические операции" в разделе [Типы данных результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
 [Оператор \/](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) возвращает полное частное, в котором сохраняется остаток в виде дробной части.  
  
## Заметки  
 Перед выполнением деления, Visual Basic пытается преобразовать любое числовое выражение с плавающей запятой в тип `Long`.  Если `Option Strict` установлен в `On`, то возникает ошибка компилятора.  Если `Option Strict` установлен в `Off`, то возможно возникновение исключения <xref:System.OverflowException>, если значение находится вне диапазона [Тип данных Long](../../../visual-basic/language-reference/data-types/long-data-type.md).  В преобразовании в тип `Long` также используется *банковское округление*.  Дополнительные сведения см. в теме "Дробные части" раздела [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Если `expression1` или `expression2` равны [Nothing](../../../visual-basic/language-reference/nothing.md), оно интерпретируется как ноль.  
  
## Попытка деления на ноль  
 Если `expression2` равно нулю, то оператор `\` вызывает исключение <xref:System.DivideByZeroException>.  Это справедливо для всех операндов числового типа.  
  
> [!NOTE]
>  Оператор `\` может быть *перегружен*; это означает, что класс или структура может переопределить его поведение, если операнд имеет тип соответствующего класса или структуры.  Если в коде используется этот оператор для такого класса или структуры, убедитесь, что его переопределенное поведение вам понятно.  Дополнительные сведения см. в разделе [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Пример  
 В следующем примере оператор `\` используется для выполнения целочисленного деления.  Результатом является целое число, представляющее целочисленное частное двух операндов, с отброшенным остатком.  
  
 [!code-vb[VbVbalrOperators#18](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/integer-division-operator_1.vb)]  
  
 Выражения в предыдущем примере возвращают значения 2, 3, 33 и \-22 соответственно.  
  
## См. также  
 [Оператор \\\=](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)   
 [Оператор \/](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)   
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)