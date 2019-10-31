---
title: Вычисление функции отключено, поскольку истекло время, выделенное на вычисление предыдущей функции
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: d004c89b742944622ce45e6a2be8d96116252745
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197566"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a>Вычисление функции отключено, поскольку истекло время, выделенное на вычисление предыдущей функции
Вычисление функции отключено, так как истекло время ожидания при вычислении предыдущей функции. Чтобы повторно включить вычисление функции, повторите шаг или перезапустите отладку.  
  
 В отладчике Visual Studio выражение указывает вызов процедуры, но время ожидания для другого вычисления истекло.  
  
 Возможные причины истечения времени ожидания вызова процедуры включают бесконечный цикл или *бесконечный цикл*. Дополнительные сведения см. в разделе [for... Следующий оператор](../../../visual-basic/language-reference/statements/for-next-statement.md).  
  
 Особый случай бесконечного цикла — *рекурсия*. Дополнительные сведения см. в разделе [Рекурсивные процедуры](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).  
  
 **Идентификатор ошибки:** BC30957  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. По возможности определите, что использовалось предыдущее вычисление функции и что привело к истечению времени ожидания. В противном случае эта ошибка может возникать снова.  
  
2. Либо пошаговый отладчик снова, либо завершите и перезапустите отладку.  
  
## <a name="see-also"></a>См. также

- [Отладка в Visual Studio](/visualstudio/debugger/debugger-feature-tour)
- [Навигация по коду с помощью отладчика](/visualstudio/debugger/navigating-through-code-with-the-debugger)
