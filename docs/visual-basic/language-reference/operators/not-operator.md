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
ms.openlocfilehash: 29e2b159e4c6261a62e788b537102b9b457fe0c8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955824"
---
# <a name="not-operator-visual-basic"></a>Оператор Not (Visual Basic)
Выполняет логическое отрицание `Boolean` выражения или побитовое отрицание в числовом выражении.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Любое `Boolean` или числовое выражение.  
  
 `expression`  
 Обязательный. Любое `Boolean` или числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Для `Boolean` выражений в следующей таблице показано, как `result` определяется.  
  
|Если `expression` имеет значение|Значение `result` равно|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 Для числовых выражений `Not` оператор инвертирует битовые значения любого числового выражения и устанавливает соответствующий бит в `result` соответствии со следующей таблицей.  
  
|Если бит в `expression` имеет значение|Бит в `result` имеет значение|  
|-------------------------------|----------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
> Так как логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, все битовые операции должны быть заключены в круглые скобки, чтобы обеспечить точное выполнение.  
  
## <a name="data-types"></a>Типы данных  
 Для логического отрицания тип данных результата — `Boolean`. Для побитового отрицания тип данных результата такой же, как `expression`и у. Однако если выражение имеет значение `Decimal`, результатом будет. `Long`  
  
## <a name="overloading"></a>Перегрузка  
 Оператор можно перегрузить, что означает, что класс или структура может переопределить свое поведение, если его операнд имеет тип этого класса или структуры. `Not` Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере `Not` оператор используется для выполнения логического отрицания `Boolean` в выражении. Результатом является `Boolean` значение, представляющее обратную величину значения выражения.  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 В предыдущем примере создаются результаты `False` и `True`соответственно.  
  
## <a name="example"></a>Пример  
 В следующем примере `Not` оператор используется для выполнения логического отрицания отдельных битов числового выражения. Бит в результирующем шаблоне имеет значение, противоположное соответствующему биту в шаблоне операнда, включая бит знака.  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 В предыдущем примере создаются результаты – 11, – 9 и – 7 соответственно.  
  
## <a name="see-also"></a>См. также

- [Логические и битовые операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
