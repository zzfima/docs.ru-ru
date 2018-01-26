---
title: "Уровни доступности (Справочник по C#)"
ms.date: 12/06/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 816ee0fab3fae21bff2ffbfcbfe39d04dcf95025
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2017
---
# <a name="accessibility-levels-c-reference"></a>Уровни доступности (Справочник по C#)

Модификаторы доступа [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) или [private](../../../csharp/language-reference/keywords/private.md) используются для указания одного из следующих объявленных уровней доступности к членам.  
  
|Объявленная доступность|Значение|  
|----------------------------|-------------|  
|`public`|Неограниченный доступ.|  
|`protected`|Доступ ограничен содержащим классом или типами, которые являются производными от содержащего класса.|  
|`internal`|Доступ ограничен текущей сборкой.|  
|`protected internal`|Доступ ограничен текущей сборкой или типами, которые являются производными от содержащего класса.|  
|`private`|Доступ ограничен содержащим типом.|  
|`private protected`|Доступ ограничен содержащим классом или типами, которые являются производными от содержащего класса в текущей сборке. Доступно с версии C# 7.2. |  
  
 Вы можете указать для члена или типа только один модификатор доступа, за исключением случаев использования сочетаний `protected internal` или `private protected`.  
  
 Модификаторы доступа не могут быть указаны для пространств имен. Пространства имен не имеют ограничений доступа.  
  
 В зависимости от контекста, в котором производится объявление члена, допускаются только некоторые объявленные уровни доступности. Если модификатор доступа не указывается в объявлении члена, используется доступность по умолчанию.  
  
 Типы верхнего уровня, не вложенные в другие типы, могут иметь только уровень доступности `internal` или `public`. Для этих типов уровнем доступности по умолчанию является `internal`.  
  
 Вложенные типы, которые являются членами других типов, могут иметь объявленные уровни доступности, как указано в следующей таблице.  
  
|Члены типа|Уровень доступности членов по умолчанию|Допустимые объявленные уровни доступности члена|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|Нет|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|Нет|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 Доступность вложенного типа зависит от [домена доступности](../../../csharp/language-reference/keywords/accessibility-domain.md), который определяется объявленным уровнем доступности члена и доменом доступности непосредственно вмещающего его типа. Однако домен доступности вложенного типа не может выходить за границы домена доступности содержащего его типа.  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [Домен доступности](../../../csharp/language-reference/keywords/accessibility-domain.md)  
 [Ограничения на использование уровней доступности](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)  
 [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [public](../../../csharp/language-reference/keywords/public.md)  
 [private](../../../csharp/language-reference/keywords/private.md)  
 [protected](../../../csharp/language-reference/keywords/protected.md)  
 [internal](../../../csharp/language-reference/keywords/internal.md)
