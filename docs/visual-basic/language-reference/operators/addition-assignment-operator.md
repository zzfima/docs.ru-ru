---
title: Оператор +=
ms.date: 07/20/2015
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
ms.openlocfilehash: 31a6da163061b905b8ffddcfc4b44978f5cdd55e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350305"
---
# <a name="-operator-visual-basic"></a>Оператор += (Visual Basic)
Добавляет значение числового выражения к значению числовой переменной или свойства и присваивает результат переменной или свойству. Можно также использовать для сцепления `String` выражения с `String` переменной или свойством и назначения результата переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
variableorproperty += expression  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Обязательно. Любая числовая или `String` переменная или свойство.  
  
 `expression`  
 Обязательно. Любое числовое или `String` выражение.  
  
## <a name="remarks"></a>Заметки  
 Элемент в левой части оператора `+=` может быть простой скалярной переменной, свойством или элементом массива. Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Оператор `+=` добавляет значение справа к переменной или свойству слева и присваивает результат переменной или свойству слева. Оператор `+=` также можно использовать для сцепления выражения `String` справа с переменной `String` или свойством слева и назначения результата переменной или свойству слева.  
  
> [!NOTE]
> При использовании оператора `+=`, возможно, не удастся определить, будет ли выполняться сложение или объединение строк. Используйте оператор `&=` для объединения, чтобы избежать неоднозначности и предоставить код для самостоятельного документирования.  
  
 Этот оператор присваивания неявно выполняет расширяющие, но не сужающие преобразования, если среда компиляции применяет строгую семантику. Дополнительные сведения об этих преобразованиях см. в разделе [расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md). Дополнительные сведения о семантике строгих и неразрешений см. в разделе [оператор Option строгий](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
 Если семантика разрешений разрешена, оператор `+=` неявно выполняет различные строковые и числовые преобразования, идентичные значениям, выполняемым оператором `+`. Дополнительные сведения об этих преобразованиях см. в разделе [оператор +](../../../visual-basic/language-reference/operators/addition-operator.md).  
  
## <a name="overloading"></a>Перегрузка  
 Оператор `+` может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Перегрузка оператора `+` влияет на поведение оператора `+=`. Если в коде используется `+=` в классе или структуре, которая перегружает `+`, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `+=` используется для объединения значения одной переменной с другой. Первая часть использует `+=` с числовыми переменными для добавления одного значения в другое. Во второй части используется `+=` с переменными `String` для сцепления одного значения с другим. В обоих случаях результат присваивается первой переменной.  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 Значение `num1` теперь равно 13, а значение `str1` теперь равно "103".  
  
## <a name="see-also"></a>См. также

- [Оператор +](../../../visual-basic/language-reference/operators/addition-operator.md)
- [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Операторы объединения](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
