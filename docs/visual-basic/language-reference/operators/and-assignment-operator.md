---
title: Оператор &amp;=
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: 8668bfcbf32bb34b422efe8116bbd12a2d80b1d4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350267"
---
# <a name="amp-operator-visual-basic"></a>Оператор &amp;= (Visual Basic)
Сцепляет `String` выражение с переменной или свойством `String` и присваивает результат переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Обязательно. Любая переменная `String` или свойство.  
  
 `expression`  
 Обязательно. Произвольное выражение `String` .  
  
## <a name="remarks"></a>Заметки  
 Элемент в левой части оператора `&=` может быть простой скалярной переменной, свойством или элементом массива. Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md). Оператор `&=` объединяет выражение `String` справа с переменной `String` или свойством слева и присваивает результат переменной или свойству слева.  
  
## <a name="overloading"></a>Перегрузка  
 [Оператор &](../../../visual-basic/language-reference/operators/concatenation-operator.md) может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Перегрузка оператора `&` влияет на поведение оператора `&=`. Если в коде используется `&=` в классе или структуре, которая перегружает `&`, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `&=` используется для сцепления двух `String` переменных и присваивания результата первой переменной.  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>См. также

- [Оператор &](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [Оператор +=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Операторы объединения](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
