---
title: "Класс делегата&lt;classname&gt;&quot;имеет отсутствует метод Invoke, поэтому выражение этого типа не может быть результатом вызова метода | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30220
- bc30220
dev_langs:
- VB
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ddc5ef0f0b3e9baa58f17dafb727e250c0fba9fd
ms.lasthandoff: 03/13/2017

---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>Класс делегата&lt;classname&gt;"имеет отсутствует метод Invoke, поэтому выражение этого типа не может быть результатом вызова метода
Вызов `Invoke` через делегат не выполнено, поскольку `Invoke` не реализован в классе делегата.  
  
 **Идентификатор ошибки:** BC30220  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что экземпляр класса делегата был создан с помощью `Dim` инструкции и что процедура была назначена экземпляру делегата с `AddressOf` оператор.  
  
2.  Найдите код, который реализует класс делегата и убедитесь, что он реализует `Invoke` процедуры.  
  
## <a name="see-also"></a>См. также  
 [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
