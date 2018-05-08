---
title: Использование экземпляра класса по умолчанию в конструкторе класса может привести к бесконечному рекурсивному вызову
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: cf5d3e16c43920a90b69c815f91601c6d33c845d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a>Использование экземпляра класса по умолчанию в конструкторе класса может привести к бесконечному рекурсивному вызову
В конструкторе класса использован экземпляр класса по умолчанию. Это может привести к бесконечному рекурсивному вызову — бесконечному циклу.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите из конструктора класса экземпляр по умолчанию.  
  
## <a name="see-also"></a>См. также  
 [Конструкторы](~/docs/visual-basic/programming-guide/concepts/object-oriented-programming.md#constructors)
