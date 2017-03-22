---
title: "Вычисление функции отключено, поскольку истекло время ожидания вычисление предыдущей функции | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30957
- vbc30957
dev_langs:
- VB
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
caps.latest.revision: 7
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b861b5c6c151c5d3aeec2810c7f2a228f22fdf6e
ms.lasthandoff: 03/13/2017

---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a>Вычисление функции отключено, поскольку истекло время, выделенное на вычисление предыдущей функции
Вычисление функции отключено, поскольку истекло время ожидания вычисление предыдущей функции. Чтобы снова включить вычисление функции, еще один шаг или перезапустите отладку.  
  
 В отладчике Visual Studio выражение задает вызов процедуры, но другое вычисление истекло.  
  
 Среди возможных причин вызов процедуры тайм-аута бесконечный цикл или *бесконечный цикл*. Дополнительные сведения см. в разделе [для... Следующий оператор](../../../visual-basic/language-reference/statements/for-next-statement.md).  
  
 Является особым случаем бесконечного цикла *рекурсии*. Дополнительные сведения см. в разделе [рекурсивные процедуры](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).  
  
 **Идентификатор ошибки:** BC30957  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Если возможно определите, каким было вычисление предыдущей функции и причину превышения его времени ожидания. В противном случае эта ошибка может возникнуть повторно.  
  
2.  Шаг, отладчик или завершить и снова запустите отладку.  
  
## <a name="see-also"></a>См. также  
 [Отладка в Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio)   
 [Навигация по коду с помощью отладчика](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)
