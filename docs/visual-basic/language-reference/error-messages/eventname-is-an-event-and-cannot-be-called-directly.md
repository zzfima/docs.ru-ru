---
title: <eventname> является событием, поэтому его прямой вызов невозможен
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: bf900566bdb4ecf8d8961a12b5dd67ba426caf27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803328"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a>"\<имя_события >" является событием и не может вызываться напрямую
"<`eventname`>" является событием и поэтому не может вызываться напрямую. Используйте `RaiseEvent` инструкцию, чтобы вызвать событие.  
  
 При вызове процедуры указывается событие для имени процедуры. Обработчик событий — это процедура, но само событие является сигнальным устройством, которое должно быть создано и обработано.  
  
 **Идентификатор ошибки:** BC32022  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Используйте `RaiseEvent` инструкцию, чтобы оповестить о событии и вызвать одну или несколько процедур, которые его обрабатывают.  
  
## <a name="see-also"></a>См. также

- [Оператор RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
