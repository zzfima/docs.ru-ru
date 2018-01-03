---
title: "Выражение Function (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cb1790d363755fe9b8bd711409734f7c3a405f3e
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="function-expression-visual-basic"></a>Выражение Function (Visual Basic)
Объявляет параметры и код, определяющий функции лямбда-выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`parameterlist`|Необязательный. Список имен локальных переменных, которые представляют параметры этой процедуры. Круглые скобки должны присутствовать даже в том случае, если список пуст. В разделе [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`expression`|Обязательно. Одно выражение. Тип выражения имеет тип возвращаемого значения функции.|  
|`statements`|Обязательно. Список инструкций, возвращает значение, используя `Return` инструкции. (См. [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).) Тип возвращаемого значения имеет тип возвращаемого значения функции.|  
  
## <a name="remarks"></a>Примечания  
 Объект *лямбда-выражение* является функцией без имени, которая вычисляет и возвращает значение. Лямбда-выражение можно использовать везде, где можно использовать тип делегата, за исключением того, как аргумент `RemoveHandler`. Дополнительные сведения о делегатах и использование лямбда-выражений с делегатами см. в разделе [оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) и [неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Синтаксис лямбда-выражений  
 Синтаксис лямбда-выражение напоминает стандартной функции. Существуют следующие различия.  
  
-   Лямбда-выражение не имеет имени.  
  
-   Лямбда-выражения не может содержать модификаторы, такие как `Overloads` или `Overrides`.  
  
-   Лямбда-выражения не используйте `As` предложений, чтобы указать тип возвращаемого значения функции. Вместо этого тип выводится из, тексте однострочный лямбда-выражение, результатом которого является значение или возвращаемое значение многострочного лямбда-выражения. Например, если текст Однострочные лямбда-выражения `Where cust.City = "London"`, его возвращаемый тип является `Boolean`.  
  
-   Текст Однострочные лямбда-выражения должен быть выражением, а не оператором. Текст может состоять из вызова процедуры function, но не вызов процедуры sub.  
  
-   Все параметры необходимо задать, необходимо определить типы данных или все.  
  
-   Optional и Paramarray параметры не разрешены.  
  
-   Универсальные параметры не допускаются.  
  
## <a name="example"></a>Пример  
 В следующих примерах показано два способа создания простых лямбда-выражений. Первый использует `Dim` для предоставления имени функции. Для вызова функции, отправить в значение параметра.  
  
 [!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]  
  
 [!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]  
  
## <a name="example"></a>Пример  
 Кроме того можно объявить и запустить функцию, в то же время.  
  
 [!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]  
  
## <a name="example"></a>Пример  
 Ниже приведен пример лямбда-выражения, которая увеличивает значение своего аргумента и возвращает значение. В примере синтаксиса однострочный и многострочный лямбда-выражения для функции. Дополнительные примеры см. в разделе [лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]  
  
## <a name="example"></a>Пример  
 Лямбда-выражения лежат в основе многих операторов запроса в [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]и может использоваться в запросах на основе методов явным образом. В следующем примере показано типичное [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запрос, с приведением результата запроса в формат метода.  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 Дополнительные сведения о методах запросов см. в разделе [запросы](../../../visual-basic/language-reference/queries/queries.md). Дополнительные сведения о стандартных операторах запросов см. в разделе [Общие сведения о стандартных операторах запроса](../../programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
## <a name="see-also"></a>См. также  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)  
 [Сравнения значений](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [Логические выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [Оператор If](../../../visual-basic/language-reference/operators/if-operator.md)  
 [Неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
