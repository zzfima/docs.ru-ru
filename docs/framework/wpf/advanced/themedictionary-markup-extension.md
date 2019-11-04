---
title: Расширение разметки ThemeDictionary
ms.date: 03/30/2017
f1_keywords:
- ThemeDictionaryExtension
- ThemeDictionary
helpviewer_keywords:
- ThemeDictionary markup extension [WPF]
- XAML [WPF], ThemeDictionary markup extension
ms.assetid: aa75e10b-13dd-4989-972d-51bab63a05e2
ms.openlocfilehash: ab38c2c885e230183852fff895e0a8a8f1d7a666
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459489"
---
# <a name="themedictionary-markup-extension"></a><span data-ttu-id="957d7-102">Расширение разметки ThemeDictionary</span><span class="sxs-lookup"><span data-stu-id="957d7-102">ThemeDictionary Markup Extension</span></span>
<span data-ttu-id="957d7-103">Предоставляет для разработчиков пользовательских элементов управления или приложений, которые объединяют элементы управления сторонних производителей, способ загрузки определенных темой словарей ресурсов для использования в стилизации элемента управления.</span><span class="sxs-lookup"><span data-stu-id="957d7-103">Provides a way for custom control authors or applications that integrate third-party controls to load theme-specific resource dictionaries to use in styling the control.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="957d7-104">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="957d7-104">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{ThemeDictionary assemblyUri}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="957d7-105">Использование элемента объекта XAML</span><span class="sxs-lookup"><span data-stu-id="957d7-105">XAML Object Element Usage</span></span>  
  
