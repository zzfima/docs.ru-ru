---
title: "Оператор -= (Visual Basic) | Microsoft Docs"
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
  - "vb.-="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "-= - оператор [Visual Basic]"
  - "операторы назначения, составное"
  - "составные операторы присваивания"
  - "-= - оператор"
  - "операторы [Visual Basic], составное присвоение"
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор -= (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Вычитает значение выражения из значения переменной или свойства и присваивает результат переменной или свойству.  
  
## Синтаксис  
  
```  
  
variableorproperty -= expression  
```  
  
## Части  
 `variableorproperty`  
 Обязательный.  Любая числовая переменная или свойство.  
  
 `expression`  
 Обязательный.  Произвольное числовое выражение.  
  
## Заметки  
 Элемент с левой стороны оператора `-=` может быть простой скалярной переменной, свойством или элементом массива.  Переменная или свойство не могут быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Оператор `-=` вначале вычитается значение выражения в правой части оператора \(\) из значения переменной или свойства \(в левой части оператора\).  Оператор затем присвоить результат этой операции в переменной или свойству.  
  
## Перегрузка  
 Оператор [Оператор "\-"](../../../visual-basic/language-reference/operators/subtraction-operator.md) может быть *перегружен*; это означает, что класс или структура может переопределить его действие, когда операнд имеет тип класса или структуры.  Перегрузка оператора `-` влияет на тип выполнения оператора `-=`.  Если в коде используется оператор `-=` для класса или структуры, перегружающей `-`, убедитесь, что его переопределенное выполнение вам понятно.  Дополнительные сведения см. в разделе [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Пример  
 В следующем примере оператор `-=` используется для вычитания значения переменной типа `Integer` из значения другой переменной и присваивания результата первой переменной.  
  
 [!code-vb[VbVbalrOperators#11](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/integer-division-assignment-operator_1.vb)]  
  
## См. также  
 [Оператор "\-"](../../../visual-basic/language-reference/operators/subtraction-operator.md)   
 [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)