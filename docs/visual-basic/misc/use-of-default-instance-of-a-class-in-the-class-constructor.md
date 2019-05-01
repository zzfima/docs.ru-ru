---
title: Использование экземпляра класса по умолчанию в конструкторе класса может привести к бесконечному рекурсивному вызову
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: 14c498bf3067415f8de2afaeaaa57cf3f28ae857
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022458"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a>Использование экземпляра класса по умолчанию в конструкторе класса может привести к бесконечному рекурсивному вызову
В конструкторе класса использован экземпляр класса по умолчанию. Это может привести к бесконечному рекурсивному вызову — бесконечному циклу.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Удалите из конструктора класса экземпляр по умолчанию.  
  
## <a name="see-also"></a>См. также

- [Конструкторы](~/docs/visual-basic/programming-guide/concepts/object-oriented-programming.md#constructors)
