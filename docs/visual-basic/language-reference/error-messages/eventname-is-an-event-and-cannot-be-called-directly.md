---
title: '&#39;&lt;EventName&gt; &#39; является событием и не может вызываться напрямую'
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 4d8a7d716d2b7c52d1d027a1e7959d981bb0857e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a>&#39;&lt;EventName&gt; &#39; является событием и не может вызываться напрямую
"<`eventname`>" является событием и поэтому не может вызываться напрямую. Используйте `RaiseEvent` оператор для вызова события.  
  
 При вызове процедуры указывается событие имени процедуры. Обработчик событий — это процедура, но само событие является сигнальным устройством, которое должно быть создано и обработано.  
  
 **Идентификатор ошибки:** BC32022  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Используйте `RaiseEvent` инструкции для генерации события и вызова процедуры или процедуры его обработки.  
  
## <a name="see-also"></a>См. также  
 [Оператор RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
