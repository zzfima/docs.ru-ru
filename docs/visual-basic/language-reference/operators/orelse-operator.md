---
title: "Оператор OrElse (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "OrElse"
  - "vb.OrElse"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "операторы [Visual Basic], дизъюнкция"
  - "операторы [Visual Basic], сокращенные вычисления"
  - "OrElse - оператор [Visual Basic]"
  - "сокращенные вычисления"
  - "сокращенные вычисления"
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Оператор OrElse (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Выполняет сокращенное вычисление логического сложения двух выражений.  
  
## Синтаксис  
  
```  
  
result = expression1 OrElse expression2  
```  
  
## Части  
 `result`  
 Обязательный.  Произвольное выражение типа `Boolean`.  
  
 `expression1`  
 Обязательный.  Произвольное выражение типа `Boolean`.  
  
 `expression2`  
 Обязательный.  Произвольное выражение типа `Boolean`.  
  
## Заметки  
 Логическая операция называется *сокращенной*, если компилируемый код может пропустить оценку одного выражения, зависящего от результата другого выражения.  Если результат первого оцененного выражения определяет конечный результат операции, то отсутствует необходимость оценивать второе выражение, так как это не повлияет на конечный результат.  Сокращенное вычисление улучшает производительность, если пропущенное выражение является сложным или содержит вызовы процедур.  
  
 Если оба выражения имеют значения `True`, то `result` тоже `True`.  В следующей таблице показан порядок определения результата `result`.  
  
|Если `expression1` имеет значение|И выражение `expression2` имеет значение|значение `result` будет следующим:|  
|---------------------------------------|----------------------------------------------|----------------------------------------|  
|`True`|\(не вычисляется\)|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## Типы данных  
 Оператор `OrElse` определен только для [Тип данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md).  В Visual Basic каждый операнд при необходимости преобразуется в тип `Boolean`, после чего операция полностью выполняется с использованием типа `Boolean`.  Если результату назначить числовой тип, Visual Basic преобразует его из типа `Boolean` в этот тип.  Это может привести к непредвиденному поведению.  Например, результат `5 OrElse 12` равен `–1` при преобразовании к типу `Integer`.  
  
## Перегрузка  
 Оператор [Оператор Or](../../../visual-basic/language-reference/operators/or-operator.md) и [Оператор IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md) может быть *перегруженным*. Это означает, что класс или структура может переопределить его поведение, если операнд имеет тип класса или структуры.  Перегрузка операторов`Or` и `IsTrue` влияет на поведение оператора `OrElse`.  Если в коде используется оператор `OrElse` для класса или структуры, которая перегружает `Or` и `IsTrue`, убедитесь, что вы понимаете его переопределенное поведение.  Дополнительные сведения см. в разделе [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Пример  
 В данном примере оператор `OrElse` используется для выполнения логического сложения двух выражений.  Результат представляет собой значение типа `Boolean`, показывающее, является ли какое\-либо из выражений истинным.  Если первое выражение является `True`, второе выражение не оценивается.  
  
 [!code-vb[VbVbalrOperators#37](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/orelse-operator_1.vb)]  
  
 В предыдущем примере формируются результаты `True`, `True` и `False` соответственно.  При вычислении `firstCheck` второе выражение не вычисляется, поскольку первое значение уже равно `True`.  Тем не менее второе выражение вычисляется в расчете `secondCheck`.  
  
## Пример  
 В следующем примере показывается оператор `If`...`Then`,содержащий два вызова процедур.  Если первый вызов возвращает `True`, вторая процедура не вызывается.  Это может привести к непредсказуемым результатам, если вторая процедура выполняет важные задачи, которые должны всегда быть выполнены при запуске в этом разделе кода.  
  
 [!code-vb[VbVbalrOperators#38](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/orelse-operator_2.vb)]  
  
## См. также  
 [Логические \(побитовые\) операторы](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Оператор Or](../../../visual-basic/language-reference/operators/or-operator.md)   
 [Оператор IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md)   
 [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)