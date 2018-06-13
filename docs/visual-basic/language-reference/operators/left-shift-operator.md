---
title: '&lt;&lt; Оператор (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: bdec015309526aeac2499bc7b459b6ccab6f1e4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604462"
---
# <a name="ltlt-operator-visual-basic"></a>&lt;&lt; Оператор (Visual Basic)
Выполняет арифметическое смещение влево для битового шаблона.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = pattern << amount  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательно. Целое числовое значение. Результат сдвига разряда. Тип данных является так же, как `pattern`.  
  
 `pattern`  
 Обязательно. Целое числовое выражение. Сдвиг битового шаблона. Тип данных должен быть целочисленный тип (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, или `ULong`).  
  
 `amount`  
 Обязательно. Числовое выражение. Число битов, на которое производится Сдвиг битового шаблона. Тип данных должен быть `Integer` или расширить до `Integer`.  
  
## <a name="remarks"></a>Примечания  
 Арифметический сдвиг не циклической, это означает, что биты, сдвигаемые результата, не подставляются с другой стороны. В арифметический сдвиг влево биты, сдвигаемые дальше диапазона типа данных результата отбрасываются, а освободившиеся справа позиции битов заполняются нулями.  
  
 Чтобы предотвратить сдвиг на количество битов, превышающее битов результата, Visual Basic маскирует значение `amount` с помощью маски размера, соответствующее типу данных `pattern`. Двоичное AND этих значений используется для сдвига. Ниже приведены маски размера:  
  
|Тип данных `pattern`|Маска размера (десятичная)|Маска размера (шестнадцатеричная)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|&AMP; H00000007|  
|`Short`, `UShort`|15|&AMP; H0000000F|  
|`Integer`, `UInteger`|31|&AMP; H0000001F|  
|`Long`, `ULong`|63|&AMP; H0000003F|  
  
 Если `amount` равно 0, значение `result` идентична значение `pattern`. Если `amount` имеет отрицательное значение, он берется значение без знака и маскируется с маской соответствующего размера.  
  
 Арифметические сдвиги никогда не создаются исключения переполнения.  
  
> [!NOTE]
>  `<<` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что переопределенное его. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `<<` оператор для выполнения арифметических левых сдвигов целых значений. Результат всегда имеет тот же тип, что и выражение, подвергаемое сдвигу данных.  
  
 [!code-vb[VbVbalrOperators#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-operator_1.vb)]  
  
 Ниже приведены результаты предыдущего примера:  
  
-   `result1` — 192 (0000 0000 1100 0000).  
  
-   `result2` — большего 3072 пикселей (0000 1100 0000 0000).  
  
-   `result3` — от -32768 (1000 0000 0000 0000).  
  
-   `result4` — 384 (0000 0001 1000 0000).  
  
-   `result5` имеет значение 0 (сдвигаются 15 разрядов слева).  
  
 Величина сдвига для `result4` вычисляется как 17 AND 15, что равно 1.  
  
## <a name="see-also"></a>См. также  
 [Операторы сдвига битов](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Оператор <<=](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
