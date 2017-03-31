---
title: "in (универсальный модификатор) (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
ms.assetid: 3a778c36-8aed-4ebe-aa8b-39f4057215b1
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b6c490d14b47aaa527fe2ddb3627ea0a84bfe604
ms.lasthandoff: 03/13/2017

---
# <a name="in-generic-modifier-c-reference"></a>in (универсальный модификатор) (Справочник по C#)
Для параметров универсального типа ключевое слово `in` указывает, что параметр типа является контравариантным. Ключевое слово `in` может применяться в универсальных интерфейсах и делегатах.  
  
 Контравариантность позволяет использовать производные типы со степенью наследования меньше, чем у типа, заданного универсальным параметром. Благодаря этому можно осуществлять неявное преобразование классов, реализующих вариантные интерфейсы, и неявное преобразование типов делегатов. Ковариантность и контравариантность поддерживаются для ссылочных типов, но не для типов значений.  
  
 Тип может быть объявлен контравариантным в универсальном интерфейсе или делегате, если он используется только как тип аргументов метода, но не как тип значения, возвращаемого методом. Параметры `Ref` и `out` не могут быть вариантными.  
  
 Интерфейс с параметром контравариантного типа позволяет своим методам принимать аргументы производных типов, степень наследования у которых меньше, чем у параметра типа интерфейса. Например, поскольку в .NET Framework 4 в интерфейсе <xref:System.Collections.Generic.IComparer%601> тип T является контравариантным, можно назначить объект типа `IComparer(Of Person)` объекту типа `IComparer(Of Employee)` без применения каких-либо специальных методов преобразования, если `Employee` наследует `Person`.  
  
 Контравариантный делегат может быть назначен другому делегату того же типа, но с производным параметром универсального типа меньшей степени.  
  
 Дополнительные сведения см. в разделе [Ковариация и контравариантность](http://msdn.microsoft.com/library/a58cc086-276f-4f91-a366-85b7f95f38b8).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как объявить, расширить и реализовать контравариантный универсальный интерфейс. В нем также показано, как можно использовать неявное преобразование для классов, реализующих этот интерфейс.  
  
 [!code-cs[csVarianceKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_1.cs)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как объявить контравариантный универсальный делегат. В нем также показано, как можно выполнить неявное преобразование типа делегата.  
  
 [!code-cs[csVarianceKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_2.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>См. также  
 [out](../../../csharp/language-reference/keywords/out-generic-modifier.md)   
 [Ковариация и контравариантность](http://msdn.microsoft.com/library/a58cc086-276f-4f91-a366-85b7f95f38b8)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)
