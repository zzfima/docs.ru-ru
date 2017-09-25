---
title: "in (универсальный модификатор) (Справочник по C#)"
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
ms.translationtype: HT
ms.sourcegitcommit: 775e4512a5ff31c7059961f6332c6bdc0dc5247a
ms.openlocfilehash: 663fa75a7e214ed97efb45dda2c9ac298559653d
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="in-generic-modifier-c-reference"></a>in (универсальный модификатор) (Справочник по C#)
Для параметров универсального типа ключевое слово `in` указывает, что параметр типа является контравариантным. Ключевое слово `in` может применяться в универсальных интерфейсах и делегатах.  
  
 Контравариантность позволяет использовать производные типы со степенью наследования меньше, чем у типа, заданного универсальным параметром. Благодаря этому можно осуществлять неявное преобразование классов, реализующих вариантные интерфейсы, и неявное преобразование типов делегатов. Ковариантность и контравариантность поддерживаются для ссылочных типов, но не для типов значений.  
  
 Тип может быть объявлен контравариантным в универсальном интерфейсе или делегате, если он используется только как тип аргументов метода, но не как тип значения, возвращаемого методом. Параметры `Ref` и `out` не могут быть вариантными.  
  
 Интерфейс с параметром контравариантного типа позволяет своим методам принимать аргументы производных типов, степень наследования у которых меньше, чем у параметра типа интерфейса. Например, поскольку в .NET Framework 4 в интерфейсе <xref:System.Collections.Generic.IComparer%601> тип T является ковариантным, можно присвоить объект типа `IComparer(Of Person)` объекту типа `IComparer(Of Employee)` без применения каких-либо специальных методов преобразования, если `Employee` наследует `Person`.  
  
 Контравариантный делегат может быть назначен другому делегату того же типа, но с производным параметром универсального типа меньшей степени.  
  
 Дополнительные сведения см. в разделе [Ковариация и контравариантность](../../programming-guide/concepts/covariance-contravariance/index.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как объявить, расширить и реализовать контравариантный универсальный интерфейс. В нем также показано, как можно использовать неявное преобразование для классов, реализующих этот интерфейс.  
  
 [!code-cs[csVarianceKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_1.cs)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как объявить контравариантный универсальный делегат. В нем также показано, как можно выполнить неявное преобразование типа делегата.  
  
 [!code-cs[csVarianceKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_2.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [out](../../../csharp/language-reference/keywords/out-generic-modifier.md)   
 [Ковариация и контравариантность](../../programming-guide/concepts/covariance-contravariance/index.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)

