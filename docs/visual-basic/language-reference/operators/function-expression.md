---
title: Выражение Function (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: 0aa47fd277cfe47b3d8f08b41ffca9c547dcbfe9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839692"
---
# <a name="function-expression-visual-basic"></a>Выражение Function (Visual Basic)
Объявляет параметры и код, которые определяют функции лямбда-выражение.  
  
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
|`parameterlist`|Необязательный параметр. Список имен локальных переменных, представляющих параметры этой процедуры. Круглые скобки должен присутствовать даже в том случае, если список пуст. См. в разделе [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`expression`|Обязательный. Одно выражение. Тип выражения — тип возвращаемого значения функции.|  
|`statements`|Обязательный. Список инструкций, возвращает значение, используя `Return` инструкции. (См. в разделе [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).) Тип возвращаемого значения — тип возвращаемого значения функции.|  
  
## <a name="remarks"></a>Примечания  
 Объект *лямбда-выражение* является функцией без имени, которая вычисляет и возвращает значение. Лямбда-выражения можно использовать везде, где можно использовать тип делегата, кроме как аргумент `RemoveHandler`. Дополнительные сведения о делегатах и использование лямбда-выражений с делегатами, см. в разделе [оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) и [неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Синтаксис лямбда-выражений  
 Синтаксис лямбда-выражения похож стандартной функции. Ниже приведены различия.  
  
-   Лямбда-выражение не имеет имени.  
  
-   Лямбда-выражения не может иметь модификаторы, такие как `Overloads` или `Overrides`.  
  
-   Лямбда-выражения не используйте `As` предложение, чтобы указать тип возвращаемого значения функции. Вместо этого тип выводится из, тело однострочных лямбда-выражение, результатом которого является значение или возвращаемое значение многострочного лямбда-выражения. Например, если текст однострочное лямбда-выражения `Where cust.City = "London"`, его возвращаемый тип — `Boolean`.  
  
-   Тело однострочное лямбда-выражения должно быть выражением, а не оператором. Текст может состоять из вызова процедуры функции, но не вызов процедуры sub.  
  
-   Необходимо заранее указать все параметры, что необходимо определить типы данных или все.  
  
-   Optional и Paramarray параметров не разрешены.  
  
-   Универсальные параметры не допускаются.  
  
## <a name="example"></a>Пример  
 В следующих примерах показано два способа создания простых лямбда-выражений. Первый использует `Dim` для предоставления имени функции. Для вызова функции, вы отправляете в значение параметра.  
  
 [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
## <a name="example"></a>Пример  
 Кроме того можно объявить и запустить функцию, в то же время.  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
## <a name="example"></a>Пример  
 Ниже приведен пример лямбда-выражения, увеличивает значение своего аргумента и возвращает значение. В этом примере синтаксис однострочный и многострочный лямбда-выражения для функции. Дополнительные примеры см. в разделе [лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
## <a name="example"></a>Пример  
 Лямбда-выражения лежат в основе многих операторов запроса в [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]и может использоваться в запросах на основе методов явным образом. В следующем примере показан типичный [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запроса, за преобразования запроса в формат метода.  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 Дополнительные сведения о методах запросов см. в разделе [запросы](../../../visual-basic/language-reference/queries/index.md). Дополнительные сведения о стандартных операторах запросов см. в разделе [Общие сведения о стандартных операторах запроса](../../programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
## <a name="see-also"></a>См. также

- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
- [Сравнения значений](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Логические выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Оператор If](../../../visual-basic/language-reference/operators/if-operator.md)
- [Неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
