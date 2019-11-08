---
title: 'Атрибут mc: Ignorable'
ms.date: 03/30/2017
helpviewer_keywords:
- mc XML namespace prefix [WPF]
- mc:Ignorable attribute
- XML [WPF], mc namespace prefix
- XAML [WPF], mc:Ignorable attribute
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
ms.openlocfilehash: e14ab0ebc7d44e2792307b16c7c0581ff7a71bc6
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740823"
---
# <a name="mcignorable-attribute"></a><span data-ttu-id="8df63-102">Атрибут mc: Ignorable</span><span class="sxs-lookup"><span data-stu-id="8df63-102">mc:Ignorable Attribute</span></span>
<span data-ttu-id="8df63-103">Указывает, какие префиксы пространства имен XML, обнаруженные в файле разметки, могут игнорироваться процессором [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8df63-103">Specifies which XML namespace prefixes encountered in a markup file may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="8df63-104">Атрибут `mc:Ignorable` поддерживает совместимость разметки как для пользовательского сопоставления пространства имен, так и для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] управления версиями.</span><span class="sxs-lookup"><span data-stu-id="8df63-104">The `mc:Ignorable` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage-single-prefix"></a><span data-ttu-id="8df63-105">Использование атрибута XAML (один префикс)</span><span class="sxs-lookup"><span data-stu-id="8df63-105">XAML Attribute Usage (Single Prefix)</span></span>  
  
```xaml  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a><span data-ttu-id="8df63-106">Использование атрибута XAML (два префикса)</span><span class="sxs-lookup"><span data-stu-id="8df63-106">XAML Attribute Usage (Two Prefixes)</span></span>  
  
```xaml  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="8df63-107">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="8df63-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8df63-108">*Игнораблепрефикс, ignorablePrefix1 и т. д.*</span><span class="sxs-lookup"><span data-stu-id="8df63-108">*ignorablePrefix, ignorablePrefix1, etc.*</span></span>|<span data-ttu-id="8df63-109">Любая допустимая строка префикса, согласно спецификации XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="8df63-109">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="8df63-110">*игнораблеури*</span><span class="sxs-lookup"><span data-stu-id="8df63-110">*ignorableUri*</span></span>|<span data-ttu-id="8df63-111">Любой допустимый URI для обозначения пространства имен в соответствии с спецификацией XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="8df63-111">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="8df63-112">*сиселементканбеигноред*</span><span class="sxs-lookup"><span data-stu-id="8df63-112">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="8df63-113">Элемент, который можно игнорировать с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] реализаций процессора, если базовый тип не может быть разрешен.</span><span class="sxs-lookup"><span data-stu-id="8df63-113">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8df63-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="8df63-114">Remarks</span></span>  
 <span data-ttu-id="8df63-115">Префикс пространства имен XML `mc` является рекомендуемым соглашением о префиксах для использования при сопоставлении `http://schemas.openxmlformats.org/markup-compatibility/2006`пространства имен совместимости [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8df63-115">The `mc` XML namespace prefix is the recommended prefix convention to use when mapping the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compatibility namespace `http://schemas.openxmlformats.org/markup-compatibility/2006`.</span></span>  
  
 <span data-ttu-id="8df63-116">Элементы или атрибуты, в которых префиксная часть имени элемента определяется как `mc:Ignorable`, не вызывает ошибок при обработке процессором [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8df63-116">Elements or attributes where the prefix portion of the element name are identified as `mc:Ignorable` will not raise errors when processed by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="8df63-117">Если этот атрибут не может быть разрешен в базовый тип или конструкцию программирования, этот элемент игнорируется.</span><span class="sxs-lookup"><span data-stu-id="8df63-117">If that attribute could not be resolved to an underlying type or programming construct, then that element is ignored.</span></span> <span data-ttu-id="8df63-118">Обратите внимание, что пропущенные элементы могут по-прежнему создавать дополнительные ошибки синтаксического анализа для дополнительных требований к элементам, которые являются побочными эффектами для этого элемента, который не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="8df63-118">Note however that ignored elements might still generate additional parsing errors for additional element requirements that are side effects of that element not being processed.</span></span> <span data-ttu-id="8df63-119">Например, для конкретной модели содержимого элемента может потребоваться только один дочерний элемент, но если указанный дочерний элемент находился в префиксе `mc:Ignorable`, а указанный дочерний элемент не удалось разрешить в тип, то процессор [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] может вызвать ошибку.</span><span class="sxs-lookup"><span data-stu-id="8df63-119">For instance, a particular element content model might require exactly one child element, but if the specified child element was in an `mc:Ignorable` prefix, and the specified child element could not be resolved to a type, then the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor might raise an error.</span></span>  
  
 <span data-ttu-id="8df63-120">`mc:Ignorable` применяется только к сопоставлениям пространств имен с строками идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="8df63-120">`mc:Ignorable` only applies to namespace mappings to identifier strings.</span></span> <span data-ttu-id="8df63-121">`mc:Ignorable` не применяется к сопоставлениям пространств имен в сборках, которые указывают пространство имен CLR и сборку (или по умолчанию для текущего исполняемого файла в качестве сборки).</span><span class="sxs-lookup"><span data-stu-id="8df63-121">`mc:Ignorable` does not apply to namespace mappings into assemblies, which specify a CLR namespace and an assembly (or default to the current executable as the assembly).</span></span>  
  
 <span data-ttu-id="8df63-122">При реализации [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора реализация процессора не должна вызывать ошибки синтаксического анализа или обработки при разрешении типов для любого элемента или атрибута, дополненного префиксом, который определен как `mc:Ignorable`.</span><span class="sxs-lookup"><span data-stu-id="8df63-122">If you are implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor, your processor implementation must not raise parsing or processing errors on type resolution for any element or attribute that is qualified by a prefix that is identified as `mc:Ignorable`.</span></span> <span data-ttu-id="8df63-123">Но реализация процессора по-прежнему может вызывать исключения, которые являются вторичным результатом невозможности загрузки или обработки элемента, такого как пример одноэлементного элемента, заданный ранее.</span><span class="sxs-lookup"><span data-stu-id="8df63-123">But your processor implementation can still raise exceptions that are a secondary result of an element failing to load or be processed, such as the one-child element example given earlier.</span></span>  
  
 <span data-ttu-id="8df63-124">По умолчанию обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] будет игнорировать содержимое в игнорируемом элементе.</span><span class="sxs-lookup"><span data-stu-id="8df63-124">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="8df63-125">Однако можно указать дополнительный атрибут [MC: ProcessContent](mc-processcontent-attribute.md), чтобы потребовать непрерывную обработку содержимого в игнорируемом элементе следующим доступным родительским элементом.</span><span class="sxs-lookup"><span data-stu-id="8df63-125">However, you can specify an additional attribute, [mc:ProcessContent Attribute](mc-processcontent-attribute.md), to require continued processing of content within an ignored element by the next available parent element.</span></span>  
  
 <span data-ttu-id="8df63-126">В атрибуте можно указать несколько префиксов, используя один или несколько символов пробела в качестве разделителя, например: `mc:Ignorable="ignore1 ignore2"`.</span><span class="sxs-lookup"><span data-stu-id="8df63-126">Multiple prefixes can be specified in the attribute, using one or more white-space characters as the separator, for example: `mc:Ignorable="ignore1 ignore2"`.</span></span>  

 <span data-ttu-id="8df63-127">Пространство имен `http://schemas.openxmlformats.org/markup-compatibility/2006` определяет другие элементы и атрибуты, не описанные в этой области пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="8df63-127">The `http://schemas.openxmlformats.org/markup-compatibility/2006` namespace defines other elements and attributes that are not documented within this area of the SDK.</span></span> <span data-ttu-id="8df63-128">Дополнительные сведения см. в разделе [Спецификация совместимости XML-разметки](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span><span class="sxs-lookup"><span data-stu-id="8df63-128">For more information, see [XML Markup Compatibility Specification](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8df63-129">См. также</span><span class="sxs-lookup"><span data-stu-id="8df63-129">See also</span></span>

- <xref:System.Windows.Markup.XamlReader>
- [<span data-ttu-id="8df63-130">Атрибут PresentationOptions: Freeze</span><span class="sxs-lookup"><span data-stu-id="8df63-130">PresentationOptions:Freeze Attribute</span></span>](presentationoptions-freeze-attribute.md)
- [<span data-ttu-id="8df63-131">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="8df63-131">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="8df63-132">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="8df63-132">Documents in WPF</span></span>](documents-in-wpf.md)
