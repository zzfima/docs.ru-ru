---
title: "Оператор ^= (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.^="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "^= - оператор [Visual Basic]"
  - "операторы назначения, составное"
  - "составные операторы присваивания"
  - "операторы [Visual Basic], составное присвоение"
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Оператор ^= (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Возводит значение переменной или свойства в степень, равную выражению, и присваивает результат переменной или свойству.  
  
## Синтаксис  
  
```  
  
variableorproperty ^= expression  
```  
  
## Части  
 `variableorproperty`  
 Обязательный.  Любая числовая переменная или свойство.  
  
 `expression`  
 Обязательный.  Произвольное числовое выражение.  
  
## Заметки  
 Элемент с левой стороны оператора `^=` может быть простой скалярной переменной, свойством или элементом массива.  Переменная или свойство не могут быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Оператор `^=` сначала вызывает значения переменной или свойства \(в левой части оператора в степень\) справа от значения выражения \(оператор\).  Оператор затем присвоить результат этой операции обратно в переменную или свойству.  
  
 Visual Basic всегда выполняет возведение в степень в [Тип данных Double](../../../visual-basic/language-reference/data-types/double-data-type.md).  Операнды любого другого типа преобразуются в `Double`. Результатом является всегда `Double`.  
  
 Значение `expression` может быть дробным, отрицательным или сразу обоими.  
  
## Перегрузка  
 Оператор [Оператор ^](../../../visual-basic/language-reference/operators/exponentiation-operator.md) может быть *перегружен*; это означает, что класс или структура может переопределить его действие, если операнд имеет тип класса или структуры.  Перегрузка оператора `^` влияет на тип выполнения оператора `^=`.  Если в коде используется оператор `^=` для класса или структуры, перегружающей `^`, убедитесь, что его переопределенное выполнение вам понятно.  Дополнительные сведения см. в разделе [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Пример  
 В следующем примере оператор `^=` используется для возведения переменной типа `Integer` в степень, равную второй переменной, и для присвоения значения первой переменной.  
  
 [!code-vb[VbVbalrOperators#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-assignment-operator_1.vb)]  
  
## См. также  
 [Оператор ^](../../../visual-basic/language-reference/operators/exponentiation-operator.md)   
 [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)