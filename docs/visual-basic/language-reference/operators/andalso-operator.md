---
title: Оператор AndAlso
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
ms.openlocfilehash: b3801c7e05142e1bc793e3c9d49a6f6991756f9d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350240"
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
|`result`|Обязательно. Произвольное выражение `Boolean` . Результатом является `Boolean` результат сравнения двух выражений.|  
|`expression1`|Обязательно. Произвольное выражение `Boolean` .|  
|`expression2`|Обязательно. Произвольное выражение `Boolean` .|  
  
## <a name="remarks"></a>Примечания  
 Логическая операция называется *сокращенной* , если скомпилированный код может обходить вычисление одного выражения в зависимости от результата другого выражения. Если результат вычисления первого выражения определяет окончательный результат операции, нет необходимости оценивать второе выражение, так как оно не может изменить окончательный результат. Сокращенное вычисление может повысить производительность, если пропущенное выражение является сложным или если оно включает вызовы процедур.  
  
 Если оба выражения оцениваются как `True`, `result` `True`. В следующей таблице показано, как определяется `result`.  
  
|Если `expression1`|И `expression2`|Значение `result` равно|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|(не вычислено)|`False`|  
  
## <a name="data-types"></a>Типы данных  
 Оператор `AndAlso` определен только для [типа данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Visual Basic преобразует каждый операнд по мере необходимости для `Boolean` перед вычислением выражения. Если результат присваивается числовому типу, Visual Basic преобразует его из `Boolean` в такой тип, чтобы `False` `0`, а `True` — `-1`.
Дополнительные сведения см. в разделе [преобразования логических типов](../data-types/boolean-data-type.md#type-conversions).
  
## <a name="overloading"></a>Перегрузка  
 [Операторы and](../../../visual-basic/language-reference/operators/and-operator.md) и [IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md) можно *перегружать*, что означает, что класс или структура могут переопределять их поведение, когда операнд имеет тип этого класса или структуры. Перегрузка операторов `And` и `IsFalse` влияет на поведение оператора `AndAlso`. Если в коде используется `AndAlso` для класса или структуры, которая перегружает `And` и `IsFalse`, убедитесь, что вы понимаете их переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `AndAlso` используется для выполнения логического умножения двух выражений. Результатом является `Boolean`ое значение, которое показывает, является ли истинным полное соединение выражения. Если первое выражение является `False`, второе значение не вычисляется.  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 В предыдущем примере создаются результаты `True`, `False`и `False`соответственно. При вычислении `secondCheck`второе выражение не вычисляется, поскольку первый уже `False`. Однако второе выражение вычисляется в вычислении `thirdCheck`.  
  
## <a name="example"></a>Пример  
 В следующем примере показана `Function` процедура, выполняющая поиск заданного значения в элементах массива. Если массив пуст или превышена длина массива, то оператор `While` не проверяет элемент массива на соответствие значению поиска.  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a>См. также

- [Логические и битовые операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Оператор And](../../../visual-basic/language-reference/operators/and-operator.md)
- [Оператор IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
