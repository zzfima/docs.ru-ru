---
title: Вычисление функции отключено, поскольку истекло время, выделенное на вычисление предыдущей функции
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 05067e730486b443b7a508adb499f34c060d5093
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a>Вычисление функции отключено, поскольку истекло время, выделенное на вычисление предыдущей функции
Вычисление функции отключено, поскольку истекло время ожидания вычисление предыдущей функции. Для повторного выполнения функции сделайте еще один шаг или перезапустите отладку.  
  
 В отладчике Visual Studio выражение задает вызов процедуры, но другое вычисление превышено время ожидания.  
  
 Среди возможных причин время ожидания при вызове процедурой бесконечный цикл или *бесконечный цикл*. Дополнительные сведения см. в разделе [для... Следующий оператор](../../../visual-basic/language-reference/statements/for-next-statement.md).  
  
 Является особым случаем бесконечного цикла *рекурсии*. Дополнительные сведения см. в разделе [рекурсивные процедуры](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).  
  
 **Идентификатор ошибки:** BC30957  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  По возможности определите было вычисление предыдущей функции и причину истечения времени ожидания. В противном случае эта ошибка может возникнуть еще раз.  
  
2.  Отладчик сделайте еще один шаг, или завершите и перезапустите отладку.  
  
## <a name="see-also"></a>См. также  
 [Отладка в Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)  
 [Навигация по коду с помощью отладчика](/visualstudio/debugger/navigating-through-code-with-the-debugger)
