---
title: '>> Operator (Visual Basic)'
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
ms.openlocfilehash: b40ed11747e057d620a9a45dd1361081f38acec8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260506"
---
# <a name="-operator-visual-basic"></a>Оператор ''>>'' (Visual Basic)
Выполняет арифметическое смещение вправо для битового шаблона.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = pattern >> amount  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Целое числовое значение. Результат сдвига битового шаблона. Тип данных является таким же, как `pattern`.  
  
 `pattern`  
 Обязательный. Целое числовое выражение. Битовый шаблон должны сдвигаться. Тип данных должен быть целочисленный тип (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, или `ULong`).  
  
 `amount`  
 Обязательный. Числовое выражение. Количество битов для сдвига битового шаблона. Тип данных должен быть `Integer` или расширяющего преобразования к `Integer`.  
  
## <a name="remarks"></a>Примечания  
 Арифметические сдвиги не являются циклическими, это означает, что биты, сдвигаемые результата, не подставляются на другом конце. В арифметического сдвига вправо биты, сдвигаемые дальше крайней правой позиции отбрасываются, а бит крайнего левого (знак) передается в позиции битов, освобожденные слева. Это означает, что если `pattern` имеет отрицательное значение, освобождаемые устанавливается один; в противном случае они равны нулю.  
  
 Обратите внимание, что типы данных `Byte`, `UShort`, `UInteger`, и `ULong` являются числа без знака, поэтому не знаковый бит для распространения. Если `pattern` имеет любой без знака типа, освобождаемые всегда присваивается нулевое значение.  
  
 Чтобы предотвратить сдвиг на количество битов, чем результат, Visual Basic маскирует значение `amount` с маской размер, соответствующий тип данных `pattern`. Двоичное AND этих значений используется для сдвига. Далее приведены маски размера.  
  
|Тип данных `pattern`|Размер маски (десятичное)|Размер маски (шестнадцатеричный)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|&AMP; H00000007|  
|`Short`, `UShort`|15|&AMP; H0000000F|  
|`Integer`, `UInteger`|31|&AMP; H0000001F|  
|`Long`, `ULong`|63|&AMP; H0000003F|  
  
 Если `amount` равно нулю, значение `result` идентично значению `pattern`. Если `amount` имеет отрицательное значение, он берется значение без знака и маскируется соответствующий размер маски.  
  
 Арифметические сдвиги никогда не создают исключения переполнения.  
  
## <a name="overloading"></a>Перегрузка  
 `>>` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `>>` оператор для выполнения арифметических при сдвиге вправо целых значений. Результат всегда имеет тот же тип данных, выражения был перемещен.  
  
 [!code-vb[VbVbalrOperators#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_1.vb)]  
  
 Далее приведены результаты в предыдущем примере.  
  
-   `result1` является 2560 (0000 1010 0000 0000).  
  
-   `result2` равно 160 (0000 0000 1010 0000).  
  
-   `result3` -2 (0000 0000 0000 0010).  
  
-   `result4` — 640 (0000 0010 1000 0000).  
  
-   `result5` значение 0 (сдвигаются 15 разрядов справа).  
  
 Величина сдвига для `result4` вычисляется как 18 и 15, что соответствует 2.  
  
 В следующем примере показано арифметические сдвиги на отрицательное значение.  
  
 [!code-vb[VbVbalrOperators#55](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_2.vb)]  
  
 Далее приведены результаты в предыдущем примере.  
  
-   `negresult1` — -512 (1111 1110 0000 0000).  
  
-   `negresult2` -1 (распространяется знаковым битом).  
  
## <a name="see-also"></a>См. также
- [Операторы сдвига битов](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Оператор >>=](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
