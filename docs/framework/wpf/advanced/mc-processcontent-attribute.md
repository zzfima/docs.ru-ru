---
title: Атрибут mc:ProcessContent
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: bc406659bec3fd8d5da87b597356a3411c7a2605
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567398"
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="9365d-102">Атрибут mc:ProcessContent</span><span class="sxs-lookup"><span data-stu-id="9365d-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="9365d-103">Указывает, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] какие элементы по-прежнему должны обрабатываться соответствующими родительскими элементами, даже если непосредственный родительский элемент может [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] игнорироваться процессором из-за указания [MC: Ignorable атрибута](mc-ignorable-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="9365d-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](mc-ignorable-attribute.md).</span></span> <span data-ttu-id="9365d-104">Атрибут поддерживает совместимость разметки как для пользовательского сопоставления пространства имен, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] так и для управления версиями. `mc:ProcessContent`</span><span class="sxs-lookup"><span data-stu-id="9365d-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="9365d-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="9365d-105">XAML Attribute Usage</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...  
  mc:ProcessContent="ignorablePrefix:ThisElementCanBeIgnored"  
>  
    <ignorablePrefix:ThisElementCanBeIgnored>  
        [content]  
    </ignorablePrefix:ThisElementCanBeIgnored>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="9365d-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="9365d-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9365d-107">*игнораблепрефикс*</span><span class="sxs-lookup"><span data-stu-id="9365d-107">*ignorablePrefix*</span></span>|<span data-ttu-id="9365d-108">Любая допустимая строка префикса, согласно спецификации XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="9365d-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="9365d-109">*игнораблеури*</span><span class="sxs-lookup"><span data-stu-id="9365d-109">*ignorableUri*</span></span>|<span data-ttu-id="9365d-110">Любой допустимый URI для обозначения пространства имен в соответствии с спецификацией XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="9365d-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="9365d-111">*сиселементканбеигноред*</span><span class="sxs-lookup"><span data-stu-id="9365d-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="9365d-112">Элемент, который может игнорироваться [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] реализациями процессора, если базовый тип не может быть разрешен.</span><span class="sxs-lookup"><span data-stu-id="9365d-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="9365d-113">*содержани*</span><span class="sxs-lookup"><span data-stu-id="9365d-113">*[content]*</span></span>|<span data-ttu-id="9365d-114">*Сиселементканбеигноред* помечен как Ignorable.</span><span class="sxs-lookup"><span data-stu-id="9365d-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="9365d-115">Если процессор не обрабатывает этот элемент, *[content]* обрабатывается *объектом*.</span><span class="sxs-lookup"><span data-stu-id="9365d-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9365d-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="9365d-116">Remarks</span></span>  
 <span data-ttu-id="9365d-117">По умолчанию [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессор будет игнорировать содержимое внутри игнорируемого элемента.</span><span class="sxs-lookup"><span data-stu-id="9365d-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="9365d-118">Можно указать конкретный элемент с помощью `mc:ProcessContent`, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] а процессор продолжит обрабатывать содержимое внутри элемента, пропускаемого пропуском.</span><span class="sxs-lookup"><span data-stu-id="9365d-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="9365d-119">Обычно это используется, если содержимое вложено в несколько тегов, по крайней мере один из которых является игнорируемым и по крайней мере один из которых не может быть проигнорирован.</span><span class="sxs-lookup"><span data-stu-id="9365d-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="9365d-120">В атрибуте можно указать несколько префиксов, используя разделитель пробелов, например: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span><span class="sxs-lookup"><span data-stu-id="9365d-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="9365d-121">[!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] Пространство имен определяет другие элементы и атрибуты, не описанные в этой области пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="9365d-121">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the SDK.</span></span> <span data-ttu-id="9365d-122">Дополнительные сведения см. в разделе [Спецификация совместимости XML-разметки](https://go.microsoft.com/fwlink/?LinkId=73824).</span><span class="sxs-lookup"><span data-stu-id="9365d-122">For more information, see [XML Markup Compatibility Specification](https://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9365d-123">См. также</span><span class="sxs-lookup"><span data-stu-id="9365d-123">See also</span></span>

- [<span data-ttu-id="9365d-124">Атрибут mc: Ignorable</span><span class="sxs-lookup"><span data-stu-id="9365d-124">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
- [<span data-ttu-id="9365d-125">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="9365d-125">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
