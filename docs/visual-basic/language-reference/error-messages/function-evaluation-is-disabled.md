---
title: Вычисление функции отключено, поскольку истекло время, выделенное на вычисление предыдущей функции
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: bc4d05e52434cf62fa90671d29b407c83114b5d2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59315781"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a>Вычисление функции отключено, поскольку истекло время, выделенное на вычисление предыдущей функции
Вычисление функции отключено, так как истекло время ожидания вычисление предыдущей функции. Чтобы снова включить вычисление функции, еще один шаг или перезапустите отладку.  
  
 В отладчике Visual Studio выражение задает вызов процедуры, но другое вычисление обнаружил превышение времени ожидания.  
  
 Среди возможных причин вызов процедуры истечения времени ожидания бесконечного цикла или *бесконечный цикл*. Дополнительные сведения см. в разделе [для... Следующий оператор](../../../visual-basic/language-reference/statements/for-next-statement.md).  
  
 Является особым случаем бесконечного цикла *рекурсии*. Дополнительные сведения см. в разделе [рекурсивные процедуры](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).  
  
 **Идентификатор ошибки:** BC30957  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. По возможности определите, какой параметр имел вычисление предыдущей функции и что вызвало его истечения времени ожидания. В противном случае эта ошибка может возникнуть еще раз.  
  
2. Опять же, завести отладчик или завершите и перезапустите отладку.  
  
## <a name="see-also"></a>См. также

- [Отладка в Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)
- [Навигация по коду с помощью отладчика](/visualstudio/debugger/navigating-through-code-with-the-debugger)
