---
title: "Копирование значение &#39; ByRef &#39; параметр &#39; &lt;имя_параметра&gt;&#39; обратно в соответствующий аргумент сужает от типа &#39;&lt; Имя_типа1&gt;&#39; ввода &#39;&lt; имя_типа2&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords: BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4bf993639007162e2e17d4b8cb9dfe8d5316acaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument-narrows-from-type-39lttypename1gt39-to-type-39lttypename2gt39"></a>Копирование значение &#39; ByRef &#39; параметр &#39; &lt;имя_параметра&gt;&#39; обратно в соответствующий аргумент сужает от типа &#39;&lt; Имя_типа1&gt;&#39; ввода &#39;&lt; имя_типа2&gt;&#39;
Процедура вызывается с аргументом, который расширяется до соответствующего параметра типа и сужающие преобразования из параметра к аргументу.  
  
 При определении класса или структуры можно определить один или несколько операторов преобразования для преобразования типа класса или структуры в другие типы. Можно также определить операторы обратного преобразования для преобразования других типов обратно в тип класса или структуры. При использовании типа класса или структуры в вызове процедуры [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] может использовать эти операторы преобразования для преобразования типа аргумента в тип соответствующего параметра.  
  
 Если передается аргумент [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] иногда копирует его значение в локальную переменную в процедуре вместо передачи ссылки. В случае когда процедура возвращает результат, среда [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] должна скопировать значение локальной переменной обратно в аргумент в вызывающем коде.  
  
 Если значение аргумента `ByRef` копируется в процедуру, а аргумент и параметр имеют один и тот же тип, то преобразование не требуется. Но если типы различны, среда [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] должна выполнить преобразование в обоих направлениях. Если один из типов является типом соответствующего класса или структуры, среда [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] должна преобразовать его в другой тип и из него. Если один из этих преобразований является расширяющим, обратное преобразование может быть сужающим.  
  
 **Идентификатор ошибки:** BC32053  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   По возможности используйте аргумент вызова того же типа, что и параметр процедуры, чтобы среде [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] не нужно было выполнять никаких преобразований.  
  
-   Если необходимо вызвать процедуру с аргументом, тип которого отличается от типа параметра, но не обязательно должны возвращать значение в аргумент вызова, то определите параметр как [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) вместо `ByRef`.  
  
-   Если требуется возвращать значение в аргумент вызова, определите оператор обратного преобразования как [Widening](../../../visual-basic/language-reference/modifiers/widening.md), если это возможно.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Параметры и аргументы процедуры](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [Передача аргументов по значению и по ссылке](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [Практическое руководство. Определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [Преобразования типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
