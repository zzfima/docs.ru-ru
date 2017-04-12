---
title: "&quot;&lt;elementname&gt;&quot; является устаревшим (предупреждение Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40008
- bc40008
dev_langs:
- VB
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: ccec3b2659502c84dd4db9c9c4d796362958030b
ms.lasthandoff: 03/13/2017

---
# <a name="39ltelementnamegt39-is-obsolete-visual-basic-warning"></a>"&lt;elementname&gt;" является устаревшим (предупреждение Visual Basic)
Оператор пытается получить доступ к элементу программирования, который был помечен с <xref:System.ObsoleteAttribute>атрибут и следует рассматривать ее как предупреждение.</xref:System.ObsoleteAttribute>  
  
 Можно пометить любой элемент программирования как более не используется путем применения <xref:System.ObsoleteAttribute>к его.</xref:System.ObsoleteAttribute> После этого можно задать атрибут <xref:System.ObsoleteAttribute.IsError%2A>значение `True` или `False`.</xref:System.ObsoleteAttribute.IsError%2A> Если задать значение `True`, компилятор будет рассматривать попытку использовать элемент как ошибку. Если задать значение `False`или оставить значение по умолчанию `False`, то при попытке использовать элемент компилятор выдаст предупреждение.  
  
 По умолчанию это сообщение является предупреждением, поскольку <xref:System.ObsoleteAttribute.IsError%2A>свойство <xref:System.ObsoleteAttribute>— `False`.</xref:System.ObsoleteAttribute> </xref:System.ObsoleteAttribute.IsError%2A> Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40008  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Убедитесь, что в ссылке исходного кода имя элемента указано правильно.  
  
## <a name="see-also"></a>См. также  
 [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)

