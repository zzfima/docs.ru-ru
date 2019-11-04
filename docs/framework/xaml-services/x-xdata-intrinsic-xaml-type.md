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
ms.openlocfilehash: 8496e7c87cf7e6eea996ca7af4f288b7495c7661
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459897"
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="7fc31-102">Встроенный тип XAML x:XData</span><span class="sxs-lookup"><span data-stu-id="7fc31-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="7fc31-103">Включает размещение островов XML-данных в рабочей среде XAML.</span><span class="sxs-lookup"><span data-stu-id="7fc31-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="7fc31-104">XML-элементы в `x:XData` не должны обрабатываться обработчиками XAML так, как если бы они были частью действующего пространства имен XAML по умолчанию или любого другого пространства имен XAML.</span><span class="sxs-lookup"><span data-stu-id="7fc31-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="7fc31-105">`x:XData` может содержать произвольный XML-файл правильного формата.</span><span class="sxs-lookup"><span data-stu-id="7fc31-105">`x:XData` can contain arbitrary well-formed XML.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="7fc31-106">Использование элемента объекта XAML</span><span class="sxs-lookup"><span data-stu-id="7fc31-106">XAML Object Element Usage</span></span>  
  
```xaml  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="7fc31-107">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="7fc31-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`elementDataRoot`|<span data-ttu-id="7fc31-108">Единственный корневой элемент вложенного острова данных.</span><span class="sxs-lookup"><span data-stu-id="7fc31-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="7fc31-109">Для большинства конечных потребителей XML, не имеющий одного корня, считается недопустимым.</span><span class="sxs-lookup"><span data-stu-id="7fc31-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="7fc31-110">В частности, один корневой элемент необходим, если `x:XData` предназначен в качестве источника XML-данных для WPF или многих других технологий, использующих источники XML для привязки данных.</span><span class="sxs-lookup"><span data-stu-id="7fc31-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|  
|`[elementData]`|<span data-ttu-id="7fc31-111">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="7fc31-111">Optional.</span></span> <span data-ttu-id="7fc31-112">XML, представляющий XML-данные.</span><span class="sxs-lookup"><span data-stu-id="7fc31-112">XML that represents the XML data.</span></span> <span data-ttu-id="7fc31-113">В качестве данных элемента может содержаться любое количество элементов, а вложенные элементы могут содержаться в других элементах. Однако применяются общие правила XML.</span><span class="sxs-lookup"><span data-stu-id="7fc31-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fc31-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="7fc31-114">Remarks</span></span>  
 <span data-ttu-id="7fc31-115">XML-элементы в объекте `x:XData` могут повторно объявлять все возможные пространства имен и префиксы, содержащиеся в данных XMLDOM.</span><span class="sxs-lookup"><span data-stu-id="7fc31-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>  
  
 <span data-ttu-id="7fc31-116">Программный доступ к XML-данным и `x:XData` встроенного типа XAML возможно в .NET Framework службах XAML через класс <xref:System.Windows.Markup.XData>.</span><span class="sxs-lookup"><span data-stu-id="7fc31-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET Framework XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="7fc31-117">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="7fc31-117">WPF Usage Notes</span></span>  
 <span data-ttu-id="7fc31-118">Объект `x:XData` в основном используется в качестве дочернего объекта <xref:System.Windows.Data.XmlDataProvider>или же в качестве дочернего объекта свойства <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> (в XAML это обычно выражается в синтаксисе элемента свойства).</span><span class="sxs-lookup"><span data-stu-id="7fc31-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>  
  
 <span data-ttu-id="7fc31-119">Данные обычно должны переопределять базовое пространство имен XML в области данных, чтобы стать новым пространством имен XML по умолчанию (для которого задана пустая строка).</span><span class="sxs-lookup"><span data-stu-id="7fc31-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="7fc31-120">Это проще всего для простых островов данных, так как выражения <xref:System.Windows.Data.Binding.XPath%2A>, используемые для ссылки на данные и привязки к ним, могут не включать префиксы.</span><span class="sxs-lookup"><span data-stu-id="7fc31-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="7fc31-121">Более сложные острова данных могут определять несколько префиксов для данных и использовать конкретный префикс для пространства имен XML в корне.</span><span class="sxs-lookup"><span data-stu-id="7fc31-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="7fc31-122">В этом случае все <xref:System.Windows.Data.Binding.XPath%2A>ные ссылки на выражения должны включать соответствующий префикс, сопоставленный с пространством имен.</span><span class="sxs-lookup"><span data-stu-id="7fc31-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="7fc31-123">Более подробную информацию см. в разделе [Общие сведения о связывании данных](../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7fc31-123">For more information, see [Data Binding Overview](../../desktop-wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="7fc31-124">Технически `x:XData` можно использовать в качестве содержимого любого свойства типа <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="7fc31-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="7fc31-125">Однако <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> является единственной выразительной реализацией.</span><span class="sxs-lookup"><span data-stu-id="7fc31-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fc31-126">См. также</span><span class="sxs-lookup"><span data-stu-id="7fc31-126">See also</span></span>

- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="7fc31-127">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="7fc31-127">Data Binding Overview</span></span>](../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="7fc31-128">Привязка расширения разметки</span><span class="sxs-lookup"><span data-stu-id="7fc31-128">Binding Markup Extension</span></span>](../wpf/advanced/binding-markup-extension.md)
