---
title: Атрибут mc:ProcessContent
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: f7db71c065a04fb14216ffd08ca3b7c9d7cdf5af
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54673963"
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="00780-102">Атрибут mc:ProcessContent</span><span class="sxs-lookup"><span data-stu-id="00780-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="00780-103">Указывает, какие [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] элементы по-прежнему содержимое должно быть обрабатываемых соответствующих родительских элементов, даже если непосредственный родительский элемент может игнорировать [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора из-за указания [mc: Ignorable-атрибут](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) .</span><span class="sxs-lookup"><span data-stu-id="00780-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md).</span></span> <span data-ttu-id="00780-104">`mc:ProcessContent` Атрибут поддерживает совместимость разметки для пользовательского сопоставления пространства имен и [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] управления версиями.</span><span class="sxs-lookup"><span data-stu-id="00780-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="00780-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="00780-105">XAML Attribute Usage</span></span>  
  
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
  
## <a name="xaml-values"></a><span data-ttu-id="00780-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="00780-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="00780-107">*ignorablePrefix*</span><span class="sxs-lookup"><span data-stu-id="00780-107">*ignorablePrefix*</span></span>|<span data-ttu-id="00780-108">Любая строка допустимый префикс, согласно спецификации XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="00780-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="00780-109">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="00780-109">*ignorableUri*</span></span>|<span data-ttu-id="00780-110">Любой допустимый URI для назначения пространства имен, согласно спецификации XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="00780-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="00780-111">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="00780-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="00780-112">Элемент, который может обрабатываться средством [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] реализаций обработчиков, если базовый тип не может быть разрешена.</span><span class="sxs-lookup"><span data-stu-id="00780-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="00780-113">*[сведения]*</span><span class="sxs-lookup"><span data-stu-id="00780-113">*[content]*</span></span>|<span data-ttu-id="00780-114">*ThisElementCanBeIgnored* помечается как игнорируемый.</span><span class="sxs-lookup"><span data-stu-id="00780-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="00780-115">Если обработчик игнорирует этот элемент *[содержимое]* обрабатывается *объект*.</span><span class="sxs-lookup"><span data-stu-id="00780-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00780-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="00780-116">Remarks</span></span>  
 <span data-ttu-id="00780-117">По умолчанию [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора будет игнорировать содержимое внутри игнорируемого элемента.</span><span class="sxs-lookup"><span data-stu-id="00780-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="00780-118">Можно указать определенный элемент, `mc:ProcessContent`и [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессор будет продолжать обработку содержимого внутри игнорируемого элемента.</span><span class="sxs-lookup"><span data-stu-id="00780-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="00780-119">Это обычно будет использоваться, если содержимое является вложенной в несколько тегов, по крайней мере один из которых является игнорируемым и по крайней мере один из которых не является игнорируемым.</span><span class="sxs-lookup"><span data-stu-id="00780-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="00780-120">Несколько префиксов может быть указан в атрибуте, используя разделитель, например: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span><span class="sxs-lookup"><span data-stu-id="00780-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="00780-121">[!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] Пространство имен определяет другие элементы и атрибуты, которые не документированы в этой области [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00780-121">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span></span> <span data-ttu-id="00780-122">Дополнительные сведения см. в разделе [спецификации совместимости разметки XML](https://go.microsoft.com/fwlink/?LinkId=73824).</span><span class="sxs-lookup"><span data-stu-id="00780-122">For more information, see [XML Markup Compatibility Specification](https://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00780-123">См. также</span><span class="sxs-lookup"><span data-stu-id="00780-123">See also</span></span>
- [<span data-ttu-id="00780-124">Атрибут mc: Ignorable</span><span class="sxs-lookup"><span data-stu-id="00780-124">mc:Ignorable Attribute</span></span>](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)
- [<span data-ttu-id="00780-125">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="00780-125">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
