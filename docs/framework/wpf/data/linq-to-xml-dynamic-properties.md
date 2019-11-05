---
title: Справочник по динамическим свойствам LINQ to XML
ms.date: 10/22/2019
ms.topic: reference
ms.openlocfilehash: 48b51e92eb78786b2cc189e3e7daa00875b41585
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197054"
---
# <a name="linq-to-xml-dynamic-properties"></a>Динамические свойства LINQ to XML

В этом разделе приведены справочные сведения о динамических свойствах в LINQ to XML. В частности, эти свойства представляются классами <xref:System.Xml.Linq.XAttribute> и <xref:System.Xml.Linq.XElement>, которые находятся в пространстве имен <xref:System.Xml.Linq>.

Как уже рассказывалось в разделе [Общие сведения о привязке данных WPF с помощью LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md), каждое динамическое свойство эквивалентно стандартному открытому свойству или методу в том же классе. В большинстве случаев следует использовать именно эти стандартные методы. Динамические свойства предоставляются специально для связывания данных с помощью LINQ to XML. Дополнительные сведения о стандартных членах этих классов см. в разделах со справочными сведениями <xref:System.Xml.Linq.XAttribute> и <xref:System.Xml.Linq.XElement>.

По разрешаемым ими значениям описанные в этом разделе динамические свойства делятся на две категории:

- Простые, например свойства `Value` в классах <xref:System.Xml.Linq.XAttribute> и <xref:System.Xml.Linq.XElement>, которые разрешаются в одно значение.

- Индексированные значения, например свойства [Elements](elements-xelement-dynamic-property.md) и [Descendants](descendants-xelement-dynamic-property.md) класса <xref:System.Xml.Linq.XElement>, которые разрешаются в тип индексатора. Чтобы типы индексатора разрешились в требуемое значение или коллекцию, им необходимо передать параметр развернутого имени.

Все динамические свойства, которые возвращают индексированное значение типа <xref:System.Collections.Generic.IEnumerable%601>, используют отложенное выполнение. Дополнительные сведения об отложенном выполнении см. в разделе [Введение в запросы LINQ (C#)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).

## <a name="reference"></a>Справочники

- <xref:System.Xml.Linq>
- <xref:System.Xml.Linq.XElement?displayProperty=fullName>
- <xref:System.Xml.Linq.XAttribute?displayProperty=fullName>

## <a name="see-also"></a>См. также

- [Привязка данных WPF с помощью LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md)
- [Общие сведения о привязке данных WPF с помощью LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md)
- [Введение в запросы LINQ (C#)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
