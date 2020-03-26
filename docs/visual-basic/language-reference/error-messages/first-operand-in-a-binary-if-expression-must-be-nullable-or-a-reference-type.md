---
title: Первый операнд в двоичном выражении If должен поддерживать значение NULL или быть ссылочного типа
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: 4b520949cb59b63ea39441632dc5e2c6d000d711
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249530"
---
# <a name="first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a>Первый операнд в двоичном выражении If должен поддерживать значение NULL или быть ссылочного типа
Выражение `If` может занять два или три аргумента. При отправке только двух аргументов первым аргументом должен быть тип ссылки или необыдаенный тип значения. Если первый аргумент оценивается `Nothing`ни к чему, кроме, его значение возвращается. Если первый аргумент `Nothing`оценивается, второй аргумент оценивается и возвращается.  
  
 Например, следующий код `If` содержит два выражения: одно с тремя аргументами и одно с двумя аргументами. Выражения вычисляют и возвращают одно и то же значение.  
  
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
  
- Если вы не можете изменить код таким образом, чтобы первый аргумент был необоснованной типом `If...Then...Else` значения или типом ссылки, рассмотрите возможность преобразования в выражение из трех аргументов `If` или в заявление.  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a>См. также

- [Оператор If](../../../visual-basic/language-reference/operators/if-operator.md)
- [Оператор If…Then…Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Типы значений, допускающие значение NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
