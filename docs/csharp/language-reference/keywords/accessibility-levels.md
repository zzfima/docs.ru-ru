---
title: "Уровни доступности (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "модификаторы доступа [C#], уровни доступности"
  - "уровни доступности"
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Уровни доступности (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Модификаторы доступа [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) или [private](../../../csharp/language-reference/keywords/private.md) используются для указания одного из следующих объявленных уровней доступности к членам.  
  
|Объявленная доступность|Значение|  
|-----------------------------|--------------|  
|`public`|Неограниченный доступ.|  
|`protected`|Доступ ограничен содержащим классом или типами, которые являются производными от содержащего класса.|  
|`internal`|Доступ ограничен текущей сборкой.|  
|`protected` `internal`|Доступ ограничен текущей сборкой или типами, которые являются производными от содержащего класса.|  
|`private`|Доступ ограничен содержащим типом.|  
  
 Только один модификатор доступа может быть указан для члена или типа, за исключением случая, когда используется сочетание `protected` `internal`.  
  
 Модификаторы доступа не могут быть указаны для пространств имен.  Пространства имен не имеют ограничений доступа.  
  
 В зависимости от контекста, в котором производится объявление члена, допускаются только некоторые объявленные уровни доступности.  Если модификатор доступа не указывается в объявлении члена, используется доступность по умолчанию.  
  
 Типы верхнего уровня, не вложенные в другие типы, могут иметь только уровень доступности `internal` или `public`.  Для этих типов уровнем доступности по умолчанию является `internal`.  
  
 Вложенные типы, которые являются членами других типов, могут иметь объявленные уровни доступности, указанные в следующей таблице.  
  
|Члены типа|Уровень доступности членов по умолчанию|Допустимые объявленные уровни доступности члена|  
|----------------|---------------------------------------------|-----------------------------------------------------|  
|`enum`|`public`|None|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected` `internal`|  
|`interface`|`public`|None|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 Доступность вложенного типа зависит от [домена доступности](../../../csharp/language-reference/keywords/accessibility-domain.md), который определяется объявленной доступностью члена и доменом доступности типа, непосредственно содержащего вложенный тип.  Однако домен доступности вложенного типа не может выходить за границы домена доступности содержащего его типа.  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Домен доступности](../../../csharp/language-reference/keywords/accessibility-domain.md)   
 [Ограничения на использование уровней доступности](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)   
 [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [закрытый](../../../csharp/language-reference/keywords/private.md)   
 [защищенные](../../../csharp/language-reference/keywords/protected.md)   
 [внутренние](../../../csharp/language-reference/keywords/internal.md)