---
title: '&amp;Оператор (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: aaa7c1b9ab7f6c920180d97b55c3bdeb23f00e02
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592245"
---
# <a name="amp-operator-visual-basic"></a>&amp;Оператор (Visual Basic)
Формирует объединение строк двух выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Любая переменная `String` или `Object`.  
  
 `expression1`  
 Обязательный. Любое выражение с типом данных, которое расширяется до `String`.  
  
 `expression2`  
 Обязательный. Любое выражение с типом данных, которое расширяется до `String`.  
  
## <a name="remarks"></a>Примечания  
 Если тип данных `expression1` или `expression2` не `String`, но расширяется до `String`, он преобразуется в `String`. Если любой из типов данных не расширяется до `String`, компилятор выдает ошибку.  
  
 Тип данных `result` — `String`. Если одно или оба выражения имеют значение [Nothing](../../../visual-basic/language-reference/nothing.md) или не имеют значения <xref:System.DBNull.Value?displayProperty=nameWithType>, они обрабатываются как строка со значением "".  
  
> [!NOTE]
> Оператор `&` можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
> Символ амперсанда (&) также можно использовать для задания переменных в качестве типа `Long`. Дополнительные сведения см. в разделе [символы типа](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="example"></a>Пример  
 В этом примере для принудительного сцепления строк используется оператор `&`. Результатом является строковое значение, представляющее объединение двух строковых операндов.  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>См. также

- [Оператор &=](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Операторы объединения](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы объединения в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
