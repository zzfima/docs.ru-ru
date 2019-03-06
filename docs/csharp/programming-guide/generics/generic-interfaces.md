---
title: Руководство по программированию на C#. Универсальные интерфейсы
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generic interfaces
- generics [C#], interfaces
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
ms.openlocfilehash: 09b8200d19b6f94cab423dbe4001fbeda83aa06f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974241"
---
# <a name="generic-interfaces-c-programming-guide"></a>Универсальные интерфейсы. (Руководство по программированию на C#)
Часто требуется определить интерфейсы для универсальных классов коллекций или для универсальных классов, представляющих элементы коллекции. Для универсальных классов предпочтительнее использовать универсальные интерфейсы, такие как <xref:System.IComparable%601>, вместо <xref:System.IComparable>, поскольку это позволяет избежать выполнения операция упаковки-преобразования и распаковки-преобразования для типов значений. В библиотеке классов .NET Framework в пространстве имен <xref:System.Collections.Generic> определяется несколько универсальных интерфейсов для работы с классами коллекций.  
  
 Если интерфейс задан в качестве ограничения для параметра типа, можно использовать только типы, реализующие такой интерфейс. В следующем примере кода демонстрируется класс `SortedList<T>`, который является производным от класса `GenericList<T>`. Дополнительные сведения см. в разделе [Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md). `SortedList<T>` добавляет ограничение `where T : IComparable<T>`. Это позволяет методу `BubbleSort` в `SortedList<T>` использовать универсальный метод <xref:System.IComparable%601.CompareTo%2A> в отношении элементов списка. В этом примере элементы списка относятся к простому классу `Person`, который реализует `IComparable<Person>`.  
  
 [!code-csharp[csProgGuideGenerics#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics2.cs#29)]  
  
 В качестве ограничений для одного типа можно задать несколько интерфейсов, как показано ниже:  
  
 [!code-csharp[csProgGuideGenerics#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#30)]  
  
 Интерфейс может определять несколько параметров типа, как показано ниже:  
  
 [!code-csharp[csProgGuideGenerics#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#31)]  
  
 Правила наследования, действующие в отношении классов, также применяются к интерфейсам:  
  
 [!code-csharp[csProgGuideGenerics#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#32)]  
  
 Универсальные интерфейсы могут наследоваться от неуниверсальных интерфейсов, если универсальный интерфейс является контравариантным (то есть использует только в качестве возвращаемого значения только свой параметр типа). В библиотеке классов .NET Framework <xref:System.Collections.Generic.IEnumerable%601> наследуется от <xref:System.Collections.IEnumerable>, поскольку <xref:System.Collections.Generic.IEnumerable%601> использует `T` только в возвращаемом значении <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> и в методе считывания свойства <xref:System.Collections.Generic.IEnumerator%601.Current%2A>.  
  
 Конкретные классы могут реализовывать закрытые сконструированные интерфейсы, как показано ниже:  
  
 [!code-csharp[csProgGuideGenerics#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#33)]  
  
 Универсальные классы могут реализовывать универсальные интерфейсы или закрытые сконструированные интерфейсы при условии, что в списке параметров класса заданы все аргументы, требуемые интерфейсом, как показано ниже:  
  
 [!code-csharp[csProgGuideGenerics#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#34)]  
  
 Правила, управляющие перегрузкой методов, одинаковы для методов с универсальными классами, структурами или интерфейсами. Дополнительные сведения см. в разделе [Универсальные методы](../../../csharp/programming-guide/generics/generic-methods.md).  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md)
- [interface](../../../csharp/language-reference/keywords/interface.md)
- [Универсальные шаблоны](~/docs/standard/generics/index.md)
