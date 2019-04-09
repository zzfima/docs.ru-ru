---
title: Расширение разметки StaticResource
ms.date: 03/30/2017
f1_keywords:
- StaticResource
- StaticResourceExtension
helpviewer_keywords:
- XAML [WPF], StaticResource markup extension
- StaticResource markup extensions [WPF]
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
ms.openlocfilehash: 8319e451268152e95326c02027157db72df631b8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125150"
---
# <a name="staticresource-markup-extension"></a><span data-ttu-id="33cbe-102">Расширение разметки StaticResource</span><span class="sxs-lookup"><span data-stu-id="33cbe-102">StaticResource Markup Extension</span></span>
<span data-ttu-id="33cbe-103">Предоставляет значение для любого [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] свойства атрибута, посмотрев на ссылку на уже заданного ресурса.</span><span class="sxs-lookup"><span data-stu-id="33cbe-103">Provides a value for any [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] property attribute by looking up a reference to an already defined resource.</span></span> <span data-ttu-id="33cbe-104">Поведение подстановки для этого ресурса аналогичен во время загрузки, который будет искать ресурсы, которые были ранее загружены из разметки текущего [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] странице, а также других источников приложения и автоматически создаст значение ресурсов как значение свойства в объектах во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="33cbe-104">Lookup behavior for that resource is analogous to load-time lookup, which will look for resources that were previously loaded from the markup of the current [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page as well as other application sources, and will generate that resource value as the property value in the run-time objects.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="33cbe-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="33cbe-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{StaticResource key}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="33cbe-106">Использование элемента объекта XAML</span><span class="sxs-lookup"><span data-stu-id="33cbe-106">XAML Object Element Usage</span></span>  
  
```xml  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="33cbe-107">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="33cbe-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`key`|<span data-ttu-id="33cbe-108">Ключ для запрашиваемого ресурса.</span><span class="sxs-lookup"><span data-stu-id="33cbe-108">The key for the requested resource.</span></span> <span data-ttu-id="33cbe-109">Этот ключ была изначально назначена по [директивы x: Key](../../xaml-services/x-key-directive.md) Если ресурс был создан в разметке или был предоставлен в виде `key` параметра при вызове <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> Если ресурс был создан в коде.</span><span class="sxs-lookup"><span data-stu-id="33cbe-109">This key was initially assigned by the [x:Key Directive](../../xaml-services/x-key-directive.md) if a resource was created in markup, or was provided as the `key` parameter when calling <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> if the resource was created in code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33cbe-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="33cbe-110">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="33cbe-111">Объект `StaticResource` не следует пытаться сделать прямую ссылку на ресурс, определенный лексически далее в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл.</span><span class="sxs-lookup"><span data-stu-id="33cbe-111">A `StaticResource` must not attempt to make a forward reference to a resource that is defined lexically further within the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="33cbe-112">Попытка выполнить такую операцию не поддерживается, и даже если эта ссылка не произойдет сбой, попытка прямой ссылки повлечет снижение производительности во время загрузки при внутренней хэш-таблиц, представляющих <xref:System.Windows.ResourceDictionary> производится поиск.</span><span class="sxs-lookup"><span data-stu-id="33cbe-112">Attempting to do so is not supported, and even if such a reference does not fail, attempting the forward reference will incur a load time performance penalty when the internal hash tables representing a <xref:System.Windows.ResourceDictionary> are searched.</span></span> <span data-ttu-id="33cbe-113">Для получения наилучших результатов настройте композицию словарей ресурсов таким образом, что можно избежать прямых ссылок.</span><span class="sxs-lookup"><span data-stu-id="33cbe-113">For best results, adjust the composition of your resource dictionaries such that forward references can be avoided.</span></span> <span data-ttu-id="33cbe-114">Если не удается избежать опережающие ссылки, используйте [расширение разметки DynamicResource](dynamicresource-markup-extension.md) вместо этого.</span><span class="sxs-lookup"><span data-stu-id="33cbe-114">If you cannot avoid a forward reference, use [DynamicResource Markup Extension](dynamicresource-markup-extension.md) instead.</span></span>  
  
 <span data-ttu-id="33cbe-115">Указанный <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> должен соответствовать имеющийся ресурс, определенный с помощью [директивы x: Key](../../xaml-services/x-key-directive.md) на определенном уровне страницы, приложения, доступный элемент управления темы и внешним ресурсам или системных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="33cbe-115">The specified <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> should correspond to an existing resource, identified with an [x:Key Directive](../../xaml-services/x-key-directive.md) at some level in your page, application, the available control themes and external resources, or system resources.</span></span> <span data-ttu-id="33cbe-116">Поиск ресурсов происходит в указанном порядке.</span><span class="sxs-lookup"><span data-stu-id="33cbe-116">The resource lookup occurs in that order.</span></span> <span data-ttu-id="33cbe-117">Дополнительные сведения о поведение подстановки ресурса для статических и динамических ресурсов, см. в разделе [ресурсы XAML](xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="33cbe-117">For more information about resource lookup behavior for static and dynamic resources, see [XAML Resources](xaml-resources.md).</span></span>  
  
 <span data-ttu-id="33cbe-118">Ключ ресурса может быть любой строкой, определенные в [Грамматика XamlName](../../xaml-services/xamlname-grammar.md).</span><span class="sxs-lookup"><span data-stu-id="33cbe-118">A resource key can be any string defined in the [XamlName Grammar](../../xaml-services/xamlname-grammar.md).</span></span> <span data-ttu-id="33cbe-119">Ключ ресурса также может быть других типов объектов, таких как <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="33cbe-119">A resource key can also be other object types, such as a <xref:System.Type>.</span></span> <span data-ttu-id="33cbe-120">Объект <xref:System.Type> ключ — это основа для элементов управления можно стилями темы, через ключ неявного стиля.</span><span class="sxs-lookup"><span data-stu-id="33cbe-120">A <xref:System.Type> key is fundamental to how controls can be styled by themes, through an implicit style key.</span></span> <span data-ttu-id="33cbe-121">Дополнительные сведения см. в разделе [Общие сведения о разработке элементов управления](../controls/control-authoring-overview.md).</span><span class="sxs-lookup"><span data-stu-id="33cbe-121">For more information, see [Control Authoring Overview](../controls/control-authoring-overview.md).</span></span>  
  
 <span data-ttu-id="33cbe-122">Декларативные альтернативные методы ссылкой на ресурс — как [расширение разметки DynamicResource](dynamicresource-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="33cbe-122">The alternative declarative means of referencing a resource is as a [DynamicResource Markup Extension](dynamicresource-markup-extension.md).</span></span>  
  
 <span data-ttu-id="33cbe-123">Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="33cbe-123">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="33cbe-124">Строковая лексема, указываемая после строки идентификатора `StaticResource`, присваивается в качестве значения <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> соответствующего класса расширения <xref:System.Windows.StaticResourceExtension>.</span><span class="sxs-lookup"><span data-stu-id="33cbe-124">The string token provided after the `StaticResource` identifier string is assigned as the <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> value of the underlying <xref:System.Windows.StaticResourceExtension> extension class.</span></span>  
  
 `StaticResource` <span data-ttu-id="33cbe-125">может использоваться в синтаксисе элемента объекта.</span><span class="sxs-lookup"><span data-stu-id="33cbe-125">can be used in object element syntax.</span></span> <span data-ttu-id="33cbe-126">В этом случае укажите значение параметра <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> свойство является обязательным.</span><span class="sxs-lookup"><span data-stu-id="33cbe-126">In this case, specifying the value of the <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> property is required.</span></span>  
  
 `StaticResource` <span data-ttu-id="33cbe-127">Можно также использовать в использовании атрибут verbose, который указывает <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> как свойство = значение пары:</span><span class="sxs-lookup"><span data-stu-id="33cbe-127">can also be used in a verbose attribute usage that specifies the <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 <span data-ttu-id="33cbe-128">Подробное определение зачастую удобно использовать для расширений, которые имеют несколько устанавливаемых свойств, а также в том случае, если некоторые свойства являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="33cbe-128">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="33cbe-129">Так как `StaticResource` имеет только одно устанавливаемое свойство, которое является обязательным, это использование не является типичным.</span><span class="sxs-lookup"><span data-stu-id="33cbe-129">Because `StaticResource` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="33cbe-130">В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] реализации обработчика обработка данного расширения разметки определяется <xref:System.Windows.StaticResourceExtension> класса.</span><span class="sxs-lookup"><span data-stu-id="33cbe-130">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.StaticResourceExtension> class.</span></span>  
  
 `StaticResource` <span data-ttu-id="33cbe-131">является расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="33cbe-131">is a markup extension.</span></span> <span data-ttu-id="33cbe-132">Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами.</span><span class="sxs-lookup"><span data-stu-id="33cbe-132">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="33cbe-133">Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы "{" и "}" в синтаксисе их атрибутов, который является соглашением, по которому обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут.</span><span class="sxs-lookup"><span data-stu-id="33cbe-133">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="33cbe-134">Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="33cbe-134">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33cbe-135">См. также</span><span class="sxs-lookup"><span data-stu-id="33cbe-135">See also</span></span>

- [<span data-ttu-id="33cbe-136">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="33cbe-136">Styling and Templating</span></span>](../controls/styling-and-templating.md)
- [<span data-ttu-id="33cbe-137">Обзор XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="33cbe-137">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="33cbe-138">Расширения разметки и XAML WPF</span><span class="sxs-lookup"><span data-stu-id="33cbe-138">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="33cbe-139">Ресурсы XAML</span><span class="sxs-lookup"><span data-stu-id="33cbe-139">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="33cbe-140">Ресурсы и код</span><span class="sxs-lookup"><span data-stu-id="33cbe-140">Resources and Code</span></span>](resources-and-code.md)
