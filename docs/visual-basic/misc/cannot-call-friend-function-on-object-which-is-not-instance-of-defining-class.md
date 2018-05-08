---
title: Невозможно вызвать дружественную функцию для объекта, не являющегося экземпляром определяющего класса.
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: a655207110d512805490b693e413b1d22b0367ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a>Невозможно вызвать дружественную функцию для объекта, не являющегося экземпляром определяющего класса.
Предпринята попытка либо вызова процедуры `Friend` класса, либо получения доступа к дружественному ( `Friend` ) свойству или методу между процессами или между потоками. Процедура `Friend` может вызываться из модуля вне класса, однако она является частью проекта, в котором определен класс.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Убедитесь, что вызов процедуры или доступ к процедуре выполняется из модуля, являющегося частью проекта, в котором определен класс.  
  
## <a name="see-also"></a>См. также  
 [Friend](../../visual-basic/language-reference/modifiers/friend.md)
