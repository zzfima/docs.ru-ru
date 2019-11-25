---
title: Расширение разметки TemplateBinding
ms.date: 03/30/2017
f1_keywords:
- TemplateBinding
- TemplateBindingExtension
helpviewer_keywords:
- XAML [WPF], TemplateBinding markup extension
- TemplateBinding markup extensions [WPF]
ms.assetid: 1d25bbfc-dbc2-499d-9f12-419d23d4ac6a
ms.openlocfilehash: 6d89978b907c8f124b5162c97de5edc034cf1e95
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976674"
---
# <a name="templatebinding-markup-extension"></a><span data-ttu-id="69780-102">Расширение разметки TemplateBinding</span><span class="sxs-lookup"><span data-stu-id="69780-102">TemplateBinding Markup Extension</span></span>
<span data-ttu-id="69780-103">Связывает значение свойства в шаблоне элемента управления со значением другого свойства элемента управления-шаблона.</span><span class="sxs-lookup"><span data-stu-id="69780-103">Links the value of a property in a control template to be the value of another property on the templated control.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="69780-104">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="69780-104">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-attribute-usage-for-setter-property-in-template-or-style"></a><span data-ttu-id="69780-105">Использование атрибута XAML (для свойства Setter в шаблоне или стиле)</span><span class="sxs-lookup"><span data-stu-id="69780-105">XAML Attribute Usage (for Setter property in template or style)</span></span>  
  
