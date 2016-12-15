---
title: "&lt;имяЭлемента&gt; является устаревшим (Предупреждение Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc40008"
  - "bc40008"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40008"
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;имяЭлемента&gt; является устаревшим (Предупреждение Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор пытается получить доступ к элементу программирования, который был помечен с помощью атрибута <xref:System.ObsoleteAttribute>, это вызывает предупреждение.  
  
 С помощью атрибута <xref:System.ObsoleteAttribute> можно пометить любой элемент программирования как более не используемый.  После этого можно задать для свойства <xref:System.ObsoleteAttribute.IsError%2A> атрибута значение `True` или `False`.  Если задано значение `True`, компилятор рассматривает попытку использования элемента как ошибку.  Если задать значение `False` или оставить используемое по умолчанию значение `False`, то при попытке использовать элемент компилятор выдает предупреждение.  
  
 По умолчанию это сообщение является предупреждением, поскольку для свойства <xref:System.ObsoleteAttribute.IsError%2A> атрибута <xref:System.ObsoleteAttribute> задается значение `False`.  Дополнительные сведения о скрытии предупреждений или их обработке как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки**: BC40008  
  
### Чтобы исправить эту ошибку  
  
-   Убедитесь, что исходный код ссылается на допустимое имя элемента.  
  
## См. также  
 [Атрибуты](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)