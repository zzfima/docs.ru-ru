---
title: "Оператор \= | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "\="
  - "vb.\="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "\= - оператор [Visual Basic]"
  - "операторы назначения, составное"
  - "составные операторы присваивания"
  - "\= - оператор [Visual Basic]"
  - "операторы [Visual Basic], составное присвоение"
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Оператор \=
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Делит значение переменной или свойства на значение выражения и присваивает целочисленный результат переменной или свойству.  
  
## Синтаксис  
  
```  
  
variableorproperty \= expression  
```  
  
## Части  
 `variableorproperty`  
 Обязательный.  Любая числовая переменная или свойство.  
  
 `expression`  
 Обязательный.  Произвольное числовое выражение.  
  
## Заметки  
 Элемент с левой стороны оператора `\=` может быть простой скалярной переменной, свойством или элементом массива.  Переменная или свойство не могут быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Оператор `\=` делит значения переменной или свойство в своем остается значением для права и присвоить его результат переменной или свойства целого числа в его влево  
  
 Дополнительные сведения о целочисленном делении см. в разделе [Оператор \\](../Topic/-%20Operator%20\(Visual%20Basic\)2.md).  
  
## Перегрузка  
 Оператор `\` может быть *перегружен*; это означает, что класс или структура может переопределить его поведение, если операнд имеет тип соответствующего класса или структуры.  Перегрузка оператора `\` влияет на тип выполнения оператора `\=`.  Если в коде используется оператор `\=` для класса или структуры, перегружающей `\`, убедитесь, что его переопределенное выполнение понятно.  Дополнительные сведения см. в разделе [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Пример  
 В следующем примере оператор `\=` используется для деления значения одной переменной типа `Integer` на значение другой переменной и присваивания целочисленного результата первой переменной.  
  
 [!code-vb[VbVbalrOperators#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-assignment-operator_1.vb)]  
  
## См. также  
 [Оператор \\](../Topic/-%20Operator%20\(Visual%20Basic\)2.md)   
 [Оператор \/\=](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)   
 [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)