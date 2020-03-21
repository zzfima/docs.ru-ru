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
ms.openlocfilehash: 8cebbf717f66b072bc84b2068193ff2fe76ea87b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187280"
---
# <a name="templatebinding-markup-extension"></a><span data-ttu-id="3bb9a-102">Расширение разметки TemplateBinding</span><span class="sxs-lookup"><span data-stu-id="3bb9a-102">TemplateBinding Markup Extension</span></span>
<span data-ttu-id="3bb9a-103">Связывает значение свойства в шаблоне элемента управления со значением другого свойства элемента управления-шаблона.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-103">Links the value of a property in a control template to be the value of another property on the templated control.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="3bb9a-104">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="3bb9a-104">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-attribute-usage-for-setter-property-in-template-or-style"></a><span data-ttu-id="3bb9a-105">Использование атрибута XAML (для свойства Setter в шаблоне или стиле)</span><span class="sxs-lookup"><span data-stu-id="3bb9a-105">XAML Attribute Usage (for Setter property in template or style)</span></span>  
  
```xml  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="3bb9a-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="3bb9a-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`propertyName`|<span data-ttu-id="3bb9a-107"><xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> для свойства задается в синтаксисе метода задания значения.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-107"><xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> of the property being set in the setter syntax.</span></span>|  
|`sourceProperty`|<span data-ttu-id="3bb9a-108">Другое свойство зависимостей для типа, который используется в качестве шаблона, задается с помощью <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-108">Another dependency property that exists on the type being templated, specified by its <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.</span></span><br /><br /> <span data-ttu-id="3bb9a-109">— или —</span><span class="sxs-lookup"><span data-stu-id="3bb9a-109">- or -</span></span><br /><br /> <span data-ttu-id="3bb9a-110">"Краткое" имя свойства, которое определяется типом, отличным от целевого шаблонного типа.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-110">A "dotted-down" property name that is defined by a different type than the target type being templated.</span></span> <span data-ttu-id="3bb9a-111">Фактически это <xref:System.Windows.PropertyPath>.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-111">This is actually a <xref:System.Windows.PropertyPath>.</span></span> <span data-ttu-id="3bb9a-112">Смотрите [PropertyPath XAML Syntax](propertypath-xaml-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="3bb9a-112">See [PropertyPath XAML Syntax](propertypath-xaml-syntax.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3bb9a-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="3bb9a-113">Remarks</span></span>  
 <span data-ttu-id="3bb9a-114">A `TemplateBinding` — это оптимизированная форма [связывания](binding-markup-extension.md) `Binding` для шаблонных сценариев, аналогичная построенной с `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=OneWay}`помощью .</span><span class="sxs-lookup"><span data-stu-id="3bb9a-114">A `TemplateBinding` is an optimized form of a [Binding](binding-markup-extension.md) for template scenarios, analogous to a `Binding` constructed with `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=OneWay}`.</span></span> <span data-ttu-id="3bb9a-115">`TemplateBinding` всегда является односторонней привязкой, даже если используемые свойства по умолчанию используют двустороннюю привязку.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-115">A `TemplateBinding` is always a one-way binding, even if properties involved default to two-way binding.</span></span> <span data-ttu-id="3bb9a-116">Оба используемых свойства должны быть свойствами зависимостей.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-116">Both properties involved must be dependency properties.</span></span> <span data-ttu-id="3bb9a-117">Для достижения двусторонней привязки к шаблону родителя `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`используйте следующее обязательное заявление вместо этого.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-117">In order to achieve two-way binding to a templated parent use the following binding statement instead `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`.</span></span>
  
 <span data-ttu-id="3bb9a-118">[RelativeSource](relativesource-markupextension.md) — это еще одно расширение разметки, которое иногда используется в сочетании с или вместо `TemplateBinding` этого для выполнения относительной связывания свойств в шаблоне.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-118">[RelativeSource](relativesource-markupextension.md) is another markup extension that is sometimes used in conjunction with or instead of `TemplateBinding` in order to perform relative property binding within a template.</span></span>  
  
 <span data-ttu-id="3bb9a-119">Описание шаблонов управления как концепции здесь не рассматривается; для получения дополнительной [информации, см.](../controls/control-styles-and-templates.md)</span><span class="sxs-lookup"><span data-stu-id="3bb9a-119">Describing control templates as a concept is not covered here; for more information, see [Control Styles and Templates](../controls/control-styles-and-templates.md).</span></span>  
  
 <span data-ttu-id="3bb9a-120">Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-120">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="3bb9a-121">Строковая лексема, указываемая после строки идентификатора `TemplateBinding`, присваивается в качестве значения <xref:System.Windows.TemplateBindingExtension.Property%2A> соответствующего класса расширения <xref:System.Windows.TemplateBindingExtension>.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-121">The string token provided after the `TemplateBinding` identifier string is assigned as the <xref:System.Windows.TemplateBindingExtension.Property%2A> value of the underlying <xref:System.Windows.TemplateBindingExtension> extension class.</span></span>  
  
 <span data-ttu-id="3bb9a-122">Синтаксис элемента объекта возможен, но он не рассматривается из-за отсутствия практического применения.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-122">Object element syntax is possible, but it is not shown because it has no realistic application.</span></span> <span data-ttu-id="3bb9a-123">`TemplateBinding` используется для заполнения значений в методах установки значений с помощью вычисленных выражений. Использование синтаксиса элемента объекта для `TemplateBinding` для заполнения синтаксиса элемента свойства `<Setter.Property>` является излишним.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-123">`TemplateBinding` is used to fill values within setters, using evaluated expressions, and using object element syntax for `TemplateBinding` to fill `<Setter.Property>` property element syntax is unnecessarily verbose.</span></span>  
  
 <span data-ttu-id="3bb9a-124">Излишним может оказаться и использование `TemplateBinding` в атрибуте, в котором свойство <xref:System.Windows.TemplateBindingExtension.Property%2A> определено как пара "свойство=значение".</span><span class="sxs-lookup"><span data-stu-id="3bb9a-124">`TemplateBinding` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.TemplateBindingExtension.Property%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 <span data-ttu-id="3bb9a-125">Подробное определение зачастую удобно использовать для расширений, которые имеют несколько устанавливаемых свойств, а также в том случае, если некоторые свойства являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-125">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="3bb9a-126">Так как `TemplateBinding` имеет только одно устанавливаемое свойство, которое является обязательным, это использование не является типичным.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-126">Because `TemplateBinding` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="3bb9a-127">В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализации процессора XAML обработка этого расширения <xref:System.Windows.TemplateBindingExtension> разметки определяется классом.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-127">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.TemplateBindingExtension> class.</span></span>  
  
 <span data-ttu-id="3bb9a-128">`TemplateBinding` является расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-128">`TemplateBinding` is a markup extension.</span></span> <span data-ttu-id="3bb9a-129">Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-129">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="3bb9a-130">Все расширения разметки в `{` XAML используют и `}` символы в их синтаксисе атрибута, который является конвенцией, с помощью которой процессор XAML признает, что расширение разметки должно обрабатывать атрибут.</span><span class="sxs-lookup"><span data-stu-id="3bb9a-130">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="3bb9a-131">Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="3bb9a-131">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bb9a-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3bb9a-132">See also</span></span>

- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="3bb9a-133">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="3bb9a-133">Styling and Templating</span></span>](../controls/styling-and-templating.md)
- [<span data-ttu-id="3bb9a-134">Обзор XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="3bb9a-134">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="3bb9a-135">Расширения разметки и XAML WPF</span><span class="sxs-lookup"><span data-stu-id="3bb9a-135">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="3bb9a-136">Расширение разметки RelativeSource</span><span class="sxs-lookup"><span data-stu-id="3bb9a-136">RelativeSource MarkupExtension</span></span>](relativesource-markupextension.md)
- [<span data-ttu-id="3bb9a-137">Привязка расширения разметки</span><span class="sxs-lookup"><span data-stu-id="3bb9a-137">Binding Markup Extension</span></span>](binding-markup-extension.md)
