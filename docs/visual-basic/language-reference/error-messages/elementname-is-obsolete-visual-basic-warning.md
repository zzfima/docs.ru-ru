---
title: <elementname> является устаревшим (Предупреждение Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbc40008
- bc40008
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
ms.openlocfilehash: c6d927ef6681838d8a77a0c6018eb6bbe30913e8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255866"
---
# <a name="elementname-is-obsolete-visual-basic-warning"></a>"\<elementname >" является устаревшим (предупреждение Visual Basic)
Оператор пытается получить доступ к элементу программирования, который был помечен атрибутом <xref:System.ObsoleteAttribute> и директивой, предписывающей расценивать это как предупреждение.  
  
 Вы можете пометить любой программный элемент как неиспользуемый, применив к нему <xref:System.ObsoleteAttribute> . Если вы это сделаете, вы можете задать для свойства <xref:System.ObsoleteAttribute.IsError%2A> атрибута значение `True` или `False`. Если задать значение `True`, компилятор будет рассматривать попытку использовать элемент как ошибку. Если задать значение `False`или оставить значение по умолчанию `False`, то при попытке использовать элемент компилятор выдаст предупреждение.  
  
 По умолчанию это сообщение считается предупреждением, так как свойство <xref:System.ObsoleteAttribute.IsError%2A> <xref:System.ObsoleteAttribute> имеет значение `False`. Дополнительные сведения о сокрытии предупреждений и обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40008  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Убедитесь, что в ссылке исходного кода имя элемента указано правильно.  
  
## <a name="see-also"></a>См. также
- [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)
