---
title: Класс делегата &#39; &lt;classname&gt;&#39; не содержит метода Invoke, поэтому выражение этого типа не может быть результатом вызова метода
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 55d0e2442807e25737d90ac4b45a59b9d3e73037
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>Класс делегата &#39; &lt;classname&gt;&#39; не содержит метода Invoke, поэтому выражение этого типа не может быть результатом вызова метода
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