```xml  
<object>  
  <object.property>  
    <ThemeDictionary AssemblyName="assemblyUri"/>  
  <object.property>  
<object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="957d7-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="957d7-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`assemblyUri`|<span data-ttu-id="957d7-107">Универсальный код ресурса (URI) сборки, содержащей сведения о теме.</span><span class="sxs-lookup"><span data-stu-id="957d7-107">The uniform resource identifier (URI) of the assembly that contains theme information.</span></span> <span data-ttu-id="957d7-108">Как правило, это URI типа pack, который ссылается на сборку в большом пакете.</span><span class="sxs-lookup"><span data-stu-id="957d7-108">Typically, this is a pack URI that references an assembly in the larger package.</span></span> <span data-ttu-id="957d7-109">Ресурсы сборки и URI типа pack упрощают развертывание.</span><span class="sxs-lookup"><span data-stu-id="957d7-109">Assembly resources and pack URIs simplify deployment issues.</span></span> <span data-ttu-id="957d7-110">Дополнительные сведения см. в разделе [URI типа pack в WPF](../app-development/pack-uris-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="957d7-110">For more information see [Pack URIs in WPF](../app-development/pack-uris-in-wpf.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="957d7-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="957d7-111">Remarks</span></span>  
 <span data-ttu-id="957d7-112">Это расширение предназначено для заполнения только одного конкретного значения свойства: значение для <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="957d7-112">This extension is intended to fill only one specific property value: a value for <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="957d7-113">С помощью этого расширения можно указать только одну сборку с ресурсами, которая содержит некоторые стили, которые будут использоваться только при применении темы Windows Aero к системе пользователя, другие стили только в том случае, если тема Luna активна и т. д.</span><span class="sxs-lookup"><span data-stu-id="957d7-113">By using this extension, you can specify a single resources-only assembly that contains some styles to use only when the Windows Aero theme is applied to the user's system, other styles only when the Luna theme is active, and so on.</span></span> <span data-ttu-id="957d7-114">Используя это расширение, содержимое словаря ресурсов элемента управления при необходимости можно автоматически считать недействительным и перезагрузить для другой темы.</span><span class="sxs-lookup"><span data-stu-id="957d7-114">By using this extension, the contents of a control-specific resource dictionary can be automatically invalidated and reloaded to be specific for another theme when required.</span></span>  
  
 <span data-ttu-id="957d7-115">Строка `assemblyUri` (значение свойства<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A>) служит основанием соглашения об именовании, которое определяет, какой словарь применяется к конкретной теме.</span><span class="sxs-lookup"><span data-stu-id="957d7-115">The `assemblyUri` string (<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> property value) forms the basis of a naming convention that identifies which dictionary applies for a particular theme.</span></span> <span data-ttu-id="957d7-116">Логика <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> для `ThemeDictionary` завершает соглашение путем создания универсального кода ресурса (URI), указывающего на конкретный вариант словаря темы, который содержится в предварительно скомпилированной сборке ресурсов.</span><span class="sxs-lookup"><span data-stu-id="957d7-116">The <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> logic for `ThemeDictionary` completes the convention by generating a uniform resource identifier (URI) that points to a particular theme dictionary variant, as contained within a precompiled resource assembly.</span></span> <span data-ttu-id="957d7-117">Описание этого соглашения или взаимодействия темы со стилизацией основных элементов управления и стилизацией уровня страницы или приложения, как концепции, полностью в данном разделе не рассматривается.</span><span class="sxs-lookup"><span data-stu-id="957d7-117">Describing this convention, or theme interactions with general control styling and page/application level styling as a concept, is not covered fully here.</span></span> <span data-ttu-id="957d7-118">Базовый сценарий использования `ThemeDictionary` — указание свойства <xref:System.Windows.ResourceDictionary.Source%2A> `ResourceDictionary`, объявленного на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="957d7-118">The basic scenario for using `ThemeDictionary` is to specify the <xref:System.Windows.ResourceDictionary.Source%2A> property of a `ResourceDictionary` declared at the application level.</span></span> <span data-ttu-id="957d7-119">При предоставлении универсального кода ресурса (URI) для сборки с помощью `ThemeDictionary`ного расширения, а не прямого URI, логика расширения предоставит логику недействительности, которая применяется при каждом изменении темы системы.</span><span class="sxs-lookup"><span data-stu-id="957d7-119">When you provide a URI for the assembly through a `ThemeDictionary` extension rather than as a direct URI, the extension logic will provide invalidation logic that applies whenever the system theme changes.</span></span>  
  
 <span data-ttu-id="957d7-120">Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="957d7-120">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="957d7-121">Строковая лексема, указываемая после строки идентификатора `ThemeDictionary`, присваивается в качестве значения <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> соответствующего класса расширения <xref:System.Windows.ThemeDictionaryExtension>.</span><span class="sxs-lookup"><span data-stu-id="957d7-121">The string token provided after the `ThemeDictionary` identifier string is assigned as the <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> value of the underlying <xref:System.Windows.ThemeDictionaryExtension> extension class.</span></span>  
  
 <span data-ttu-id="957d7-122">`ThemeDictionary` также можно использовать в синтаксисе элемента объекта.</span><span class="sxs-lookup"><span data-stu-id="957d7-122">`ThemeDictionary` may also be used in object element syntax.</span></span> <span data-ttu-id="957d7-123">В этом случае необходимо указать значение свойства <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A>.</span><span class="sxs-lookup"><span data-stu-id="957d7-123">In this case, specifying the value of the <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> property is required.</span></span>  
  
 <span data-ttu-id="957d7-124">Излишним может оказаться и использование `ThemeDictionary` в атрибуте, в котором свойство <xref:System.Windows.Markup.StaticExtension.Member%2A> определено как пара "свойство=значение".</span><span class="sxs-lookup"><span data-stu-id="957d7-124">`ThemeDictionary` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.Markup.StaticExtension.Member%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" .../>  
```  
  
 <span data-ttu-id="957d7-125">Подробное определение зачастую удобно использовать для расширений, которые имеют несколько устанавливаемых свойств, а также в том случае, если некоторые свойства являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="957d7-125">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="957d7-126">Так как `ThemeDictionary` имеет только одно устанавливаемое свойство, которое является обязательным, это использование не является типичным.</span><span class="sxs-lookup"><span data-stu-id="957d7-126">Because `ThemeDictionary` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="957d7-127">В реализации процессора [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] обработка этого расширения разметки определяется классом <xref:System.Windows.ThemeDictionaryExtension>.</span><span class="sxs-lookup"><span data-stu-id="957d7-127">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.ThemeDictionaryExtension> class.</span></span>  
  
 <span data-ttu-id="957d7-128">`ThemeDictionary` является расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="957d7-128">`ThemeDictionary` is a markup extension.</span></span> <span data-ttu-id="957d7-129">Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами.</span><span class="sxs-lookup"><span data-stu-id="957d7-129">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="957d7-130">Все расширения разметки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используют символы "{" и "}" в синтаксисе их атрибутов, который является соглашением, по которому обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] распознает, что расширение разметки должно обработать атрибут.</span><span class="sxs-lookup"><span data-stu-id="957d7-130">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="957d7-131">Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="957d7-131">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="957d7-132">См. также</span><span class="sxs-lookup"><span data-stu-id="957d7-132">See also</span></span>

- [<span data-ttu-id="957d7-133">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="957d7-133">Styling and Templating</span></span>](../controls/styling-and-templating.md)
- [<span data-ttu-id="957d7-134">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="957d7-134">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="957d7-135">Расширения разметки и XAML WPF</span><span class="sxs-lookup"><span data-stu-id="957d7-135">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="957d7-136">Файлы ресурсов, контента и данных WPF-приложения</span><span class="sxs-lookup"><span data-stu-id="957d7-136">WPF Application Resource, Content, and Data Files</span></span>](../app-development/wpf-application-resource-content-and-data-files.md)
