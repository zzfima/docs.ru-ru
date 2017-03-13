---
title: "Оператор += (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.+="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "+= - оператор [Visual Basic]"
  - "+= - оператор [Visual Basic], дополнение строк"
  - "операторы назначения, составное"
  - "составные операторы присваивания"
  - "операторы [Visual Basic], составное присвоение"
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Оператор += (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Добавляет значение числового выражения к значению числовой переменной или свойства и присваивает результат переменной или свойству.  Может также использоваться для объединения `String` выражения с `String` переменной или свойством и присваивает результат переменной или свойству.  
  
## Синтаксис  
  
```  
  
variableorproperty += expression  
```  
  
## Части  
 `variableorproperty`  
 Обязательный.  Любая численная или `String` переменная или свойство.  
  
 `expression`  
 Обязательный.  Любое выражение типа `String` или числовое выражение.  
  
## Заметки  
 Элемент с левой стороны оператора `+=` может быть простой скалярной переменной, свойством или элементом массива.  Переменная или свойство не могут быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 `+=` оператор добавляет значение в своем правой части к переменной или свойство в его влево и присвоить его результат переменной или свойство в своем слева.  `+=` оператор может также использоваться для сцепления  `String` выражение на его правой части к  `String` переменная или свойство в своем слева и присвоить его результат переменной или свойство в своем слева.  
  
> [!NOTE]
>  При использовании оператора `+=` не всегда удается определить, произойдет объединение строк или операция сложения.  Чтобы избежать неоднозначности и получить самодокументирующий код, используйте для объединения оператор `&=`.  
  
 Данный оператор присваивания производит неявное преобразование типов в сторону расширения типа данных, если среда требует строгой семантики.  Дополнительные сведения о этих преобразованиях содержатся в разделе [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  Дополнительные сведения о строгой и разрешающей семантике содержатся в разделе [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
 Если используется разрешающая семантика, то оператор `+=` неявно выполняет различные строковые и числовые преобразования, которые идентичны выполняемым оператором `+`.  Сведения об этих преобразованиях содержатся в разделе [Оператор \+](../../../visual-basic/language-reference/operators/addition-operator.md).  
  
## Перегрузка  
 Оператор `+` может быть *перегружен*; это означает, что класс или структура может переопределить его поведение, если операнд имеет тип соответствующего класса или структуры.  Перегрузка оператора `+` влияет на поведение оператора `+=`.  Если в коде используется оператор `+=` для класса или структуры, перегружающей `+`, убедитесь, что его переопределенное выполнение понятно.  Дополнительные сведения см. в разделе [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Пример  
 В следующем примере оператор `+=` используется для объединения значения одной переменной с другой.  Первая часть использует `+=` с числовыми переменными для добавления одного значения к другому.  Вторая часть использует `+=` с `String` переменными для добавления одной строки к другой.  В обоих случаях результат присваивается первой переменной.  
  
 [!code-vb[VbVbalrOperators#7](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_1.vb)]  
  
 [!code-vb[VbVbalrOperators#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_2.vb)]  
  
 Значение `num1` становится 13, а значение `str1` становится "103".  
  
## См. также  
 [Оператор \+](../../../visual-basic/language-reference/operators/addition-operator.md)   
 [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Операторы объединения](../../../visual-basic/language-reference/operators/concatenation-operators.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)