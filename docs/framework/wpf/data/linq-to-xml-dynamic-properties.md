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
# <a name="linq-to-xml-dynamic-properties"></a><span data-ttu-id="db0ef-102">Динамические свойства LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="db0ef-102">LINQ to XML dynamic properties</span></span>

<span data-ttu-id="db0ef-103">В этом разделе приведены справочные сведения о динамических свойствах в LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="db0ef-103">This section provides reference information about the dynamic properties in LINQ to XML.</span></span> <span data-ttu-id="db0ef-104">В частности, эти свойства представляются классами <xref:System.Xml.Linq.XAttribute> и <xref:System.Xml.Linq.XElement>, которые находятся в пространстве имен <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="db0ef-104">Specifically, these properties are exposed by the <xref:System.Xml.Linq.XAttribute> and <xref:System.Xml.Linq.XElement> classes, which are in the <xref:System.Xml.Linq> namespace.</span></span>

<span data-ttu-id="db0ef-105">Как уже рассказывалось в разделе [Общие сведения о привязке данных WPF с помощью LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md), каждое динамическое свойство эквивалентно стандартному открытому свойству или методу в том же классе.</span><span class="sxs-lookup"><span data-stu-id="db0ef-105">As explained in the topic [Overview of WPF data binding with LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md), each of the dynamic properties is equivalent to a standard public property or method in the same class.</span></span> <span data-ttu-id="db0ef-106">В большинстве случаев следует использовать именно эти стандартные методы. Динамические свойства предоставляются специально для связывания данных с помощью LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="db0ef-106">These standard members should be used for most purposes; dynamic properties are provided specifically for LINQ to XML data binding scenarios.</span></span> <span data-ttu-id="db0ef-107">Дополнительные сведения о стандартных членах этих классов см. в разделах со справочными сведениями <xref:System.Xml.Linq.XAttribute> и <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="db0ef-107">For more information about the standard members of these classes, see the <xref:System.Xml.Linq.XAttribute> and <xref:System.Xml.Linq.XElement> reference topics.</span></span>

<span data-ttu-id="db0ef-108">По разрешаемым ими значениям описанные в этом разделе динамические свойства делятся на две категории:</span><span class="sxs-lookup"><span data-stu-id="db0ef-108">With respect to their resolved values, the dynamic properties in this section fall into two categories:</span></span>

- <span data-ttu-id="db0ef-109">Простые, например свойства `Value` в классах <xref:System.Xml.Linq.XAttribute> и <xref:System.Xml.Linq.XElement>, которые разрешаются в одно значение.</span><span class="sxs-lookup"><span data-stu-id="db0ef-109">Simple ones, such as the `Value` properties in the <xref:System.Xml.Linq.XAttribute> and <xref:System.Xml.Linq.XElement> classes, that resolve to a single value.</span></span>

- <span data-ttu-id="db0ef-110">Индексированные значения, например свойства [Elements](elements-xelement-dynamic-property.md) и [Descendants](descendants-xelement-dynamic-property.md) класса <xref:System.Xml.Linq.XElement>, которые разрешаются в тип индексатора.</span><span class="sxs-lookup"><span data-stu-id="db0ef-110">Indexed values, such as the [Elements](elements-xelement-dynamic-property.md) and [Descendants](descendants-xelement-dynamic-property.md) properties of <xref:System.Xml.Linq.XElement>, that resolve into an indexer type.</span></span> <span data-ttu-id="db0ef-111">Чтобы типы индексатора разрешились в требуемое значение или коллекцию, им необходимо передать параметр развернутого имени.</span><span class="sxs-lookup"><span data-stu-id="db0ef-111">For indexer types to be resolved to the desired value or collection, an expanded name parameter must be passed to them.</span></span>

<span data-ttu-id="db0ef-112">Все динамические свойства, которые возвращают индексированное значение типа <xref:System.Collections.Generic.IEnumerable%601>, используют отложенное выполнение.</span><span class="sxs-lookup"><span data-stu-id="db0ef-112">All the dynamic properties that return an indexed value of type <xref:System.Collections.Generic.IEnumerable%601> use deferred execution.</span></span> <span data-ttu-id="db0ef-113">Дополнительные сведения об отложенном выполнении см. в разделе [Введение в запросы LINQ (C#)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="db0ef-113">For more information about deferred execution, see [Introduction to LINQ queries (C#)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>

## <a name="reference"></a><span data-ttu-id="db0ef-114">Справочники</span><span class="sxs-lookup"><span data-stu-id="db0ef-114">Reference</span></span>

- <xref:System.Xml.Linq>
- <xref:System.Xml.Linq.XElement?displayProperty=fullName>
- <xref:System.Xml.Linq.XAttribute?displayProperty=fullName>

## <a name="see-also"></a><span data-ttu-id="db0ef-115">См. также</span><span class="sxs-lookup"><span data-stu-id="db0ef-115">See also</span></span>

- [<span data-ttu-id="db0ef-116">Привязка данных WPF с помощью LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="db0ef-116">WPF data binding with LINQ to XML</span></span>](wpf-data-binding-with-linq-to-xml-overview.md)
- [<span data-ttu-id="db0ef-117">Общие сведения о привязке данных WPF с помощью LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="db0ef-117">WPF data binding with LINQ to XML overview</span></span>](wpf-data-binding-with-linq-to-xml-overview.md)
- [<span data-ttu-id="db0ef-118">Введение в запросы LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="db0ef-118">Introduction to LINQ queries (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
