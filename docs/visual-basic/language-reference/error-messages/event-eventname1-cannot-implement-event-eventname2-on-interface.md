---
title: Событие <eventname1> не может реализовать событие <eventname2> в интерфейсе <interface>, так как их делегируемые типы <delegate1> и <delegate2> не совпадают
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: 9581168fa86f8f0715e004b60c2eb2a813cd38ab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58840527"
---
# <a name="event-eventname1-cannot-implement-event-eventname2-on-interface-interface-because-their-delegate-types-delegate1-and-delegate2-do-not-match"></a>Событие "\<имя_события1 >" не удается реализовать событие "\<имя_события2 >" в интерфейсе "\<интерфейс >" так как их делегируемые типы\<delegate1 > "и"\<delegate2 > "не совпадают
Visual Basic не может реализовать событие, поскольку тип делегата события не соответствует типу делегата события в интерфейсе. Эта ошибка может возникнуть при определении нескольких событий в интерфейсе и последующей попытке их совместной реализации с использованием одного события. Событие может реализовывать два или более событий, только если все они объявлены с помощью синтаксиса `As` и указывают один и тот же тип делегата.  
  
 **Идентификатор ошибки:** BC31423  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Реализуйте события по отдельности.  
  
     —или—  
  
-   Определите события в интерфейсе, используя `As` синтаксис и укажите тот же тип делегата.  
  
## <a name="see-also"></a>См. также

- [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [События](../../../visual-basic/programming-guide/language-features/events/index.md)
