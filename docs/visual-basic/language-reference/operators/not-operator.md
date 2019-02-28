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
ms.openlocfilehash: db88b61518a52a70553c037fdd95f9a135dcb268
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981222"
---
# <a name="not-operator-visual-basic"></a>Оператор Not (Visual Basic)
Выполняет логическое отрицание `Boolean` выражения или побитовое отрицание в числовом выражении.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Любой `Boolean` или числовое выражение.  
  
 `expression`  
 Обязательный. Любой `Boolean` или числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Для `Boolean` выражения, в следующей таблице показано как `result` определяется.  
  
|Если `expression` —|Значение `result` —|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 Для числовых выражений `Not` оператор инвертирует значения битов числового выражения и устанавливает значение соответствующего бита в `result` согласно следующей таблице.  
  
|Если бит в `expression` —|Бит в `result` —|  
|-------------------------------|----------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
>  Поскольку логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, битовые операции следует заключать в круглые скобки, чтобы обеспечить правильное выполнение.  
  
## <a name="data-types"></a>Типы данных  
 Для логического отрицания тип данных результата — `Boolean`. Для поразрядного отрицания, тип данных результата будет таким же, как `expression`. Тем не менее если выражение является `Decimal`, в результате `Long`.  
  
## <a name="overloading"></a>Перегрузка  
 `Not` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если его операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Not` оператор логического отрицания `Boolean` выражение. В результате `Boolean` значение, которое представляет обратное значение выражения.  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 В предыдущем примере получался результат `False` и `True`, соответственно.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Not` оператор для выполнения логического отрицания отдельных битов числового выражения. Бит в шаблоне результат присваивается обратное соответствующий бит в шаблоне операнда, включая бит знака.  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 В предыдущем примере получался результаты – 11, – 9 и – 7 соответственно.  
  
## <a name="see-also"></a>См. также
- [Логические (побитовые) операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
