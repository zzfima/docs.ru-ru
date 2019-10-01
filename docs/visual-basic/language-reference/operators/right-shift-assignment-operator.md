---
title: '>>Оператор = (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
ms.openlocfilehash: 08d4e251a96ca387a709319e752351db6825d9e8
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701347"
---
# <a name="-operator-visual-basic"></a>Оператор > > = (Visual Basic)
Выполняет арифметическое смещение вправо для значения переменной или свойства и присваивает результат переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Обязательный. Переменная или свойство целочисленного типа (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` или `ULong`).  
  
 `amount`  
 Обязательный. Числовое выражение типа данных, которое расширяется до `Integer`.  
  
## <a name="remarks"></a>Примечания  
 Элемент в левой части оператора `>>=` может быть простой скалярной переменной, свойством или элементом массива. Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Оператор `>>=` сначала выполняет арифметический сдвиг значения переменной или свойства вправо. Затем оператор присваивает результат этой операции с переменной или свойством.  
  
 Арифметические сдвиги не являются циклическими, то есть биты, сдвинутые за пределы результата, не переносятся на другой конец. При арифметическом сдвиге вправо биты, сдвинутые за пределы крайней правой позиции, отбрасываются, а крайний левый бит передается в позиции, освобожденные слева. Это означает, что если `variableorproperty` имеет отрицательное значение, освобождаемые позиции будут установлены на единицу. Если `variableorproperty` является положительным или если его тип данных не является типом без знака, освобождаемые позиции устанавливаются в ноль.  
  
## <a name="overloading"></a>Перегрузка  
 [Оператор > >](../../../visual-basic/language-reference/operators/right-shift-operator.md) может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Перегрузка оператора `>>` влияет на поведение оператора `>>=`. Если в коде используется `>>=` для класса или структуры, которая перегружает `>>`, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `>>=` используется для сдвига битового шаблона переменной `Integer` вправо на указанное значение и присваивает результат переменной.  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>См. также

- [Оператор >>](../../../visual-basic/language-reference/operators/right-shift-operator.md)
- [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Операторы сдвига битов](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
