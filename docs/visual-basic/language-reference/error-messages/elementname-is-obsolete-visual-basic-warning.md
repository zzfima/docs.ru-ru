---
title: '&#39;&lt;ElementName&gt; &#39; устарел (предупреждение Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vbc40008
- bc40008
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
ms.openlocfilehash: 4dc2d0b8eace9bc411a344b4f2c4c79f7e09ac22
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="39ltelementnamegt39-is-obsolete-visual-basic-warning"></a>&#39;&lt;ElementName&gt; &#39; устарел (предупреждение Visual Basic)
Оператор пытается получить доступ к элементу программирования, который был помечен атрибутом <xref:System.ObsoleteAttribute> и директивой, предписывающей расценивать это как предупреждение.  
  
 Вы можете пометить любой программный элемент как неиспользуемый, применив к нему <xref:System.ObsoleteAttribute> . Если вы это сделаете, вы можете задать для свойства <xref:System.ObsoleteAttribute.IsError%2A> атрибута значение `True` или `False`. Если задать значение `True`, компилятор будет рассматривать попытку использовать элемент как ошибку. Если задать значение `False`или оставить значение по умолчанию `False`, то при попытке использовать элемент компилятор выдаст предупреждение.  
  
 По умолчанию это сообщение считается предупреждением, так как свойство <xref:System.ObsoleteAttribute.IsError%2A> <xref:System.ObsoleteAttribute> имеет значение `False`. Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40008  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Убедитесь, что в ссылке исходного кода имя элемента указано правильно.  
  
## <a name="see-also"></a>См. также  
 [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)
