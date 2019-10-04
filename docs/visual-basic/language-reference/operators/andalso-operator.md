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
ms.openlocfilehash: a52f598c8a7c7a79b0f2436f1add7b3eb5d5261b
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71835231"
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
|`result`|Обязательный. Произвольное выражение `Boolean` . Результатом является `Boolean` при сравнении двух выражений.|  
|`expression1`|Обязательный. Произвольное выражение `Boolean` .|  
|`expression2`|Обязательный. Произвольное выражение `Boolean` .|  
  
## <a name="remarks"></a>Примечания  
 Логическая операция называется *сокращенной* , если скомпилированный код может обходить вычисление одного выражения в зависимости от результата другого выражения. Если результат вычисления первого выражения определяет окончательный результат операции, нет необходимости оценивать второе выражение, так как оно не может изменить окончательный результат. Сокращенное вычисление может повысить производительность, если пропущенное выражение является сложным или если оно включает вызовы процедур.  
  
 Если оба выражения имеют значение `True`, `result` — `True`. В следующей таблице показано, как определяется `result`.  
  
|Если `expression1` имеет значение|И `expression2` является|Значение `result` равно|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|(не вычислено)|`False`|  
  
## <a name="data-types"></a>Типы данных  
 Оператор `AndAlso` определен только для [типа данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md). При необходимости Visual Basic преобразует каждый операнд в `Boolean` перед вычислением выражения. Если результат присваивается числовому типу, Visual Basic преобразует его из `Boolean` в этот тип, чтобы `False` стало `0`, а `True` преобразуется в `-1`.
Дополнительные сведения см. в разделе [преобразования логических типов](../data-types/boolean-data-type.md#type-conversions).
  
## <a name="overloading"></a>Перегрузка  
 [Операторы and](../../../visual-basic/language-reference/operators/and-operator.md) и [IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md) можно *перегружать*, что означает, что класс или структура могут переопределять их поведение, когда операнд имеет тип этого класса или структуры. Перегрузка операторов `And` и `IsFalse` влияет на поведение оператора `AndAlso`. Если в коде используется `AndAlso` для класса или структуры, которая перегружает `And` и `IsFalse`, убедитесь, что вы понимаете их переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `AndAlso` используется для выполнения логического умножения двух выражений. Результатом является значение `Boolean`, которое показывает, является ли все соединение истинным. Если первое выражение — `False`, второе значение не вычисляется.  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 В предыдущем примере создаются результаты `True`, `False` и `False` соответственно. При вычислении `secondCheck` второе выражение не вычисляется, поскольку первый уже `False`. Однако второе выражение вычисляется в вычислении `thirdCheck`.  
  
## <a name="example"></a>Пример  
 В следующем примере показана процедура `Function`, которая осуществляет поиск заданного значения в элементах массива. Если массив пуст или превышена длина массива, то оператор `While` не проверяет элемент массива на соответствие значению поиска.  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a>См. также

- [Логические и битовые операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Оператор And](../../../visual-basic/language-reference/operators/and-operator.md)
- [Оператор IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
