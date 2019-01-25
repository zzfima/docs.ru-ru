---
title: Класс делегата &#39; &lt;classname&gt; &#39; не содержит метода Invoke, поэтому выражение этого типа не может быть результатом вызова метода
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: d5421ea05968a221bbbf8f52a575550d1bca3cb2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54653168"
---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>Класс делегата &#39; &lt;classname&gt; &#39; не содержит метода Invoke, поэтому выражение этого типа не может быть результатом вызова метода
Вызов `Invoke` через делегат не выполнено, поскольку `Invoke` не реализован в классе делегата.  
  
 **Идентификатор ошибки:** BC30220  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что создания экземпляра класса делегата с `Dim` инструкции и что процедура была назначена экземпляру делегата с `AddressOf` оператор.  
  
2.  Найдите код, который реализует класс делегата и убедитесь, что он реализует `Invoke` процедуры.  
  
## <a name="see-also"></a>См. также
- [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
