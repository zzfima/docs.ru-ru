---
title: "Оператор ^ (Visual Basic) | Microsoft Docs"
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
  - "vb.^"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "^ - оператор [Visual Basic]"
  - "^ - оператор [Visual Basic], возведение в степень"
  - "арифметические операторы, возведение в степень"
  - "показатель степени"
  - "оператор возведения в степень [Visual Basic]"
  - "числа, возведение"
  - "степень"
  - "возведение чисел в степень"
  - "оператор возведения в квадрат"
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор ^ (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Возводит число в степень, обозначенную другим числом.  
  
## Синтаксис  
  
```  
  
number ^ exponent  
```  
  
## Части  
 `number`  
 Обязательный.  Произвольное числовое выражение.  
  
 `exponent`  
 Обязательный.  Произвольное числовое выражение.  
  
## Результат  
 В результате получается значение `Double` равное значению `number`, возведенному в степень `exponent`.  
  
## Поддерживаемые типы  
 `Double`.  Операнды любого другого типа преобразуются в `Double`.  
  
## Заметки  
 Visual Basic всегда выполняет возведение в степень в [Тип данных Double](../../../visual-basic/language-reference/data-types/double-data-type.md).  
  
 Значение `exponent` может быть дробным, отрицательным или сразу обоими.  
  
 При выполнении нескольких возведений в степень в одном выражении оператор `^` вычисляется слева направо в том порядке, в котором он записан.  
  
> [!NOTE]
>  Оператор `^` может быть *перегружен*; это означает, что класс или структура может переопределить его поведение, если операнд имеет тип соответствующего класса или структуры.  Если в коде используется этот оператор для такого класса или структуры, убедитесь, что его переопределенное поведение вам понятно.  Дополнительные сведения см. в разделе [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Пример  
 В данном примере оператор `^` используется для возведения числа в степень экспоненты.  Результатом является первый операнд, возведенный в степень, обозначенную вторым.  
  
 [!code-vb[VbVbalrOperators#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-operator_1.vb)]  
  
 В итоге получены следующие результаты.  
  
 Значение `exp1` устанавливается в 4 \(2 в квадрате\) .  
  
 Значение `exp2` устанавливается в 19683 \(3 в кубе, а затем полученное значение в кубе\).  
  
 Значение `exp3` устанавливается в 125 \(5 в кубе\) .  
  
 Значение `exp4` устанавливается в 625 \(\-5 в четвертой степени\)  
  
 Значение `exp5` устанавливается в 2 \(кубический корень из 8\).  
  
 Значение `exp6` устанавливается в 0.5 \(1.0 делится на кубический корень из 8\).  
  
 Обратите внимание на важность круглых скобок в выражениях в предыдущем примере.  Из\-за *приоритетов операторов* Visual Basic обычно выполняет оператор `^` перед любыми другими, даже унарным оператором `–`.  Если бы `exp4` и `exp6` были рассчитаны без скобок, то они имели бы следующие результаты:  
  
 `exp4 = -5 ^ 4` было бы вычисляется как 5 до четвертой power \(–\), приведет к появлению \-625.  
  
 `exp6 = 8 ^ -1.0 / 3.0` будет рассчитываться как \(8 в степени \-1 или 0,125\) разделить на 3,0, что равно 0,041666666666666666666666666666667.  
  
## См. также  
 [Оператор ^\=](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)   
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)