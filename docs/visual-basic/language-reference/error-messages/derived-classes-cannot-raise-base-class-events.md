---
title: Производные классы не могут вызывать события базового класса
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 70dde8b96980adfd618e38b9ce142cdec56a6b13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="derived-classes-cannot-raise-base-class-events"></a>Производные классы не могут вызывать события базового класса
Событие можно вызвать только из области объявления, в котором она объявлена. Таким образом класс не может вызвать событие из другого класса, хотя бы один из которого он является производным.  
  
 **Идентификатор ошибки:** BC30029  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Переместить `Event` инструкции или `RaiseEvent` инструкции так, чтобы они в том же классе.  
  
## <a name="see-also"></a>См. также  
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Оператор RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
