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
ms.openlocfilehash: d387b2dfdbb3fefe357364f7b2a3dde155cbd489
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968358"
---
# <a name="amp-operator-visual-basic"></a>&amp;Оператор (Visual Basic)
Формирует объединение строк двух выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Любая `String` переменная `Object` или.  
  
 `expression1`  
 Обязательный. Любое выражение с типом данных, которое расширяется до `String`.  
  
 `expression2`  
 Обязательный. Любое выражение с типом данных, которое расширяется до `String`.  
  
## <a name="remarks"></a>Примечания  
 `expression1` Если тип `String`данных или `expression2` не `String` имеет значение, а расширяется до `String`, то он преобразуется в. Если один из типов данных не расширяется до `String`, компилятор выдает ошибку.  
  
 Тип `result` данных — `String`. Если одно или оба выражения имеют значение [Nothing](../../../visual-basic/language-reference/nothing.md) или не имеют значения <xref:System.DBNull.Value?displayProperty=nameWithType>, они обрабатываются как строка со значением "".  
  
> [!NOTE]
> Оператор можно перегрузить, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. `&` Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
> Символ амперсанда (&) также можно использовать для задания переменных в качестве типа `Long`. Дополнительные сведения см. в разделе [символы типа](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="example"></a>Пример  
 В этом примере `&` оператор используется для принудительного сцепления строк. Результатом является строковое значение, представляющее объединение двух строковых операндов.  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>См. также

- [Оператор &=](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Операторы объединения](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы объединения в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
