---
title: Неявное преобразование из &#39; &lt;Имя_типа1&gt; &#39; для &#39; &lt;имя_типа2&gt; &#39; в копировании значения параметра &#39;ByRef&#39; параметр &#39; &lt; имя_параметра&gt; &#39; обратно в соответствующий аргумент.
ms.date: 07/20/2015
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
ms.openlocfilehash: 9f05a5fbcbef828b4ffa920d8cade475cedb64d5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537247"
---
# <a name="implicit-conversion-from-39lttypename1gt39-to-39lttypename2gt39-in-copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument"></a>Неявное преобразование из &#39; &lt;Имя_типа1&gt; &#39; для &#39; &lt;имя_типа2&gt; &#39; в копировании значения параметра &#39;ByRef&#39; параметр &#39; &lt; имя_параметра&gt; &#39; обратно в соответствующий аргумент.
Процедура вызывается с [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) аргумента отличается от соответствующего параметра типа.  
  
 Если при передаче аргумента `ByRef`, Visual Basic иногда копирует его значение в локальную переменную в процедуре вместо передачи ссылки. В этом случае когда процедура возвращает результат, Visual Basic должен скопировать значение локальной переменной обратно в аргументе в вызывающем коде.  
  
 Если значение аргумента `ByRef` копируется в процедуру, а аргумент и параметр имеют один и тот же тип, то преобразование не требуется. Но если типы различны, Visual Basic необходимо преобразовать в обоих направлениях. Поскольку вы не можете использовать `CType` или любые другие преобразования ключевые слова на аргумента процедуры или параметра, такое преобразование всегда является неявным.  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC41999  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   По возможности используйте аргумент вызова того же типа, что и параметр процедуры, поэтому Visual Basic не нужно выполнять никаких преобразований.  
  
-   Если необходимо вызвать процедуру с аргументом, тип которого отличается от типа параметра, но не требуется возвращать значение в аргумент вызова, то определите параметр как [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) , а не `ByRef`.  
  
## <a name="see-also"></a>См. также
- [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Параметры и аргументы процедуры](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Передача аргументов по значению и по ссылке](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
