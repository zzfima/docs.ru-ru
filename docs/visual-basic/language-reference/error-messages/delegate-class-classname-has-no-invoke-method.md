---
title: "В делегируемом классе &lt;имяКласса&gt; отсутствует метод Invoke, поэтому выражение этого типа не может быть вызвано посредством метода | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30220"
  - "bc30220"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30220"
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# В делегируемом классе &lt;имяКласса&gt; отсутствует метод Invoke, поэтому выражение этого типа не может быть вызвано посредством метода
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Вызов метода `Invoke` с помощью делегата завершился с ошибкой, т.к. метод `Invoke` не реализован в классе делегата.  
  
 **Идентификатор ошибки:** BC30220  
  
### Чтобы исправить эту ошибку  
  
1.  Убедитесь, что экземпляр класса делегата был создан с помощью оператора `Dim`, и что процедура была назначена экземпляру делегата с помощью оператора `AddressOf`.  
  
2.  Найдите код, который реализует класс делегата, и убедитесь, что он реализует процедуру `Invoke`.  
  
## См. также  
 [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)