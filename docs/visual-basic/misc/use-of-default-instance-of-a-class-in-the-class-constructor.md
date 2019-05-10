---
title: Использование экземпляра класса по умолчанию в конструкторе класса может привести к бесконечному рекурсивному вызову
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: 1cad1e3cf3943e945d519aee061a877c91684b4a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623471"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a>Использование экземпляра класса по умолчанию в конструкторе класса может привести к бесконечному рекурсивному вызову
В конструкторе класса использован экземпляр класса по умолчанию. Это может привести к бесконечному рекурсивному вызову — бесконечному циклу.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Удалите из конструктора класса экземпляр по умолчанию.  
  
## <a name="see-also"></a>См. также

- [Конструкторы](~/docs/visual-basic/programming-guide/concepts/object-oriented-programming.md#constructors)
