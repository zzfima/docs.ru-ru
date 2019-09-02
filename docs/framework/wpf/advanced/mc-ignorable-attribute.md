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
ms.openlocfilehash: b68909d94ad8cc5bba75b2c520db82c5ccf1b922
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70206189"
---
# <a name="mcignorable-attribute"></a><span data-ttu-id="eef90-102">Атрибут mc: Ignorable</span><span class="sxs-lookup"><span data-stu-id="eef90-102">mc:Ignorable Attribute</span></span>
<span data-ttu-id="eef90-103">Указывает, [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] какие префиксы пространства имен [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , обнаруженные в файле разметки, могут игнорироваться процессором.</span><span class="sxs-lookup"><span data-stu-id="eef90-103">Specifies which [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefixes encountered in a markup file may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="eef90-104">Атрибут поддерживает совместимость разметки как для пользовательского сопоставления пространства имен, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] так и для управления версиями. `mc:Ignorable`</span><span class="sxs-lookup"><span data-stu-id="eef90-104">The `mc:Ignorable` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage-single-prefix"></a><span data-ttu-id="eef90-105">Использование атрибута XAML (один префикс)</span><span class="sxs-lookup"><span data-stu-id="eef90-105">XAML Attribute Usage (Single Prefix)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a><span data-ttu-id="eef90-106">Использование атрибута XAML (два префикса)</span><span class="sxs-lookup"><span data-stu-id="eef90-106">XAML Attribute Usage (Two Prefixes)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="eef90-107">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="eef90-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eef90-108">*Игнораблепрефикс, ignorablePrefix1 и т. д.*</span><span class="sxs-lookup"><span data-stu-id="eef90-108">*ignorablePrefix, ignorablePrefix1, etc.*</span></span>|<span data-ttu-id="eef90-109">Любая допустимая строка префикса, согласно спецификации XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="eef90-109">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="eef90-110">*игнораблеури*</span><span class="sxs-lookup"><span data-stu-id="eef90-110">*ignorableUri*</span></span>|<span data-ttu-id="eef90-111">Любой допустимый URI для обозначения пространства имен в соответствии с спецификацией XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="eef90-111">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="eef90-112">*сиселементканбеигноред*</span><span class="sxs-lookup"><span data-stu-id="eef90-112">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="eef90-113">Элемент, который может игнорироваться [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] реализациями процессора, если базовый тип не может быть разрешен.</span><span class="sxs-lookup"><span data-stu-id="eef90-113">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eef90-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="eef90-114">Remarks</span></span>  
 <span data-ttu-id="eef90-115">Префикс пространства имен является рекомендуемым соглашением о префиксах [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для использования при сопоставлении пространства имен `http://schemas.openxmlformats.org/markup-compatibility/2006`Compatibility. [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] `mc`</span><span class="sxs-lookup"><span data-stu-id="eef90-115">The `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefix is the recommended prefix convention to use when mapping the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compatibility namespace `http://schemas.openxmlformats.org/markup-compatibility/2006`.</span></span>  
  
 <span data-ttu-id="eef90-116">Элементы или атрибуты, для которых префиксная часть имени элемента определяются как `mc:Ignorable` , не будут вызывать ошибки при обработке [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессором.</span><span class="sxs-lookup"><span data-stu-id="eef90-116">Elements or attributes where the prefix portion of the element name are identified as `mc:Ignorable` will not raise errors when processed by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="eef90-117">Если этот атрибут не может быть разрешен в базовый тип или конструкцию программирования, этот элемент игнорируется.</span><span class="sxs-lookup"><span data-stu-id="eef90-117">If that attribute could not be resolved to an underlying type or programming construct, then that element is ignored.</span></span> <span data-ttu-id="eef90-118">Обратите внимание, что пропущенные элементы могут по-прежнему создавать дополнительные ошибки синтаксического анализа для дополнительных требований к элементам, которые являются побочными эффектами для этого элемента, который не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="eef90-118">Note however that ignored elements might still generate additional parsing errors for additional element requirements that are side effects of that element not being processed.</span></span> <span data-ttu-id="eef90-119">Например, для конкретной модели содержимого элемента может потребоваться только один дочерний элемент, но если указанный дочерний элемент был `mc:Ignorable` в префиксе, а указанный дочерний элемент не удалось разрешить в тип, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] то процессор может вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="eef90-119">For instance, a particular element content model might require exactly one child element, but if the specified child element was in an `mc:Ignorable` prefix, and the specified child element could not be resolved to a type, then the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor might raise an error.</span></span>  
  
 <span data-ttu-id="eef90-120">`mc:Ignorable`применяется только к сопоставлениям пространств имен с строками идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="eef90-120">`mc:Ignorable` only applies to namespace mappings to identifier strings.</span></span> <span data-ttu-id="eef90-121">`mc:Ignorable`не применяется к сопоставлениям пространств имен в сборках, которые указывают пространство имен CLR и сборку (или по умолчанию для текущего исполняемого файла в качестве сборки).</span><span class="sxs-lookup"><span data-stu-id="eef90-121">`mc:Ignorable` does not apply to namespace mappings into assemblies, which specify a CLR namespace and an assembly (or default to the current executable as the assembly).</span></span>  
  
 <span data-ttu-id="eef90-122">При реализации [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора реализация процессора не должна вызывать ошибки синтаксического анализа или обработки при разрешении типов для любого элемента или атрибута, дополненного префиксом, который определен как `mc:Ignorable`.</span><span class="sxs-lookup"><span data-stu-id="eef90-122">If you are implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor, your processor implementation must not raise parsing or processing errors on type resolution for any element or attribute that is qualified by a prefix that is identified as `mc:Ignorable`.</span></span> <span data-ttu-id="eef90-123">Но реализация процессора по-прежнему может вызывать исключения, которые являются вторичным результатом невозможности загрузки или обработки элемента, такого как пример одноэлементного элемента, заданный ранее.</span><span class="sxs-lookup"><span data-stu-id="eef90-123">But your processor implementation can still raise exceptions that are a secondary result of an element failing to load or be processed, such as the one-child element example given earlier.</span></span>  
  
 <span data-ttu-id="eef90-124">По умолчанию [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессор будет игнорировать содержимое внутри игнорируемого элемента.</span><span class="sxs-lookup"><span data-stu-id="eef90-124">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="eef90-125">Однако можно указать дополнительный атрибут [MC: ProcessContent](mc-processcontent-attribute.md), чтобы потребовать непрерывную обработку содержимого в игнорируемом элементе следующим доступным родительским элементом.</span><span class="sxs-lookup"><span data-stu-id="eef90-125">However, you can specify an additional attribute, [mc:ProcessContent Attribute](mc-processcontent-attribute.md), to require continued processing of content within an ignored element by the next available parent element.</span></span>  
  
 <span data-ttu-id="eef90-126">В атрибуте можно указать несколько префиксов, используя один или несколько пробельных символов в качестве разделителя, например: `mc:Ignorable="ignore1 ignore2"`.</span><span class="sxs-lookup"><span data-stu-id="eef90-126">Multiple prefixes can be specified in the attribute, using one or more white-space characters as the separator, for example: `mc:Ignorable="ignore1 ignore2"`.</span></span>  

 <span data-ttu-id="eef90-127">`http://schemas.openxmlformats.org/markup-compatibility/2006` Пространство имен определяет другие элементы и атрибуты, не описанные в этой области пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="eef90-127">The `http://schemas.openxmlformats.org/markup-compatibility/2006` namespace defines other elements and attributes that are not documented within this area of the SDK.</span></span> <span data-ttu-id="eef90-128">Дополнительные сведения см. в разделе [Спецификация совместимости XML-разметки](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span><span class="sxs-lookup"><span data-stu-id="eef90-128">For more information, see [XML Markup Compatibility Specification](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eef90-129">См. также</span><span class="sxs-lookup"><span data-stu-id="eef90-129">See also</span></span>

- <xref:System.Windows.Markup.XamlReader>
- [<span data-ttu-id="eef90-130">Атрибут PresentationOptions: Freeze</span><span class="sxs-lookup"><span data-stu-id="eef90-130">PresentationOptions:Freeze Attribute</span></span>](presentationoptions-freeze-attribute.md)
- [<span data-ttu-id="eef90-131">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="eef90-131">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="eef90-132">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="eef90-132">Documents in WPF</span></span>](documents-in-wpf.md)
