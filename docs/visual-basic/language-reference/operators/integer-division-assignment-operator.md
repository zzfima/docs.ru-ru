---
title: Оператор \=
ms.date: 07/20/2015
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
ms.openlocfilehash: 600acf9b41b63358da245fe602595fee4093b15b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330945"
---
# <a name="-operator"></a>Оператор \\=
Делит значение переменной или свойства на значение выражения и присваивает целочисленный результат переменной или свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
variableorproperty \= expression  
```  
  
## <a name="parts"></a>Части  
 `variableorproperty`  
 Обязательно. Любая числовая переменная или свойство.  
  
 `expression`  
 Обязательно. Произвольное числовое выражение.  
  
## <a name="remarks"></a>Заметки  
 Элемент в левой части оператора `\=` может быть простой скалярной переменной, свойством или элементом массива. Переменная или свойство не может быть [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Оператор `\=` делит значение переменной или свойства слева на значение справа и присваивает целочисленный результат переменной или свойству, расположенному слева  
  
 Дополнительные сведения о целочисленном делении см. в разделе [оператор \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).  
  
## <a name="overloading"></a>Перегрузка  
 Оператор `\` может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Перегрузка оператора `\` влияет на поведение оператора `\=`. Если в коде используется `\=` в классе или структуре, которая перегружает `\`, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `\=` используется для деления одной `Integer` переменной на вторую и присваивания целочисленного результата первой переменной.  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>См. также

- [Оператор \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [Оператор/= (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [Операторы присваивания](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
