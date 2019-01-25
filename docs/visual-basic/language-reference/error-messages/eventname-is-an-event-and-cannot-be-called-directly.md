---
title: '&#39;&lt;EventName&gt; &#39; — это событие и не может вызываться напрямую'
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 3efd8c18497ce288e16659db4ca4693d5a3e6acc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582006"
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a>&#39;&lt;EventName&gt; &#39; — это событие и не может вызываться напрямую
"<`eventname`>" является событием и поэтому не может вызываться напрямую. Используйте `RaiseEvent` инструкцию, чтобы вызвать событие.  
  
 При вызове процедуры указывается событие для имени процедуры. Обработчик событий — это процедура, но само событие является сигнальным устройством, которое должно быть создано и обработано.  
  
 **Идентификатор ошибки:** BC32022  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Используйте `RaiseEvent` инструкцию, чтобы оповестить о событии и вызвать одну или несколько процедур, которые его обрабатывают.  
  
## <a name="see-also"></a>См. также
- [Оператор RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
