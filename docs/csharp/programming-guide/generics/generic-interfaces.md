---
title: "Универсальные интерфейсы. (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, generic interfaces
- generics [C#], interfaces
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
caps.latest.revision: 28
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2a9a994c339553b923b930660c0e129dd930de96
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="generic-interfaces-c-programming-guide"></a>Универсальные интерфейсы. (Руководство по программированию на C#)
Часто требуется определить интерфейсы для универсальных классов коллекций или для универсальных классов, представляющих элементы коллекции. Для универсальных классов предпочтительнее использовать универсальные интерфейсы, такие как <xref:System.IComparable%601>, вместо <xref:System.IComparable>, поскольку это позволяет избежать выполнения операция упаковки-преобразования и распаковки-преобразования для типов значений. В библиотеке классов .NET Framework в пространстве имен <xref:System.Collections.Generic> определяется несколько универсальных интерфейсов для работы с классами коллекций.  
  
 Если интерфейс задан в качестве ограничения для параметра типа, можно использовать только типы, реализующие такой интерфейс. В следующем примере кода демонстрируется класс `SortedList<T>`, который является производным от класса `GenericList<T>`. Дополнительные сведения см. в разделе [Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md). `SortedList<T>` добавляет ограничение `where T : IComparable<T>`. Это позволяет методу `BubbleSort` в `SortedList<T>` использовать универсальный метод <xref:System.IComparable%601.CompareTo%2A> в отношении элементов списка. В этом примере элементы списка относятся к простому классу `Person`, который реализует `IComparable<Person>`.  
  
 [!code-cs[csProgGuideGenerics#29](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_1.cs)]  
  
 В качестве ограничений для одного типа можно задать несколько интерфейсов, как показано ниже:  
  
 [!code-cs[csProgGuideGenerics#30](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_2.cs)]  
  
 Интерфейс может определять несколько параметров типа, как показано ниже:  
  
 [!code-cs[csProgGuideGenerics#31](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_3.cs)]  
  
 Правила наследования, действующие в отношении классов, также применяются к интерфейсам:  
  
 [!code-cs[csProgGuideGenerics#32](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_4.cs)]  
  
 Универсальные интерфейсы могут наследоваться от неуниверсальных интерфейсов, если универсальный интерфейс является контравариантным (то есть использует только в качестве возвращаемого значения только свой параметр типа). В библиотеке классов .NET Framework <xref:System.Collections.Generic.IEnumerable%601> наследуется от <xref:System.Collections.IEnumerable>, поскольку <xref:System.Collections.Generic.IEnumerable%601> использует `T` только в возвращаемом значении <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> и в методе считывания свойства <xref:System.Collections.Generic.IEnumerator%601.Current%2A>.  
  
 Конкретные классы могут реализовывать закрытые сконструированные интерфейсы, как показано ниже:  
  
 [!code-cs[csProgGuideGenerics#33](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_5.cs)]  
  
 Универсальные классы могут реализовывать универсальные интерфейсы или закрытые сконструированные интерфейсы при условии, что в списке параметров класса заданы все аргументы, требуемые интерфейсом, как показано ниже:  
  
 [!code-cs[csProgGuideGenerics#34](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_6.cs)]  
  
 Правила, управляющие перегрузкой методов, одинаковы для методов с универсальными классами, структурами или интерфейсами. Дополнительные сведения см. в разделе [Универсальные методы](../../../csharp/programming-guide/generics/generic-methods.md).  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [interface](../../../csharp/language-reference/keywords/interface.md)   
 [Универсальные шаблоны](~/docs/standard/generics/index.md)

