---
title: "Оператор AndAlso (Visual Basic) | Microsoft Docs"
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
  - "vb.AndAlso"
  - "AndAlso"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "AndAlso - оператор"
  - "операторы [Visual Basic], конъюнкция"
  - "операторы [Visual Basic], сокращенные вычисления"
  - "сокращенные вычисления"
  - "сокращенные вычисления"
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор AndAlso (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Выполняет упрощенную операцию логического умножения над двумя выражениями.  
  
## Синтаксис  
  
```  
  
result = expression1 AndAlso expression2  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`result`|Обязательный.  Произвольное выражение типа `Boolean`.  При сравнении двух выражений будет получен результат типа `Boolean`.|  
|`expression1`|Обязательный.  Произвольное выражение типа `Boolean`.|  
|`expression2`|Обязательный.  Произвольное выражение типа `Boolean`.|  
  
## Заметки  
 Логическая операция называется *сокращенной*, если компилируемый код может пропустить оценку одного выражения, зависящего от результата другого выражения.  Если результат первого оцененного выражения определяет конечный результат операции, то отсутствует необходимость оценивать второе выражение, так как это не повлияет на конечный результат.  Сокращенное вычисление улучшает производительность, если пропущенное выражение является сложным или содержит вызовы процедур.  
  
 Если оба выражения определяются значением `True`, то результат `result` имеет значение `True`.  В следующей таблице показан порядок определения результата `result`.  
  
||||  
|-|-|-|  
|Если `expression1` имеет значение|И выражение `expression2` имеет значение|значение `result` будет следующим:|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|\(не вычисляется\)|`False`|  
  
## Типы данных  
 Оператор `AndAlso` определен только для типа данных Boolean \([Тип данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)\).  В Visual Basic каждый операнд при необходимости преобразуется в тип `Boolean`, после чего операция полностью выполняется с использованием типа `Boolean`.  Если результату назначить числовой тип, Visual Basic преобразует его из типа `Boolean` в этот тип.  Это может привести к непредвиденному поведению.  Например, результат операции `5 AndAlso 12` равен `–1`, если преобразуется в тип `Integer`.  
  
## Перегрузка  
 Оператор [Оператор And](../../../visual-basic/language-reference/operators/and-operator.md) и [Оператор IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md) может быть *перегруженным*. Это означает, что класс или структура может переопределить его поведение, если операнд имеет тип класса или структуры.  Перегрузка операторов`And` и `IsFalse` влияет на поведение оператора `AndAlso`.  Если в коде используется оператор `AndAlso` для класса или структуры, которая перегружает `And` и `IsFalse`, убедитесь, что вы понимаете его переопределенное поведение.  Дополнительные сведения см. в разделе [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Пример  
 В данном примере оператор `AndAlso` используется для выполнения логического умножения двух выражений.  Результат представляет собой значение `Boolean`, которое показывает, что объединенное выражение истинно.  Если первое выражение является `False`, второе выражение не оценивается.  
  
 [!code-vb[VbVbalrOperators#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_1.vb)]  
  
 В предыдущем примере получаются результаты `True`, `False` и `False`, соответственно.  При вычислении `secondCheck` второе выражение не вычисляется, поскольку первое значение уже равно `False`.  Тем не менее, второе выражение определяется при вычислении `thirdCheck`.  
  
## Пример  
 В следующем примере процедура `Function` выполняет поиск заданного значения среди элементов массива.  Если массив пуст или превышена длина массива, оператор `While` не проверяет элементы массива на значение поиска.  
  
 [!code-vb[VbVbalrOperators#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_2.vb)]  
  
## См. также  
 [Логические \(побитовые\) операторы](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Оператор And](../../../visual-basic/language-reference/operators/and-operator.md)   
 [Оператор IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md)   
 [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)