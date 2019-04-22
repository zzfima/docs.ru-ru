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
ms.openlocfilehash: 1076ce62077391f2c88ebdd621d1dbd6fb40d647
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838967"
---
# <a name="-operator-visual-basic"></a>>> =-оператор (Visual Basic)
Выполняет арифметическое смещение вправо от значения переменной или свойства и присваивает результат переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Обязательный. Переменная или свойство целочисленного типа (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, или `ULong`).  
  
 `amount`  
 Обязательный. Числовое выражение типа данных, который расширяется до `Integer`.  
  
## <a name="remarks"></a>Примечания  
 Элемент, на левой стороне `>>=` оператор может быть простой скалярной переменной, свойства или элемента массива. Не может быть переменной или свойству [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 `>>=` Оператор сначала выполняет арифметическое смещение вправо от значения переменной или свойству. Затем оператор присваивает результат этой операции переменной или свойству.  
  
 Арифметические сдвиги не являются циклическими, это означает, что биты, сдвигаемые результата, не подставляются на другом конце. В арифметического сдвига вправо биты, сдвигаемые дальше крайней правой позиции отбрасываются, а первый бит распространяется в позиции битов, освобожденные слева. Это означает, что если `variableorproperty` имеет отрицательное значение, освобождаемые устанавливается один. Если `variableorproperty` положительно, или если его тип данных является тип без знака, освобождаемые присваивается нулевое значение.  
  
## <a name="overloading"></a>Перегрузка  
 [>> Оператор](../../../visual-basic/language-reference/operators/right-shift-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Перегрузка `>>` оператор влияет на поведение `>>=` оператор. Если код использует `>>=` для класса или структуры, перегружающей `>>`, убедитесь, что его переопределенное. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `>>=` оператор, чтобы сдвинуть битовый шаблон из `Integer` переменной вправо на заданную величину и назначает полученное значение переменной.  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>См. также

- [Оператор >>](../../../visual-basic/language-reference/operators/right-shift-operator.md)
- [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Операторы сдвига битов](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
