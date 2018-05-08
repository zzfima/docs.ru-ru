---
title: Класс делегата &#39; &lt;classname&gt; &#39; не содержит метода Invoke, поэтому выражение этого типа не может быть результатом вызова метода
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: cc1abba46224772e733780800dd104dfc7ebe9ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>Класс делегата &#39; &lt;classname&gt; &#39; не содержит метода Invoke, поэтому выражение этого типа не может быть результатом вызова метода
Вызов `Invoke` в делегате не выполнено, поскольку `Invoke` не реализован в классе делегата.  
  
 **Идентификатор ошибки:** BC30220  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что экземпляр класса делегата был создан с `Dim` инструкции и что процедура была назначена экземпляру делегата с `AddressOf` оператор.  
  
2.  Найдите код, который реализует класс делегата и убедитесь, что он реализует `Invoke` процедуры.  
  
## <a name="see-also"></a>См. также  
 [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
