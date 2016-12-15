---
title: "Оператор *= (Visual Basic) | Microsoft Docs"
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
  - "vb.*="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "*= - оператор [Visual Basic]"
  - "операторы назначения, составное"
  - "составные операторы присваивания"
  - "*= - оператор"
  - "операторы [Visual Basic], составное присвоение"
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор *= (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Умножает значение переменной или свойства на значение выражения и присваивает результат переменной или свойству.  
  
## Синтаксис  
  
```  
  
variableorproperty *= expression  
```  
  
## Части  
 `variableorproperty`  
 Обязательный.  Любая числовая переменная или свойство.  
  
 `expression`  
 Обязательный.  Произвольное числовое выражение.  
  
## Заметки  
 Элемент с левой стороны оператора `*=` может быть простой скалярной переменной, свойством или элементом массива.  Переменная или свойство не могут быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Оператор `*=` сначала умножает значение выражения \(справа от оператора\) значение переменной или свойства \(в левой части оператора\).  Оператор затем присвоить результат этой операции в переменной или свойству.  
  
## Перегрузка  
 [Оператор \*](../../../visual-basic/language-reference/operators/multiplication-operator.md) может быть *перегружен*. Это означает, что класс или структура может переопределить его действие, если операнд имеет такой же тип класса или структуры.  Перегрузка оператора `*` влияет на поведение оператора `*=`.  Если в коде используется оператор `*=` для класса или структуры, перегружающей `*`, убедитесь, что его переопределенное выполнение понятно.  Дополнительные сведения см. в разделе [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Пример  
 В следующем примере оператор `*=` используется для умножения значения одной переменной типа `Integer` на значение другой переменной и присваивания результата первой переменной.  
  
 [!code-vb[VbVbalrOperators#5](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/multiplication-assignment-operator_1.vb)]  
  
## См. также  
 [Оператор \*](../../../visual-basic/language-reference/operators/multiplication-operator.md)   
 [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)