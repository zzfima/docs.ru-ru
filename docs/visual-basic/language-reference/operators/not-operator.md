---
title: Оператор Not (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
ms.openlocfilehash: 5ebc5f9dbf674a9a6560bd96b3e8c9edcae08a81
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701082"
---
# <a name="not-operator-visual-basic"></a>Оператор Not (Visual Basic)
Выполняет логическое отрицание в выражении `Boolean` или побитовое отрицание числового выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
result = Not expression  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Любое `Boolean` или числовое выражение.  
  
 `expression`  
 Обязательный. Любое `Boolean` или числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Для выражений `Boolean` в следующей таблице показано, как определяется `result`.  
  
|Если `expression` имеет значение|Значение `result` равно|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 Для числовых выражений оператор `Not` инвертирует битовые значения любого числового выражения и устанавливает соответствующий бит в `result` в соответствии со следующей таблицей.  
  
|Если бит в `expression` равен|Бит в `result` является|  
|-------------------------------|----------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
> Так как логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, все битовые операции должны быть заключены в круглые скобки, чтобы обеспечить точное выполнение.  
  
## <a name="data-types"></a>Типы данных  
 Для логического отрицания тип данных результата — `Boolean`. Для побитового отрицания тип данных результата такой же, как и в `expression`. Однако если выражение имеет значение `Decimal`, результатом будет `Long`.  
  
## <a name="overloading"></a>Перегрузка  
 Оператор `Not` может быть *перегружен*, что означает, что класс или структура может переопределить его поведение, если его операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `Not` используется для выполнения логического отрицания в выражении `Boolean`. Результатом является значение `Boolean`, представляющее обратный результат выражения.  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 В предыдущем примере создаются результаты `False` и `True` соответственно.  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `Not` используется для выполнения логического отрицания отдельных битов числового выражения. Бит в результирующем шаблоне имеет значение, противоположное соответствующему биту в шаблоне операнда, включая бит знака.  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 В предыдущем примере создаются результаты – 11, – 9 и – 7 соответственно.  
  
## <a name="see-also"></a>См. также

- [Логические и битовые операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
