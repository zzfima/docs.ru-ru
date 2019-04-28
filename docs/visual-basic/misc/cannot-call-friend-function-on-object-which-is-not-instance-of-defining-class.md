---
title: Невозможно вызвать дружественную функцию для объекта, не являющегося экземпляром определяющего класса.
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: c65bbb5028cf042b702bb2b8336d40512c980790
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61912695"
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a>Невозможно вызвать дружественную функцию для объекта, не являющегося экземпляром определяющего класса.
Предпринята попытка либо вызова процедуры `Friend` класса, либо получения доступа к дружественному ( `Friend` ) свойству или методу между процессами или между потоками. Процедура `Friend` может вызываться из модуля вне класса, однако она является частью проекта, в котором определен класс.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Убедитесь, что вызов процедуры или доступ к процедуре выполняется из модуля, являющегося частью проекта, в котором определен класс.  
  
## <a name="see-also"></a>См. также

- [Friend](../../visual-basic/language-reference/modifiers/friend.md)
