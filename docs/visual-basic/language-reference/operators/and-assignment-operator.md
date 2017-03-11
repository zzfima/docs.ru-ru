---
title: "Оператор &amp;= (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.&="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "&= - оператор [Visual Basic]"
  - "операторы назначения, составное"
  - "составные операторы присваивания"
  - "&= - оператор"
  - "операторы [Visual Basic], составное присвоение"
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Оператор &amp;= (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Сцепляет выражения типа `String` с переменной или свойством `String` и присваивает результат переменной или свойству.  
  
## Синтаксис  
  
```  
  
variableorproperty &= expression  
```  
  
## Части  
 `variableorproperty`  
 Обязательный.  Какая\-либо переменная или свойство типа `String`.  
  
 `expression`  
 Обязательный.  Произвольное выражение типа `String`.  
  
## Заметки  
 Элемент с левой стороны оператора `&=` может быть простой скалярной переменной, свойством или элементом массива.  Переменная или свойство не могут быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  `&=` оператор сцепляет  `String` выражение на его правой части к  `String` переменная или свойство в своем слева и присвоить его результат переменной или свойство в своем слева.  
  
## Перегрузка  
 Оператор [Оператор &](../../../visual-basic/language-reference/operators/concatenation-operator.md) может быть *перегружен*; это означает, что класс или структура может переопределить его тип, когда операнд имеет тип класса или структуры.  Перегрузка оператора `&` влияет на тип выполнения оператора `&=`.  Если в коде используется оператор `&=` для класса или структуры, перегружающей `&`, убедитесь, что его переопределенное выполнение вам понятно.  Дополнительные сведения см. в разделе [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Пример  
 В приведенном ниже примере оператор `&=` выполняет сцепление двух переменных типа `String` и присваивает результат первой переменной.  
  
 [!code-vb[VbVbalrOperators#3](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/and-assignment-operator_1.vb)]  
  
## См. также  
 [Оператор &](../../../visual-basic/language-reference/operators/concatenation-operator.md)   
 [Оператор \+\=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)   
 [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Операторы объединения](../../../visual-basic/language-reference/operators/concatenation-operators.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)