```xml  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="69780-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="69780-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`propertyName`|<span data-ttu-id="69780-107"><xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> для свойства задается в синтаксисе метода задания значения.</span><span class="sxs-lookup"><span data-stu-id="69780-107"><xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> of the property being set in the setter syntax.</span></span>|  
|`sourceProperty`|<span data-ttu-id="69780-108">Другое свойство зависимостей для типа, который используется в качестве шаблона, задается с помощью <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="69780-108">Another dependency property that exists on the type being templated, specified by its <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.</span></span><br /><br /> <span data-ttu-id="69780-109">-или-</span><span class="sxs-lookup"><span data-stu-id="69780-109">- or -</span></span><br /><br /> <span data-ttu-id="69780-110">"Краткое" имя свойства, которое определяется типом, отличным от целевого шаблонного типа.</span><span class="sxs-lookup"><span data-stu-id="69780-110">A "dotted-down" property name that is defined by a different type than the target type being templated.</span></span> <span data-ttu-id="69780-111">Фактически это <xref:System.Windows.PropertyPath>.</span><span class="sxs-lookup"><span data-stu-id="69780-111">This is actually a <xref:System.Windows.PropertyPath>.</span></span> <span data-ttu-id="69780-112">См. раздел [синтаксис языка XAML PropertyPath](propertypath-xaml-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="69780-112">See [PropertyPath XAML Syntax](propertypath-xaml-syntax.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69780-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="69780-113">Remarks</span></span>  
 <span data-ttu-id="69780-114">`TemplateBinding` — это оптимизированная форма [привязки](binding-markup-extension.md) для сценариев шаблонов, аналогичная `Binding`, созданной с помощью `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=OneWay}`.</span><span class="sxs-lookup"><span data-stu-id="69780-114">A `TemplateBinding` is an optimized form of a [Binding](binding-markup-extension.md) for template scenarios, analogous to a `Binding` constructed with `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=OneWay}`.</span></span> <span data-ttu-id="69780-115">`TemplateBinding` всегда является односторонней привязкой, даже если используемые свойства по умолчанию используют двустороннюю привязку.</span><span class="sxs-lookup"><span data-stu-id="69780-115">A `TemplateBinding` is always a one-way binding, even if properties involved default to two-way binding.</span></span> <span data-ttu-id="69780-116">Оба используемых свойства должны быть свойствами зависимостей.</span><span class="sxs-lookup"><span data-stu-id="69780-116">Both properties involved must be dependency properties.</span></span> <span data-ttu-id="69780-117">Чтобы обеспечить двустороннюю привязку к шаблонному родителю, вместо этого используйте следующую инструкцию привязки `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`.</span><span class="sxs-lookup"><span data-stu-id="69780-117">In order to achieve two-way binding to a templated parent use the following binding statement instead `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`.</span></span> 
  
 <span data-ttu-id="69780-118">[RelativeSource](relativesource-markupextension.md) — это еще одно расширение разметки, которое иногда используется вместе с или вместо `TemplateBinding` для выполнения относительной привязки свойства в шаблоне.</span><span class="sxs-lookup"><span data-stu-id="69780-118">[RelativeSource](relativesource-markupextension.md) is another markup extension that is sometimes used in conjunction with or instead of `TemplateBinding` in order to perform relative property binding within a template.</span></span>  
  
 <span data-ttu-id="69780-119">Описание шаблонов элементов управления в качестве концепции не рассматривается здесь. Дополнительные сведения см. в разделе [стили и шаблоны элемента управления](../controls/control-styles-and-templates.md).</span><span class="sxs-lookup"><span data-stu-id="69780-119">Describing control templates as a concept is not covered here; for more information, see [Control Styles and Templates](../controls/control-styles-and-templates.md).</span></span>  
  
 <span data-ttu-id="69780-120">Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="69780-120">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="69780-121">Строковая лексема, указываемая после строки идентификатора `TemplateBinding`, присваивается в качестве значения <xref:System.Windows.TemplateBindingExtension.Property%2A> соответствующего класса расширения <xref:System.Windows.TemplateBindingExtension>.</span><span class="sxs-lookup"><span data-stu-id="69780-121">The string token provided after the `TemplateBinding` identifier string is assigned as the <xref:System.Windows.TemplateBindingExtension.Property%2A> value of the underlying <xref:System.Windows.TemplateBindingExtension> extension class.</span></span>  
  
 <span data-ttu-id="69780-122">Синтаксис элемента объекта возможен, но он не рассматривается из-за отсутствия практического применения.</span><span class="sxs-lookup"><span data-stu-id="69780-122">Object element syntax is possible, but it is not shown because it has no realistic application.</span></span> <span data-ttu-id="69780-123">`TemplateBinding` используется для заполнения значений в методах установки значений с помощью вычисленных выражений. Использование синтаксиса элемента объекта для `TemplateBinding` для заполнения синтаксиса элемента свойства `<Setter.Property>` является излишним.</span><span class="sxs-lookup"><span data-stu-id="69780-123">`TemplateBinding` is used to fill values within setters, using evaluated expressions, and using object element syntax for `TemplateBinding` to fill `<Setter.Property>` property element syntax is unnecessarily verbose.</span></span>  
  
 <span data-ttu-id="69780-124">Излишним может оказаться и использование `TemplateBinding` в атрибуте, в котором свойство <xref:System.Windows.TemplateBindingExtension.Property%2A> определено как пара "свойство=значение".</span><span class="sxs-lookup"><span data-stu-id="69780-124">`TemplateBinding` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.TemplateBindingExtension.Property%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 <span data-ttu-id="69780-125">Подробное определение зачастую удобно использовать для расширений, которые имеют несколько устанавливаемых свойств, а также в том случае, если некоторые свойства являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="69780-125">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="69780-126">Так как `TemplateBinding` имеет только одно устанавливаемое свойство, которое является обязательным, это использование не является типичным.</span><span class="sxs-lookup"><span data-stu-id="69780-126">Because `TemplateBinding` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="69780-127">В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализации процессора XAML обработка этого расширения разметки определяется классом <xref:System.Windows.TemplateBindingExtension>.</span><span class="sxs-lookup"><span data-stu-id="69780-127">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.TemplateBindingExtension> class.</span></span>  
  
 <span data-ttu-id="69780-128">`TemplateBinding` является расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="69780-128">`TemplateBinding` is a markup extension.</span></span> <span data-ttu-id="69780-129">Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами.</span><span class="sxs-lookup"><span data-stu-id="69780-129">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="69780-130">Все расширения разметки в XAML используют `{` и `}` символов в синтаксисе атрибутов, который является соглашением, по которому обработчик XAML распознает, что расширение разметки должно обработать атрибут.</span><span class="sxs-lookup"><span data-stu-id="69780-130">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="69780-131">Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="69780-131">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69780-132">См. также</span><span class="sxs-lookup"><span data-stu-id="69780-132">See also</span></span>

- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="69780-133">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="69780-133">Styling and Templating</span></span>](../controls/styling-and-templating.md)
- [<span data-ttu-id="69780-134">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="69780-134">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="69780-135">Расширения разметки и XAML WPF</span><span class="sxs-lookup"><span data-stu-id="69780-135">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="69780-136">Расширение разметки RelativeSource</span><span class="sxs-lookup"><span data-stu-id="69780-136">RelativeSource MarkupExtension</span></span>](relativesource-markupextension.md)
- [<span data-ttu-id="69780-137">Привязка расширения разметки</span><span class="sxs-lookup"><span data-stu-id="69780-137">Binding Markup Extension</span></span>](binding-markup-extension.md)
