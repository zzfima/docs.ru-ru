---
title: Оператор AndAlso (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AndAlso
- AndAlso
helpviewer_keywords:
- short-circuiting
- AndAlso operator [Visual Basic]
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], conjunction
- short-circuit evaluation
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
ms.openlocfilehash: 1cb4d372d3ac228f29c6fa45f124796e5dfb6709
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2019
ms.locfileid: "67859885"
---
# <a name="andalso-operator-visual-basic"></a>Оператор AndAlso (Visual Basic)
Выполняет сокращенное вычисление логического умножения двух выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`result`|Обязательный. Произвольное выражение `Boolean` . В результате `Boolean` результат сравнения двух выражений.|  
|`expression1`|Обязательный. Произвольное выражение `Boolean` .|  
|`expression2`|Обязательный. Произвольное выражение `Boolean` .|  
  
## <a name="remarks"></a>Примечания  
 Логическая операция называется *сокращенного вычисления* Если скомпилированный код может пропустить вычисления одного выражения в зависимости от результата другого выражения. Если результат вычисления первого выражения определяет конечный результат операции, нет необходимости для вычисления второго выражения, так как он не может изменить результат. Сокращенное вычисление может повысить производительность, если пропущенное выражение является сложным или содержит вызовы процедур.  
  
 Если оба выражения имеют значение `True`, `result` является `True`. В следующей таблице показано как `result` определяется.  
  
|Если `expression1` —|И `expression2` —|Значение `result` —|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|(не вычисленное)|`False`|  
  
## <a name="data-types"></a>Типы данных  
 `AndAlso` Оператор определен только для [логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Visual Basic преобразует каждый операнд при необходимости `Boolean` перед вычислением выражения. Если результат назначается числовой тип, Visual Basic преобразует его из `Boolean` к этому типу таким образом, чтобы `False` становится `0` и `True` становится `-1`.
Дополнительные сведения см. в разделе [логическое преобразования типов](../data-types/boolean-data-type.md#type-conversions)
  
## <a name="overloading"></a>Перегрузка  
 [И оператором](../../../visual-basic/language-reference/operators/and-operator.md) и [оператор IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить их поведение, если операнд имеет тип, класс или структура. Перегрузка `And` и `IsFalse` операторы влияет на поведение `AndAlso` оператор. Если код использует `AndAlso` для класса или структуры, перегружающей `And` и `IsFalse`, убедитесь, что их переопределенное. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `AndAlso` оператору выполнять логическое умножение двух выражений. В результате `Boolean` значение, представляющее ли весь объединенных выражение имеет значение true. Если первое выражение является `False`, второй не вычисляется.  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 В предыдущем примере получался результат `True`, `False`, и `False`, соответственно. В расчет `secondCheck`, второе выражение не вычисляется, так как первый уже `False`. Однако второе выражение оценивается в расчете `thirdCheck`.  
  
## <a name="example"></a>Пример  
 В следующем примере показан `Function` процедуру, которая выполняет поиск заданного значения среди элементов массива. Если массив пуст или если длина массива было превышено, `While` инструкции не проверяет элемент массива на значение поиска.  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a>См. также

- [Логические (побитовые) операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Оператор And](../../../visual-basic/language-reference/operators/and-operator.md)
- [Оператор IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
