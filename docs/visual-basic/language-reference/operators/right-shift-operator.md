---
title: '>> Оператор (Visual Basic)'
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
ms.openlocfilehash: 337d651e831dc2ab132056f6e9a1f2b5300bf7f8
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701328"
---
# <a name="-operator-visual-basic"></a>Оператор > > (Visual Basic)
Выполняет арифметический сдвиг битового шаблона вправо.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
result = pattern >> amount  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Целое числовое значение. Результат сдвига битового шаблона. Тип данных такой же, как `pattern`и у.  
  
 `pattern`  
 Обязательный. Целое числовое выражение. Битовый шаблон для сдвига. `SByte`Тип данных должен быть целочисленным типом ( `Byte` `Short`,,, `UShort` `UInteger` `Integer`,,, `Long`или `ULong`).  
  
 `amount`  
 Обязательный. Числовое выражение. Число битов для сдвига битового шаблона. Тип данных должен быть `Integer` или расширяться на. `Integer`  
  
## <a name="remarks"></a>Примечания  
 Арифметические сдвиги не являются циклическими, то есть биты, сдвинутые за пределы результата, не переносятся на другой конец. При арифметическом сдвиге вправо биты, сдвинутые за пределы крайней правой позиции, отбрасываются, а самый левый бит (знак) распространяется на биты, освобожденные слева. Это означает, что если `pattern` имеет отрицательное значение, освобождаемые позиции устанавливаются в единицу. в противном случае устанавливается нулевое значение.  
  
 Обратите внимание, что типы данных `Byte`, `UShort`, `UInteger` и `ULong` не подписаны, поэтому для распространения нет бита знака. Если `pattern` относится к любому типу без знака, освобождаемые позиции всегда устанавливаются в ноль.  
  
 Чтобы предотвратить сдвиг на большее количество битов, чем может вместить результат, Visual Basic маскирует значение `amount` с маской размера, соответствующей типу данных `pattern`. Двоичные значения и этих значений используются для величины сдвига. Ниже приведены маски размера.  
  
|Тип данных `pattern`|Маска размера (десятичная)|Маска размера (шестнадцатеричная)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|& H00000007|  
|`Short`, `UShort`|15|& H0000000F|  
|`Integer`, `UInteger`|31|& H0000001F|  
|`Long`, `ULong`|63|& H0000003F|  
  
 Если `amount` равно нулю, значение `result` идентично значению `pattern`. Если `amount` является отрицательным, он принимается как значение без знака и маскируется с соответствующей маской размера.  
  
 Арифметические сдвиги никогда не создают исключений переполнения.  
  
## <a name="overloading"></a>Перегрузка  
 Оператор `>>` можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `>>` используется для выполнения арифметических сдвигов в целочисленных значениях вправо. Результат всегда имеет тот же тип данных, что и выражение, для которого выполняется сдвиг.  
  
 [!code-vb[VbVbalrOperators#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#14)]  
  
 Ниже приведены результаты предыдущего примера.  
  
- `result1` — 2560 (0000 1010 0000 0000).  
  
- `result2` — 160 (0000 0000 1010 0000).  
  
- `result3` — 2 (0000 0000 0000 0010).  
  
- `result4` — 640 (0000 0010 1000 0000).  
  
- `result5` равно 0 (смещено 15 позиций вправо).  
  
 Сумма сдвига для `result4` вычисляется как 18 и 15, что равно 2.  
  
 В следующем примере показаны арифметические сдвиги для отрицательного значения.  
  
 [!code-vb[VbVbalrOperators#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#55)]  
  
 Ниже приведены результаты предыдущего примера.  
  
- `negresult1` — 512 (1111 1110 0000 0000).  
  
- `negresult2` равно-1 (бит знака распространяется).  
  
## <a name="see-also"></a>См. также

- [Операторы сдвига битов](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Оператор >>=](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
