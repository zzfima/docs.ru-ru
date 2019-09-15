---
title: Атрибут mc:ProcessContent
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: e625d99cdb30368a798b4829d103f8f26b2c9274
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991854"
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="a2f86-102">Атрибут mc:ProcessContent</span><span class="sxs-lookup"><span data-stu-id="a2f86-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="a2f86-103">Указывает, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] какие элементы по-прежнему должны обрабатываться соответствующими родительскими элементами, даже если непосредственный родительский элемент может [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] игнорироваться процессором из-за указания [MC: Ignorable атрибута](mc-ignorable-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="a2f86-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](mc-ignorable-attribute.md).</span></span> <span data-ttu-id="a2f86-104">Атрибут поддерживает совместимость разметки как для пользовательского сопоставления пространства имен, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] так и для управления версиями. `mc:ProcessContent`</span><span class="sxs-lookup"><span data-stu-id="a2f86-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="a2f86-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="a2f86-105">XAML Attribute Usage</span></span>  
  
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
  
## <a name="xaml-values"></a><span data-ttu-id="a2f86-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="a2f86-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a2f86-107">*игнораблепрефикс*</span><span class="sxs-lookup"><span data-stu-id="a2f86-107">*ignorablePrefix*</span></span>|<span data-ttu-id="a2f86-108">Любая допустимая строка префикса, согласно спецификации XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="a2f86-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="a2f86-109">*игнораблеури*</span><span class="sxs-lookup"><span data-stu-id="a2f86-109">*ignorableUri*</span></span>|<span data-ttu-id="a2f86-110">Любой допустимый URI для обозначения пространства имен в соответствии с спецификацией XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="a2f86-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="a2f86-111">*сиселементканбеигноред*</span><span class="sxs-lookup"><span data-stu-id="a2f86-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="a2f86-112">Элемент, который может игнорироваться [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] реализациями процессора, если базовый тип не может быть разрешен.</span><span class="sxs-lookup"><span data-stu-id="a2f86-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="a2f86-113">*содержани*</span><span class="sxs-lookup"><span data-stu-id="a2f86-113">*[content]*</span></span>|<span data-ttu-id="a2f86-114">*Сиселементканбеигноред* помечен как Ignorable.</span><span class="sxs-lookup"><span data-stu-id="a2f86-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="a2f86-115">Если процессор не обрабатывает этот элемент, *[content]* обрабатывается *объектом*.</span><span class="sxs-lookup"><span data-stu-id="a2f86-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2f86-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="a2f86-116">Remarks</span></span>  
 <span data-ttu-id="a2f86-117">По умолчанию [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессор будет игнорировать содержимое внутри игнорируемого элемента.</span><span class="sxs-lookup"><span data-stu-id="a2f86-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="a2f86-118">Можно указать конкретный элемент с помощью `mc:ProcessContent`, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] а процессор продолжит обрабатывать содержимое внутри элемента, пропускаемого пропуском.</span><span class="sxs-lookup"><span data-stu-id="a2f86-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="a2f86-119">Обычно это используется, если содержимое вложено в несколько тегов, по крайней мере один из которых является игнорируемым и по крайней мере один из которых не может быть проигнорирован.</span><span class="sxs-lookup"><span data-stu-id="a2f86-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="a2f86-120">В атрибуте можно указать несколько префиксов, используя разделитель пробелов, например: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span><span class="sxs-lookup"><span data-stu-id="a2f86-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="a2f86-121">`http://schemas.openxmlformats.org/markup-compatibility/2006` Пространство имен определяет другие элементы и атрибуты, не описанные в этой области пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="a2f86-121">The `http://schemas.openxmlformats.org/markup-compatibility/2006` namespace defines other elements and attributes that are not documented within this area of the SDK.</span></span> <span data-ttu-id="a2f86-122">Дополнительные сведения см. в разделе [Спецификация совместимости XML-разметки](https://go.microsoft.com/fwlink/?LinkId=73824).</span><span class="sxs-lookup"><span data-stu-id="a2f86-122">For more information, see [XML Markup Compatibility Specification](https://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2f86-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a2f86-123">See also</span></span>

- [<span data-ttu-id="a2f86-124">Атрибут mc: Ignorable</span><span class="sxs-lookup"><span data-stu-id="a2f86-124">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
- [<span data-ttu-id="a2f86-125">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="a2f86-125">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
