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
ms.openlocfilehash: 7b8a2ef6e27bc6b25776157e59bef04b883fcb1a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="mcignorable-attribute"></a><span data-ttu-id="9830a-102">Атрибут mc: Ignorable</span><span class="sxs-lookup"><span data-stu-id="9830a-102">mc:Ignorable Attribute</span></span>
<span data-ttu-id="9830a-103">Определяет, какая [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] может проигнорировать префиксы пространства имен в файле разметки [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора.</span><span class="sxs-lookup"><span data-stu-id="9830a-103">Specifies which [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefixes encountered in a markup file may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="9830a-104">`mc:Ignorable` Атрибут поддерживает совместимость разметки для пользовательского сопоставления пространства имен и [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] управления версиями.</span><span class="sxs-lookup"><span data-stu-id="9830a-104">The `mc:Ignorable` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage-single-prefix"></a><span data-ttu-id="9830a-105">Использование атрибута XAML (один префикс)</span><span class="sxs-lookup"><span data-stu-id="9830a-105">XAML Attribute Usage (Single Prefix)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a><span data-ttu-id="9830a-106">Использование атрибута XAML (два префикса)</span><span class="sxs-lookup"><span data-stu-id="9830a-106">XAML Attribute Usage (Two Prefixes)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="9830a-107">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="9830a-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9830a-108">*ignorablePrefix, ignorablePrefix1 и т. д.*</span><span class="sxs-lookup"><span data-stu-id="9830a-108">*ignorablePrefix, ignorablePrefix1, etc.*</span></span>|<span data-ttu-id="9830a-109">Любая строка допустимый префикс, в соответствии со спецификацией XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="9830a-109">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="9830a-110">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="9830a-110">*ignorableUri*</span></span>|<span data-ttu-id="9830a-111">Любой допустимый URI для назначения пространства имен, в соответствии со спецификацией XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="9830a-111">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="9830a-112">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="9830a-112">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="9830a-113">Элемент, который может игнорироваться [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] реализации процессора, если не удается разрешить базовый тип.</span><span class="sxs-lookup"><span data-stu-id="9830a-113">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9830a-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="9830a-114">Remarks</span></span>  
 <span data-ttu-id="9830a-115">`mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Префикс пространства имен — соглашение рекомендуемый префикс, который используется для сопоставления [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] имен совместимости [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9830a-115">The `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefix is the recommended prefix convention to use when mapping the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compatibility namespace [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].</span></span>  
  
 <span data-ttu-id="9830a-116">Элементы или атрибуты, где префиксная часть имени элемента определяется как `mc:Ignorable` не создают ошибок при обработке [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора.</span><span class="sxs-lookup"><span data-stu-id="9830a-116">Elements or attributes where the prefix portion of the element name are identified as `mc:Ignorable` will not raise errors when processed by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="9830a-117">Если этот атрибут не может быть разрешена для базового типа или программных конструкций, этот элемент игнорируется.</span><span class="sxs-lookup"><span data-stu-id="9830a-117">If that attribute could not be resolved to an underlying type or programming construct, then that element is ignored.</span></span> <span data-ttu-id="9830a-118">Обратите внимание, что пропущенные элементы по-прежнему может создавать дополнительные синтаксические ошибки для дополнительных требований к элементу, побочные эффекты этого элемента не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="9830a-118">Note however that ignored elements might still generate additional parsing errors for additional element requirements that are side effects of that element not being processed.</span></span> <span data-ttu-id="9830a-119">Для экземпляра конкретный элемент содержимого модели может потребоваться только один дочерний элемент, но если указанный дочерний элемент был с `mc:Ignorable` префикс и указанный дочерний элемент не удалось разрешить тип, то [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] может процессора Возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="9830a-119">For instance, a particular element content model might require exactly one child element, but if the specified child element was in an `mc:Ignorable` prefix, and the specified child element could not be resolved to a type, then the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor might raise an error.</span></span>  
  
 <span data-ttu-id="9830a-120">`mc:Ignorable` применяется только для сопоставления пространства имен с идентификатором строки.</span><span class="sxs-lookup"><span data-stu-id="9830a-120">`mc:Ignorable` only applies to namespace mappings to identifier strings.</span></span> <span data-ttu-id="9830a-121">`mc:Ignorable` не применяется для сопоставления пространства имен в сборках, указывающих [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] пространства имен и сборки (или по умолчанию для текущего исполняемого файла в качестве сборки).</span><span class="sxs-lookup"><span data-stu-id="9830a-121">`mc:Ignorable` does not apply to namespace mappings into assemblies, which specify a [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] namespace and an assembly (or default to the current executable as the assembly).</span></span>  
  
 <span data-ttu-id="9830a-122">Если вы реализуете [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора, не должны вызывать реализация обработчика, синтаксического анализа и обработки ошибок при приведении типа любого элемента или атрибута, которые уточняются префикс, который определяется как `mc:Ignorable`.</span><span class="sxs-lookup"><span data-stu-id="9830a-122">If you are implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor, your processor implementation must not raise parsing or processing errors on type resolution for any element or attribute that is qualified by a prefix that is identified as `mc:Ignorable`.</span></span> <span data-ttu-id="9830a-123">Но реализация процессора по-прежнему может вызывать исключения, которые являются побочным результатом сбоя загрузки или обработки, такие как в приведенном выше примере одного дочернего элемента элемента.</span><span class="sxs-lookup"><span data-stu-id="9830a-123">But your processor implementation can still raise exceptions that are a secondary result of an element failing to load or be processed, such as the one-child element example given earlier.</span></span>  
  
 <span data-ttu-id="9830a-124">По умолчанию [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора будет игнорировать содержимое внутри игнорируемого элемента.</span><span class="sxs-lookup"><span data-stu-id="9830a-124">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="9830a-125">Тем не менее, можно указать дополнительный атрибут, [mc: ProcessContent атрибута](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md), для продолжения обработки содержимого в пределах игнорируемого элемента следующим доступным родительским элементом.</span><span class="sxs-lookup"><span data-stu-id="9830a-125">However, you can specify an additional attribute, [mc:ProcessContent Attribute](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md), to require continued processing of content within an ignored element by the next available parent element.</span></span>  
  
 <span data-ttu-id="9830a-126">Несколько префиксов, которые можно указать в атрибуте, используя один или несколько знаков пробела в качестве разделителя, например: `mc:Ignorable="ignore1 ignore2"`.</span><span class="sxs-lookup"><span data-stu-id="9830a-126">Multiple prefixes can be specified in the attribute, using one or more whitespace characters as the separator, for example: `mc:Ignorable="ignore1 ignore2"`.</span></span>  
  
 <span data-ttu-id="9830a-127">[!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] Пространство имен определяет другие элементы и атрибуты, которые не описаны в этой области [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9830a-127">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span></span> <span data-ttu-id="9830a-128">Дополнительные сведения см. в разделе [спецификация совместимости разметки XML](http://go.microsoft.com/fwlink/?LinkId=73824).</span><span class="sxs-lookup"><span data-stu-id="9830a-128">For more information, see [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9830a-129">См. также</span><span class="sxs-lookup"><span data-stu-id="9830a-129">See Also</span></span>  
 <xref:System.Windows.Markup.XamlReader>  
 [<span data-ttu-id="9830a-130">Атрибут PresentationOptions: Freeze</span><span class="sxs-lookup"><span data-stu-id="9830a-130">PresentationOptions:Freeze Attribute</span></span>](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)  
 [<span data-ttu-id="9830a-131">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="9830a-131">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="9830a-132">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="9830a-132">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
