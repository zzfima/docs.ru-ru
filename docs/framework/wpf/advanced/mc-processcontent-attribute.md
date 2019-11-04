---
title: Атрибут mc:ProcessContent
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: dde304cc2b9db9cb01f9264ca1359b8979512cfa
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458780"
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="79abb-102">Атрибут mc:ProcessContent</span><span class="sxs-lookup"><span data-stu-id="79abb-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="79abb-103">Указывает, какие элементы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] должны по-прежнему обрабатываться соответствующими родительскими элементами, даже если непосредственный родительский элемент может игнорироваться процессором [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], так как указан [атрибут MC: Ignorable](mc-ignorable-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="79abb-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](mc-ignorable-attribute.md).</span></span> <span data-ttu-id="79abb-104">Атрибут `mc:ProcessContent` поддерживает совместимость разметки как для пользовательского сопоставления пространства имен, так и для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] управления версиями.</span><span class="sxs-lookup"><span data-stu-id="79abb-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="79abb-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="79abb-105">XAML Attribute Usage</span></span>  
  
```xaml  
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
  
## <a name="xaml-values"></a><span data-ttu-id="79abb-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="79abb-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="79abb-107">*игнораблепрефикс*</span><span class="sxs-lookup"><span data-stu-id="79abb-107">*ignorablePrefix*</span></span>|<span data-ttu-id="79abb-108">Любая допустимая строка префикса, согласно спецификации XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="79abb-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="79abb-109">*игнораблеури*</span><span class="sxs-lookup"><span data-stu-id="79abb-109">*ignorableUri*</span></span>|<span data-ttu-id="79abb-110">Любой допустимый URI для обозначения пространства имен в соответствии с спецификацией XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="79abb-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="79abb-111">*сиселементканбеигноред*</span><span class="sxs-lookup"><span data-stu-id="79abb-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="79abb-112">Элемент, который можно игнорировать с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] реализаций процессора, если базовый тип не может быть разрешен.</span><span class="sxs-lookup"><span data-stu-id="79abb-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="79abb-113">*содержани*</span><span class="sxs-lookup"><span data-stu-id="79abb-113">*[content]*</span></span>|<span data-ttu-id="79abb-114">*Сиселементканбеигноред* помечен как Ignorable.</span><span class="sxs-lookup"><span data-stu-id="79abb-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="79abb-115">Если процессор не обрабатывает этот элемент, *[content]* обрабатывается *объектом*.</span><span class="sxs-lookup"><span data-stu-id="79abb-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79abb-116">Заметки</span><span class="sxs-lookup"><span data-stu-id="79abb-116">Remarks</span></span>  
 <span data-ttu-id="79abb-117">По умолчанию обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] будет игнорировать содержимое в игнорируемом элементе.</span><span class="sxs-lookup"><span data-stu-id="79abb-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="79abb-118">Вы можете указать конкретный элемент, `mc:ProcessContent`, а процессор [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] продолжит обрабатывать содержимое внутри элемента, пропускаемого пропуском.</span><span class="sxs-lookup"><span data-stu-id="79abb-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="79abb-119">Обычно это используется, если содержимое вложено в несколько тегов, по крайней мере один из которых является игнорируемым и по крайней мере один из которых не может быть проигнорирован.</span><span class="sxs-lookup"><span data-stu-id="79abb-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="79abb-120">В атрибуте можно указать несколько префиксов, используя разделитель пробелов, например: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span><span class="sxs-lookup"><span data-stu-id="79abb-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="79abb-121">Пространство имен `http://schemas.openxmlformats.org/markup-compatibility/2006` определяет другие элементы и атрибуты, не описанные в этой области пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="79abb-121">The `http://schemas.openxmlformats.org/markup-compatibility/2006` namespace defines other elements and attributes that are not documented within this area of the SDK.</span></span> <span data-ttu-id="79abb-122">Дополнительные сведения см. в разделе [Спецификация совместимости XML-разметки](https://go.microsoft.com/fwlink/?LinkId=73824).</span><span class="sxs-lookup"><span data-stu-id="79abb-122">For more information, see [XML Markup Compatibility Specification](https://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79abb-123">См. также</span><span class="sxs-lookup"><span data-stu-id="79abb-123">See also</span></span>

- [<span data-ttu-id="79abb-124">Атрибут mc: Ignorable</span><span class="sxs-lookup"><span data-stu-id="79abb-124">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
- [<span data-ttu-id="79abb-125">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="79abb-125">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
