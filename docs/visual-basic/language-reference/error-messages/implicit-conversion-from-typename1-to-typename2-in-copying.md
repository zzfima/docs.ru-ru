---
title: "Неявное приведение &lt;имяТипа1&gt; к &lt;имяТипа2&gt; при копировании значения параметра &lt;имяПараметра&gt;, объявленного как ByRef, обратно в соответствующий аргумент. | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc41999"
  - "bc41999"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC41999"
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Неявное приведение &lt;имяТипа1&gt; к &lt;имяТипа2&gt; при копировании значения параметра &lt;имяПараметра&gt;, объявленного как ByRef, обратно в соответствующий аргумент.
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Процедура вызывается с помощью аргумента [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) типа, отличного от соответствующего ему параметра.  
  
 При передаче аргумента `ByRef` [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] иногда копирует его значение в локальную переменную в процедуре вместо передачи ссылки.  В таком случае, когда процедура возвращает результат, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] должен скопировать значение локальной переменной обратно в аргумент в коде вызова.  
  
 Если значение аргумента `ByRef` копируется в процедуру и аргумент и параметр имеют один и тот же тип, то преобразование не требуется.  Но если типы различны, то [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] должен выполнить преобразование в обоих направлениях.  Поскольку невозможно использовать `CType` или любые другие ключевые слова для определения параметра или аргумента процедуры преобразования, такое преобразование всегда является неявным.  
  
 По умолчанию это сообщение является предупреждающим.  Дополнительные сведения о скрытии предупреждений или их обработке как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC41999  
  
### Чтобы исправить эту ошибку  
  
-   По возможности следует использовать аргумент вызова того же типа, что и параметр процедуры, чтобы для [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] не было необходимости выполнять какие\-либо преобразования.  
  
-   Если необходимо вызвать процедуру с аргументом, тип которого отличается от типа параметра, но нет необходимости возвращать результат в аргумент вызова, то определите параметр как [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), а не `ByRef`.  
  
## См. также  
 [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Параметры и аргументы процедуры](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Передача аргументов по значению и по ссылке](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)