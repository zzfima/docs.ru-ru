---
title: "Оператор /= (Visual Basic) | Microsoft Docs"
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
  - "vb./="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/= - оператор [Visual Basic]"
  - "операторы назначения, составное"
  - "составные операторы присваивания"
  - "/= - оператор"
  - "операторы [Visual Basic], составное присвоение"
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
caps.latest.revision: 23
caps.handback.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор /= (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Делит значение переменной или свойства на значение выражения и присваивает результат с плавающей точкой переменной или свойству.  
  
## Синтаксис  
  
```  
  
variableorproperty /= expression  
```  
  
## Части  
 `variableorproperty`  
 Обязательный.  Любая числовая переменная или свойство.  
  
 `expression`  
 Обязательный.  Произвольное числовое выражение.  
  
## Заметки  
 Элемент с левой стороны оператора `/=` может быть простой скалярной переменной, свойством или элементом массива.  Переменная или свойство не могут быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Оператор `/=` сначала делит значения переменной или свойства \(в левой части оператора \(\) значение выражения в правой части оператора\).  Оператор затем присвоить результат этой операции с плавающей запятой в переменную или свойству.  
  
 Этот оператор будет присвоено значение `Double` переменной или свойство слева.  Если `Option Strict` принимает значение `On`, то `variableorproperty` должен быть `Double`.  Если `Option Strict` установлен в `Off`, Visual Basic произведет неявное преобразование и присвоит результирующее значение `variableorproperty`, с возможной ошибкой во время выполнения.  Дополнительные сведения см. в разделах [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## Перегрузка  
 [Оператор \/](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) может быть *перегружен*; это означает, что класс или структура может переопределить его действие, если операнд имеет определенный тип класса или структуры.  Перегрузка оператора `/` влияет на тип выполнения оператора `/=`.  Если в коде используется оператор `/=` для класса или структуры, перегружающей `/`, убедитесь, что его переопределенное выполнение вам понятно.  Дополнительные сведения см. в разделе [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Пример  
 В следующем примере оператор `/=` используется для деления значения одной переменной типа `Integer` на значение другой переменной и присваивания результата первой переменной.  
  
 [!code-vb[VbVbalrOperators#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-assignment-operator_1.vb)]  
  
## См. также  
 [Оператор \/](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)   
 [Оператор \\\=](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)   
 [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)