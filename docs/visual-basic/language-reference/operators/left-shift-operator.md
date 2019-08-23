---
title: Оператор < < (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: d6b186ad519bcd7cf82cce12523f2d75e09317cc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966887"
---
# <a name="-operator-visual-basic"></a>\<\<Оператор (Visual Basic)
Выполняет арифметический сдвиг битового шаблона влево.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = pattern << amount  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Целое числовое значение. Результат сдвига битового шаблона. Тип данных такой же, как `pattern`и у.  
  
 `pattern`  
 Обязательный. Целое числовое выражение. Битовый шаблон для сдвига. `SByte`Тип данных должен быть целочисленным типом ( `Byte` `Short`,,, `UShort` `UInteger` `Integer`,,, `Long`или `ULong`).  
  
 `amount`  
 Обязательный. Числовое выражение. Число битов для сдвига битового шаблона. Тип данных должен быть `Integer` или расширяться на. `Integer`  
  
## <a name="remarks"></a>Примечания  
 Арифметические сдвиги не являются циклическими, то есть биты, сдвинутые за пределы результата, не переносятся на другой конец. При выполнении арифметического сдвига влево биты, сдвинутые за пределы диапазона результирующего типа данных, отбрасываются, а позиции битов, освобожденные справа, устанавливаются в ноль.  
  
 Чтобы предотвратить сдвиг на больше бит, чем может вместить результат, Visual Basic маскирует значение `amount` с маской размера, соответствующей `pattern`типу данных. Двоичные значения и этих значений используются для величины сдвига. Ниже приведены маски размера.  
  
|Тип данных`pattern`|Маска размера (десятичная)|Маска размера (шестнадцатеричная)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|& H00000007|  
|`Short`, `UShort`|15|& H0000000F|  
|`Integer`, `UInteger`|31|& H0000001F|  
|`Long`, `ULong`|63|& H0000003F|  
  
 Если `amount` равен нулю, `result` значение `pattern`идентично значению. Если `amount` имеет отрицательное значение, оно принимается в качестве значения без знака и маскируется с соответствующей маской размера.  
  
 Арифметические сдвиги никогда не создают исключений переполнения.  
  
> [!NOTE]
> Оператор можно перегрузить, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. `<<` Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере `<<` оператор используется для выполнения арифметических сдвигов влево по целочисленным значениям. Результат всегда имеет тот же тип данных, что и выражение, для которого выполняется сдвиг.  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 Результаты предыдущего примера выглядят следующим образом:  
  
- `result1`— 192 (0000 0000 1100 0000).  
  
- `result2`— 3072 (0000 1100 0000 0000).  
  
- `result3`— 32768 (1000 0000 0000 0000).  
  
- `result4`— 384 (0000 0001 1000 0000).  
  
- `result5`равно 0 (смещено 15 позиций влево).  
  
 Сумма сдвига для `result4` вычисляется как 17 и 15, что равно 1.  
  
## <a name="see-also"></a>См. также

- [Операторы сдвига битов](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Оператор <<=](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
