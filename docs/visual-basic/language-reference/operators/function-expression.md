---
title: "Выражение Function (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Function - выражение [Visual Basic]"
  - "функции [Visual Basic], выражения функций"
  - "лямбда-выражения [Visual Basic], выражение функции"
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Выражение Function (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Объявляет параметры и код, который определяет функцию\-лямбда\-выражение.  
  
## Синтаксис  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`parameterlist`|Необязательный.  Список имен локальных переменных, представляющих параметры этой процедуры.  Круглые скобки должны присутствовать даже если список пуст.  Дополнительные сведения см. в разделе [Список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`expression`|Обязательный.  Одиночное выражение.  Тип выражения — возвращаемый тип функции.|  
|`statements`|Обязательный.  Список операторов, возвращающих значение с помощью оператора`Return` .  \(См. раздел [Оператор Return](../../../visual-basic/language-reference/statements/return-statement.md)\). Тип возвращаемого значения — возвращаемый тип функции.|  
  
## Заметки  
 *Лямбда\-выражение* представляет собой функцию без имени для вычисления и возврата значения.  Можно использовать лямбда\-выражение везде, где можно использовать тип делегата, за исключением использования в качестве аргумента в `RemoveHandler`.  Дополнительные сведения о делегатах и использовании лямбда\-выражений с делегатами см. в разделах [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) и [Неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## Синтаксис лямбда\-выражений  
 Синтаксис лямбда\-выражения схож с синтаксисом стандартной функции.  Различия заключаются в следующем:  
  
-   Лямбда\-выражение не имеет имени.  
  
-   Лямбда\-выражения не могут включать модификаторы, такие как `Overloads` или `Overrides`.  
  
-   Лямбда\-выражения не используют предложение `As` для обозначения типа возвращаемого значения функции.  Вместо этого тип выводится из значения, которое вычисляется в теле однострочного лямбда\-выражения. или из возвращаемого значения многострочного лямбда\-выражения.  Например, если тело однострочного лямбда\-выражения — `Where cust.City = "London"`, возвращается тип `Boolean`.  
  
-   Телом однострокового лямбда\-выражения должно быть выражение, а не оператор.  Тело может содержать вызов процедуры Function, но не вызов процедуры Sub.  
  
-   Все параметры должны иметь определенный или выводимый тип данных.  
  
-   Параметры Optional и Paramarray не разрешены.  
  
-   Универсальные параметры не разрешены.  
  
## Пример  
 В следующем примере показано два способа создания простых лямбда\-выражений.  Первый использует `Dim` для предоставления имени функции.  Чтобы вызвать функцию, передайте ее значение в качестве параметра.  
  
 [!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]  
  
 [!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]  
  
## Пример  
 Кроме того, можно и объявить и запустить функцию одновременно.  
  
 [!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]  
  
## Пример  
 В следующем примере лямбда\-выражение увеличивает значение своего аргумента и возвращает его.  В примере показан синтаксис однострокового и многострокового лямбда\-выражения для функции.  Дополнительные примеры см. в разделе [Лямбда\-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]  
  
## Пример  
 Лямбда\-выражения лежат в основе многих операторов запроса [!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext_md.md)], и могут быть явно использованы в запросах на основе методов.  В следующем примере показан типичный запрос [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)], с приведением результата запроса в формат метода.  
  
```vb#  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 Дополнительные сведения о методах запросов см. в разделе [Запросы](../../../visual-basic/language-reference/queries/queries.md).  Дополнительные сведения о стандартных операторах запроса см в разделе [Standard Query Operators Overview](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
## См. также  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Лямбда\-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Сравнения значений](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Логические выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)   
 [Оператор If](../../../visual-basic/language-reference/operators/if-operator.md)   
 [Неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)