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
ms.openlocfilehash: 3a16379fd6104342529723bf6d0bc9fb4762cf92
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="4446a-102">Встроенный тип XAML x:XData</span><span class="sxs-lookup"><span data-stu-id="4446a-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="4446a-103">Обеспечивает размещение острова данных XML в пределах рабочей среды XAML.</span><span class="sxs-lookup"><span data-stu-id="4446a-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="4446a-104">XML-элементы в `x:XData` не следует обрабатывать обработчиками XAML, как если бы они были частью пространства имен XAML по умолчанию действующего или любое другое пространство имен XAML.</span><span class="sxs-lookup"><span data-stu-id="4446a-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="4446a-105">`x:XData` может содержать произвольный корректный XML.</span><span class="sxs-lookup"><span data-stu-id="4446a-105">`x:XData` can contain arbitrary well-formed XML.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="4446a-106">Использование элемента объекта XAML</span><span class="sxs-lookup"><span data-stu-id="4446a-106">XAML Object Element Usage</span></span>  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="4446a-107">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="4446a-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`elementDataRoot`|<span data-ttu-id="4446a-108">Единственный корневой элемент вложенной области данных.</span><span class="sxs-lookup"><span data-stu-id="4446a-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="4446a-109">Для большинства окончательной потребителей XML, который имеет один корневой считается недействительным.</span><span class="sxs-lookup"><span data-stu-id="4446a-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="4446a-110">В частности, один корень является обязательным, если `x:XData` предназначен как источник данных XML для WPF и многих других технологий, использующих источники XML для привязки данных.</span><span class="sxs-lookup"><span data-stu-id="4446a-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|  
|`[elementData]`|<span data-ttu-id="4446a-111">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="4446a-111">Optional.</span></span> <span data-ttu-id="4446a-112">XML-ФАЙЛ, который представляет XML-данные.</span><span class="sxs-lookup"><span data-stu-id="4446a-112">XML that represents the XML data.</span></span> <span data-ttu-id="4446a-113">Как элемент данных может содержаться любое количество элементов и вложенные элементы, которые могут содержаться в других элементах; Однако применить общие правила XML.</span><span class="sxs-lookup"><span data-stu-id="4446a-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4446a-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="4446a-114">Remarks</span></span>  
 <span data-ttu-id="4446a-115">XML-элементы в `x:XData` объекта могут повторно объявлять все возможные пространства имен и префиксы внешней XML DOM в данных.</span><span class="sxs-lookup"><span data-stu-id="4446a-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>  
  
 <span data-ttu-id="4446a-116">Программный доступ к XML-данных и `x:XData` возможен встроенный тип XAML в службах XAML .NET Framework по <xref:System.Windows.Markup.XData> класса.</span><span class="sxs-lookup"><span data-stu-id="4446a-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET Framework XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="4446a-117">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="4446a-117">WPF Usage Notes</span></span>  
 <span data-ttu-id="4446a-118">`x:XData` Объекта в основном используется как дочерний объект <xref:System.Windows.Data.XmlDataProvider>, то же, как дочерний объект <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> свойство (XAML, это обычно выражается в синтаксис элемента свойства).</span><span class="sxs-lookup"><span data-stu-id="4446a-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>  
  
 <span data-ttu-id="4446a-119">Как правило, данные должны переопределять базовое пространство имен XML в пределах острова данных для нового пространства имен XML по умолчанию (задается пустая строка).</span><span class="sxs-lookup"><span data-stu-id="4446a-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="4446a-120">Это проще всего для простых данных о-ва поскольку <xref:System.Windows.Data.Binding.XPath%2A> выражениям, используемым для ссылки и привязки к данным можно избежать префиксов.</span><span class="sxs-lookup"><span data-stu-id="4446a-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="4446a-121">Более сложные острова данных может определить несколько префиксов для данных и использовать специальный префикс для пространства имен XML в корне.</span><span class="sxs-lookup"><span data-stu-id="4446a-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="4446a-122">В этом случае все <xref:System.Windows.Data.Binding.XPath%2A> ссылках в выражениях следует включить соответствующий префикс сопоставлены пространств имен.</span><span class="sxs-lookup"><span data-stu-id="4446a-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="4446a-123">Более подробную информацию см. в разделе [Общие сведения о связывании данных](../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4446a-123">For more information, see [Data Binding Overview](../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="4446a-124">С технической точки зрения `x:XData` можно использовать в качестве содержимого любого свойства типа <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="4446a-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="4446a-125">Тем не менее <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> является только Показательным реализацией.</span><span class="sxs-lookup"><span data-stu-id="4446a-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4446a-126">См. также</span><span class="sxs-lookup"><span data-stu-id="4446a-126">See Also</span></span>  
 <xref:System.Windows.Data.XmlDataProvider>  
 [<span data-ttu-id="4446a-127">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="4446a-127">Data Binding Overview</span></span>](../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="4446a-128">Привязка расширения разметки</span><span class="sxs-lookup"><span data-stu-id="4446a-128">Binding Markup Extension</span></span>](../../../docs/framework/wpf/advanced/binding-markup-extension.md)
