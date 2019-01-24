---
title: Использование экземпляра класса по умолчанию в конструкторе класса может привести к бесконечному рекурсивному вызову
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: b4cae7802019cba569cf15517b1e948266a576f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631442"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a>Использование экземпляра класса по умолчанию в конструкторе класса может привести к бесконечному рекурсивному вызову
В конструкторе класса использован экземпляр класса по умолчанию. Это может привести к бесконечному рекурсивному вызову — бесконечному циклу.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите из конструктора класса экземпляр по умолчанию.  
  
## <a name="see-also"></a>См. также
- [Конструкторы](~/docs/visual-basic/programming-guide/concepts/object-oriented-programming.md#constructors)
