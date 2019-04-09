---
title: Встроенный тип XAML x:XData
ms.date: 03/30/2017
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
ms.openlocfilehash: c8044bc341ded6ef7b03bbdf701e724654460d54
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125163"
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="c3a0a-102">Встроенный тип XAML x:XData</span><span class="sxs-lookup"><span data-stu-id="c3a0a-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="c3a0a-103">Обеспечивает размещение острова данных XML в пределах рабочей XAML.</span><span class="sxs-lookup"><span data-stu-id="c3a0a-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="c3a0a-104">XML-элементы в `x:XData` не следует обрабатывать процессорами XAML, как если бы они были частью пространства имен XAML по умолчанию действующего или любое другое пространство имен XAML.</span><span class="sxs-lookup"><span data-stu-id="c3a0a-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> `x:XData` <span data-ttu-id="c3a0a-105">может содержать произвольное XML правильного формата.</span><span class="sxs-lookup"><span data-stu-id="c3a0a-105">can contain arbitrary well-formed XML.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="c3a0a-106">Использование элемента объекта XAML</span><span class="sxs-lookup"><span data-stu-id="c3a0a-106">XAML Object Element Usage</span></span>  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="c3a0a-107">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="c3a0a-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`elementDataRoot`|<span data-ttu-id="c3a0a-108">Единственный корневой элемент вложенной области данных.</span><span class="sxs-lookup"><span data-stu-id="c3a0a-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="c3a0a-109">Для большинства итоговой потребителей XML, который имеет один корневой считается недопустимым.</span><span class="sxs-lookup"><span data-stu-id="c3a0a-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="c3a0a-110">В частности, один корень является обязательным, если `x:XData` предназначен как источник данных XML для WPF и многих других технологий, использующих источники XML для привязки данных.</span><span class="sxs-lookup"><span data-stu-id="c3a0a-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|  
|`[elementData]`|<span data-ttu-id="c3a0a-111">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="c3a0a-111">Optional.</span></span> <span data-ttu-id="c3a0a-112">XML, который представляет XML-данные.</span><span class="sxs-lookup"><span data-stu-id="c3a0a-112">XML that represents the XML data.</span></span> <span data-ttu-id="c3a0a-113">Как элемент данных может содержаться любое количество элементов и вложенных элементов, которые могут содержаться в других элементах; Тем не менее применить общие правила из XML.</span><span class="sxs-lookup"><span data-stu-id="c3a0a-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3a0a-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="c3a0a-114">Remarks</span></span>  
 <span data-ttu-id="c3a0a-115">XML-элементы в `x:XData` объект можно повторно объявить все возможные пространства имен и префиксы содержащего XMLDOM в данных.</span><span class="sxs-lookup"><span data-stu-id="c3a0a-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>  
  
 <span data-ttu-id="c3a0a-116">Программный доступ к XML-данных и `x:XData` возможен встроенный тип XAML в службах XAML .NET Framework через <xref:System.Windows.Markup.XData> класса.</span><span class="sxs-lookup"><span data-stu-id="c3a0a-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET Framework XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="c3a0a-117">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="c3a0a-117">WPF Usage Notes</span></span>  
 <span data-ttu-id="c3a0a-118">`x:XData` Объекта в основном используется в качестве дочернего объекта <xref:System.Windows.Data.XmlDataProvider>, или вариант, в качестве дочернего объекта <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> свойство (в XAML, это обычно выражается в синтаксис элемента свойства).</span><span class="sxs-lookup"><span data-stu-id="c3a0a-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>  
  
 <span data-ttu-id="c3a0a-119">Как правило, данные должны переопределять базовое пространство имен XML в пределах острова данных, чтобы быть новое пространство имен XML по умолчанию (присваивается пустая строка).</span><span class="sxs-lookup"><span data-stu-id="c3a0a-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="c3a0a-120">Это самый простой для простых данных о-ва поскольку <xref:System.Windows.Data.Binding.XPath%2A> выражениям, используемым для ссылки и привязки к данным можно избежать префиксов.</span><span class="sxs-lookup"><span data-stu-id="c3a0a-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="c3a0a-121">Более сложные острова данных может определить несколько префиксов для данных и использовать специальный префикс для пространства имен XML в корне.</span><span class="sxs-lookup"><span data-stu-id="c3a0a-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="c3a0a-122">В этом случае все <xref:System.Windows.Data.Binding.XPath%2A> ссылки выражение должно включать соответствующий префикс сопоставления пространства имен.</span><span class="sxs-lookup"><span data-stu-id="c3a0a-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="c3a0a-123">Более подробную информацию см. в разделе [Общие сведения о связывании данных](../wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c3a0a-123">For more information, see [Data Binding Overview](../wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="c3a0a-124">С технической точки зрения `x:XData` можно использовать в качестве содержимого любого свойства типа <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="c3a0a-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="c3a0a-125">Тем не менее <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> представляет собой реализацию только заметной.</span><span class="sxs-lookup"><span data-stu-id="c3a0a-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3a0a-126">См. также</span><span class="sxs-lookup"><span data-stu-id="c3a0a-126">See also</span></span>

- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="c3a0a-127">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="c3a0a-127">Data Binding Overview</span></span>](../wpf/data/data-binding-overview.md)
- [<span data-ttu-id="c3a0a-128">Привязка расширения разметки</span><span class="sxs-lookup"><span data-stu-id="c3a0a-128">Binding Markup Extension</span></span>](../wpf/advanced/binding-markup-extension.md)
