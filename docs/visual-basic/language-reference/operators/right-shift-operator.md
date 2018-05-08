---
title: '&gt;&gt; Оператор (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>
helpviewer_keywords:
- operator>>
- '>> operator [Visual Basic]'
- bit shift operators [Visual Basic]
- operator >>
- right shift operators [Visual Basic]
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
ms.openlocfilehash: 9bb8e82b3f5451417fe1867d08b7601ee1acb036
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="gtgt-operator-visual-basic"></a>&gt;&gt; Оператор (Visual Basic)
Выполняет арифметический сдвиг вправо для битового шаблона.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = pattern >> amount  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательно. Целое числовое значение. Результат сдвига разряда. Тип данных является так же, как `pattern`.  
  
 `pattern`  
 Обязательно. Целое числовое выражение. Сдвиг битового шаблона. Тип данных должен быть целочисленный тип (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, или `ULong`).  
  
 `amount`  
 Обязательно. Числовое выражение. Число битов, на которое производится Сдвиг битового шаблона. Тип данных должен быть `Integer` или расширить до `Integer`.  
  
## <a name="remarks"></a>Примечания  
 Арифметический сдвиг не циклической, это означает, что биты, сдвигаемые результата, не подставляются с другой стороны. В арифметический сдвиг вправо биты, сдвигаемые дальше крайней правой позиции отбрасываются, а крайний левый (знаковый) бит передается в освободившиеся слева позиции битов. Это означает, что если `pattern` имеет отрицательное значение, освобождаемые устанавливаются в один; в противном случае они заполняются нулями.  
  
 Обратите внимание, что типы данных `Byte`, `UShort`, `UInteger`, и `ULong` не подписаны, то есть не знаковый бит для передачи. Если `pattern` имеет любой тип без учета знака, освобождаемые всегда равен нулю.  
  
 Чтобы предотвратить сдвиг на количество битов, превышающее битов результата, Visual Basic маскирует значение `amount` с помощью маски размера, соответствующей типу данных элемента `pattern`. Двоичное AND этих значений используется для сдвига. Ниже приведены маски размера:  
  
|Тип данных `pattern`|Маска размера (десятичная)|Маска размера (шестнадцатеричная)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|&AMP; H00000007|  
|`Short`, `UShort`|15|&AMP; H0000000F|  
|`Integer`, `UInteger`|31|&AMP; H0000001F|  
|`Long`, `ULong`|63|&AMP; H0000003F|  
  
 Если `amount` равно 0, значение `result` идентична значение `pattern`. Если `amount` имеет отрицательное значение, он берется значение без знака и маскируется с маской соответствующего размера.  
  
 Арифметические сдвиги никогда не создаются исключения переполнения.  
  
## <a name="overloading"></a>Перегрузка  
 `>>` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `>>` оператор для выполнения арифметических правых сдвигов целых значений. Результат всегда имеет тот же тип, что и выражение, подвергаемое сдвигу данных.  
  
 [!code-vb[VbVbalrOperators#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_1.vb)]  
  
 Ниже приведены результаты предыдущего примера:  
  
-   `result1` — 2560 (0000 1010 0000 0000).  
  
-   `result2` — 160 (0000 0000 1010 0000).  
  
-   `result3` -2 (0000 0000 0000 0010).  
  
-   `result4` — 640 (0000 0010 1000 0000).  
  
-   `result5` имеет значение 0 (сдвигаются 15 разрядов справа).  
  
 Величина сдвига для `result4` рассчитывается как 18 и 15, что равно 2.  
  
 В следующем примере показано арифметические сдвиги отрицательных значений.  
  
 [!code-vb[VbVbalrOperators#55](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_2.vb)]  
  
 Ниже приведены результаты предыдущего примера:  
  
-   `negresult1` Это -512 (1111 1110 0000 0000).  
  
-   `negresult2` -1 (распространяется бит знака).  
  
## <a name="see-also"></a>См. также  
 [Операторы сдвига битов](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Оператор >>=](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
