---
title: Оператор Not
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
ms.openlocfilehash: 08b091ccf6c50438b5ad9d6c445510112abe7418
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348299"
---
# <a name="not-operator-visual-basic"></a>Оператор Not (Visual Basic)
Выполняет логическое отрицание в выражении `Boolean` или побитовое отрицание в числовом выражении.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
result = Not expression  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательно. Любое `Boolean` или числовое выражение.  
  
 `expression`  
 Обязательно. Любое `Boolean` или числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Для `Boolean` выражений в следующей таблице показано, как определяется `result`.  
  
|Если `expression`|Значение `result` равно|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 Для числовых выражений оператор `Not` инвертирует битовые значения любого числового выражения и устанавливает соответствующий бит в `result` в соответствии со следующей таблицей.  
  
|Если бит в `expression` имеет значение|Бит в `result`|  
|-------------------------------|----------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
> Так как логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, все битовые операции должны быть заключены в круглые скобки, чтобы обеспечить точное выполнение.  
  
## <a name="data-types"></a>Типы данных  
 Для логического отрицания тип данных результата `Boolean`. Для побитового отрицания тип данных результата такой же, как у `expression`. Однако если выражение `Decimal`, результатом будет `Long`.  
  
## <a name="overloading"></a>Перегрузка  
 Оператор `Not` может быть *перегружен*, а это означает, что класс или структура могут переопределять свое поведение, когда его операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `Not` используется для выполнения логического отрицания в выражении `Boolean`. Результатом является `Boolean` значение, представляющее обратную величину значения выражения.  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 В предыдущем примере создаются результаты `False` и `True`соответственно.  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `Not` используется для выполнения логического отрицания отдельных битов числового выражения. Бит в результирующем шаблоне имеет значение, противоположное соответствующему биту в шаблоне операнда, включая бит знака.  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 В предыдущем примере создаются результаты – 11, – 9 и – 7 соответственно.  
  
## <a name="see-also"></a>См. также

- [Логические и битовые операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
