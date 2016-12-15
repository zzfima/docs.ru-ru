---
title: "При копировании значения ByRef параметра &lt;имяПараметра&gt; обратно в соответствующий аргумент тип &lt;имяТипа1&gt; сужается в тип &lt;имяТипа2&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc32053"
  - "vbc32053"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32053"
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# При копировании значения ByRef параметра &lt;имяПараметра&gt; обратно в соответствующий аргумент тип &lt;имяТипа1&gt; сужается в тип &lt;имяТипа2&gt;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Процедура вызывается с аргументом, расширяющим соответствующий тип параметра, а преобразование параметра к аргументу является сужающим.  
  
 При определении класса или структуры можно определить один или несколько операторов преобразования для преобразования типа класса или структуры к другим типам.  Можно также определить операторы обратного преобразования для преобразования других типов обратно к типу класса или структуры.  При использовании типов класса или структуры в вызове процедуры [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] может использовать эти операторы преобразования, чтобы преобразовать их к типу соответствующего параметра для этой процедуры.  
  
 При передаче аргумента [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] иногда копирует его значение в локальную переменную в процедуре вместо передачи ссылки.  В таком случае, когда процедура возвращает результат, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] должен скопировать значение локальной переменной обратно в аргумент в коде вызова.  
  
 Если значение аргумента `ByRef` копируется в процедуру и аргумент и параметр имеют один и тот же тип, то преобразование не требуется.  Но если типы различны, то [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] должен выполнить преобразование в обоих направлениях.  Если один из типов является типом соответствующего класса или структуры, то [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] должен выполнить его преобразование к другому типу и обратное преобразование.  Если одно их этих преобразований является расширяющим, то обратное преобразование может быть сужающим.  
  
 **Идентификатор ошибки**: BC32053  
  
### Чтобы исправить эту ошибку  
  
-   По возможности следует использовать аргумент вызова того же типа, что и параметр процедуры, чтобы для [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не было необходимости выполнять какие\-либо преобразования.  
  
-   Если необходимо вызвать процедуру с аргументом, тип которого отличается от типа параметра, но нет необходимости возвращать результат в аргумент вызова, то определите параметр как [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), а не `ByRef`.  
  
-   Если требуется возвращать значение в аргументе, определите оператор обратного преобразования как [Widening](../../../visual-basic/language-reference/modifiers/widening.md), если это возможно.  
  
## См. также  
 [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Параметры и аргументы процедуры](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Передача аргументов по значению и по ссылке](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Оператор Operator](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [Практическое руководство. Определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Преобразование типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)