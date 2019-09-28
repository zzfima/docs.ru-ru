---
title: Оператор ^= (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: 382e0b27c2dbf27e5acccf29f1b8d2b002cb6664
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592226"
---
# <a name="-operator-visual-basic"></a>Оператор ^= (Visual Basic)
Возвращает значение переменной или свойства в степень выражения и присваивает результат переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Обязательный. Любая числовая переменная или свойство.  
  
 `expression`  
 Обязательный. Произвольное числовое выражение.  
  
## <a name="remarks"></a>Примечания  
 Элемент в левой части оператора `^=` может быть простой скалярной переменной, свойством или элементом массива. Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Оператор `^=` сначала вызывает значение переменной или свойства (в левой части оператора) на степень значения выражения (в правой части оператора)...;. Затем оператор присваивает результат этой операции с переменной или свойством.  
  
 Visual Basic всегда выполняет возведение в степень в [типе данных Double](../../../visual-basic/language-reference/data-types/double-data-type.md). Операнды любого другого типа преобразуются в `Double`, а результат всегда `Double`.  
  
 Значение `expression` может быть дробным, отрицательным или обоими.  
  
## <a name="overloading"></a>Перегрузка  
 [Оператор ^](../../../visual-basic/language-reference/operators/exponentiation-operator.md) может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Перегрузка оператора `^` влияет на поведение оператора `^=`. Если в коде используется `^=` для класса или структуры, которая перегружает `^`, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `^=` используется для возведения значения одной переменной `Integer` в степень второй переменной и присваивания результата первой переменной.  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>См. также

- [Оператор ^](../../../visual-basic/language-reference/operators/exponentiation-operator.md)
- [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
