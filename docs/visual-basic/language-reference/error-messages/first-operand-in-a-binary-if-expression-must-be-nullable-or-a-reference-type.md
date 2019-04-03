---
title: Первый операнд в двоичном выражении If должен поддерживать значение NULL или быть ссылочного типа
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: 32ff0adca9d35e6b5439ae06be85414924dac2e6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838629"
---
# <a name="first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a>Первый операнд в двоичном выражении If должен поддерживать значение NULL или быть ссылочного типа
`If` Выражение может принимать два или три аргумента. При отправке только два аргумента, первый аргумент должен быть ссылочным типом или типом, допускающий значение NULL. Если первый аргумент принимает на любое другое, отличное от `Nothing`, возвращается его значение. Если первый аргумент принимает значение `Nothing`, второй аргумент вычисляется и возвращается.  
  
 Например, следующий код содержит два `If` выражения: с тремя аргументами и с двумя аргументами. Выражения вычисления и возвращают одинаковое значение.  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 Следующие выражения вызывают эту ошибку:  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 **Идентификатор ошибки:** BC33107  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если не удается изменить код таким образом, первый аргумент является ссылочным типом или ссылочным типом, следует преобразовать с тремя аргументами `If` выражения, или к `If...Then...Else` инструкции.  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a>См. также

- [Оператор If](../../../visual-basic/language-reference/operators/if-operator.md)
- [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Типы значений, допускающие значение NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
