---
title: "Расширение разметки x:Type"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
caps.latest.revision: "27"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: ed0372349a08687fd83b0fc989cc4cb88c29d96c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xtype-markup-extension"></a><span data-ttu-id="d6b4b-102">Расширение разметки x:Type</span><span class="sxs-lookup"><span data-stu-id="d6b4b-102">x:Type Markup Extension</span></span>
<span data-ttu-id="d6b4b-103">Среда CLR предоставляет <xref:System.Type> объект, который является базовым типом для указанного типа XAML.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-103">Supplies the CLR <xref:System.Type> object that is the underlying type for a specified XAML type.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="d6b4b-104">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="d6b4b-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Type prefix:typeNameValue}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="d6b4b-105">Использование элемента объекта XAML</span><span class="sxs-lookup"><span data-stu-id="d6b4b-105">XAML Object Element Usage</span></span>  
  
```xaml  
<x:Type TypeName="prefix:typeNameValue"/>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="d6b4b-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="d6b4b-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`prefix`|<span data-ttu-id="d6b4b-107">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-107">Optional.</span></span> <span data-ttu-id="d6b4b-108">Префикс, который сопоставляет пространство имен XAML не по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-108">A prefix that maps a non-default XAML namespace.</span></span> <span data-ttu-id="d6b4b-109">Указание префикса часто не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-109">Specifying a prefix is frequently not necessary.</span></span> <span data-ttu-id="d6b4b-110">См. заметки.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-110">See Remarks.</span></span>|  
|`typeNameValue`|<span data-ttu-id="d6b4b-111">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-111">Required.</span></span> <span data-ttu-id="d6b4b-112">Имя типа, которое разрешается до текущего пространства имен XAML по умолчанию; или указанного сопоставленного префикса, если `prefix` предоставляется.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-112">A type name resolvable to the current default XAML namespace; or the specified mapped prefix if `prefix` is supplied.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6b4b-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="d6b4b-113">Remarks</span></span>  
 <span data-ttu-id="d6b4b-114">`x:Type` Расширение разметки получает аналогичные функции для `typeof()` оператор в [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)] или `GetType` оператор в [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6b4b-114">The `x:Type` markup extension has a similar function to the `typeof()` operator in [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)] or the `GetType` operator in [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)].</span></span>  
  
 <span data-ttu-id="d6b4b-115">`x:Type` Расширение разметки предоставляет поведение преобразования из строки для свойств, которые принимают тип <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-115">The `x:Type` markup extension supplies a from-string conversion behavior for properties that take the type <xref:System.Type>.</span></span> <span data-ttu-id="d6b4b-116">Входные данные — это тип XAML.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-116">The input is a XAML type.</span></span> <span data-ttu-id="d6b4b-117">Связь между тип входных данных XAML и выходных данных CLR <xref:System.Type> выводится, <xref:System.Type> — <xref:System.Xaml.XamlType.UnderlyingType%2A> входного <xref:System.Xaml.XamlType>, поиск необходимого <xref:System.Xaml.XamlType> на основе контекста схемы XAML и <xref:System.Windows.Markup.IXamlTypeResolver>предоставляет контекст службы.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-117">The relationship between the input XAML type and the output CLR <xref:System.Type> is that the output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input <xref:System.Xaml.XamlType>, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>  
  
 <span data-ttu-id="d6b4b-118">В службах XAML .NET Framework, определяется обработка для данного расширения разметки <xref:System.Windows.Markup.TypeExtension> класса.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-118">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.TypeExtension> class.</span></span>  
  
 <span data-ttu-id="d6b4b-119">В реализациях конкретной платформы, некоторые свойства, принимающие <xref:System.Type> как значения можно принять имя типа напрямую (строковое значение типа `Name`).</span><span class="sxs-lookup"><span data-stu-id="d6b4b-119">In specific framework implementations, some properties that take <xref:System.Type> as a value can accept the name of the type directly (the string value of the type `Name`).</span></span> <span data-ttu-id="d6b4b-120">Тем не менее для реализации этого поведения является сложным сценарием.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-120">However, implementing this behavior is a complex scenario.</span></span> <span data-ttu-id="d6b4b-121">Примеры см. в следующем разделе «Примечания об использовании WPF».</span><span class="sxs-lookup"><span data-stu-id="d6b4b-121">For examples, see the "WPF Usage Notes" section that follows.</span></span>  
  
 <span data-ttu-id="d6b4b-122">Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-122">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="d6b4b-123">Строковая лексема, указываемая после строки идентификатора `x:Type`, присваивается в качестве значения <xref:System.Windows.Markup.TypeExtension.TypeName%2A> соответствующего класса расширения <xref:System.Windows.Markup.TypeExtension>.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-123">The string token provided after the `x:Type` identifier string is assigned as the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> value of the underlying <xref:System.Windows.Markup.TypeExtension> extension class.</span></span> <span data-ttu-id="d6b4b-124">В контексте схемы XAML по умолчанию для служб XAML .NET Framework, который основан на типах CLR, значение этого атрибута является <xref:System.Reflection.MemberInfo.Name%2A> нужного типа, или содержит, <xref:System.Reflection.MemberInfo.Name%2A> предшествует префикс для пространства имен XAML не по умолчанию сопоставление.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-124">Under the default XAML schema context for .NET Framework XAML Services, which is based on CLR types, the value of this attribute is either the <xref:System.Reflection.MemberInfo.Name%2A> of the desired type, or contains that <xref:System.Reflection.MemberInfo.Name%2A> preceded by a prefix for a non-default XAML namespace mapping.</span></span>  
  
 <span data-ttu-id="d6b4b-125">`x:Type` Расширения разметки может использоваться в синтаксисе элемента объекта.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-125">The `x:Type` markup extension can be used in object element syntax.</span></span> <span data-ttu-id="d6b4b-126">В этом случае укажите значение параметра <xref:System.Windows.Markup.TypeExtension.TypeName%2A> свойства, необходимые для правильной инициализации расширения.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-126">In this case, specifying the value of the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> property is required to properly initialize the extension.</span></span>  
  
 <span data-ttu-id="d6b4b-127">`x:Type` Расширения разметки также может использоваться как атрибут verbose; Однако такое использование не является типичным: `<``object``property``="{x:Type TypeName=``typeNameValue``}" .../>`</span><span class="sxs-lookup"><span data-stu-id="d6b4b-127">The `x:Type` markup extension can also be used as a verbose attribute; however this use is not typical: `<``object` `property``="{x:Type TypeName=``typeNameValue``}" .../>`</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="d6b4b-128">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="d6b4b-128">WPF Usage Notes</span></span>  
  
### <a name="default-xaml-namespace-and-type-mapping"></a><span data-ttu-id="d6b4b-129">Сопоставление типов и пространства имен XAML по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d6b4b-129">Default XAML Namespace and Type Mapping</span></span>  
 <span data-ttu-id="d6b4b-130">Пространство имен XAML по умолчанию для программирования WPF содержит большинство типов XAML, что нужно для типовых сценариев XAML; Таким образом часто можно избежать префиксы при ссылке на значения типа XAML.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-130">The default XAML namespace for WPF programming contains most of the XAML types you need for typical XAML scenarios; therefore, you can often avoid prefixes when referencing XAML type values.</span></span> <span data-ttu-id="d6b4b-131">Может потребоваться сопоставление префикса, если ссылка на тип из пользовательской сборки, а также для типов, существующих в сборке WPF, но из пространства имен CLR, которое не было сопоставлено пространству имен XAML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-131">You might need to map a prefix if you are referencing a type from a custom assembly or for types that exist in a WPF assembly but are from a CLR namespace that was not mapped to the default XAML namespace.</span></span> <span data-ttu-id="d6b4b-132">Дополнительные сведения о префиксы пространства имен языка XAML и сопоставление пространств имен CLR см. в разделе [пространства имен XAML и сопоставление пространства имен для WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="d6b4b-132">For more information about prefixes, XAML namespaces, and mapping CLR namespaces, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>  
  
### <a name="type-properties-that-support-typename-as-string"></a><span data-ttu-id="d6b4b-133">Свойства этой поддержки Typename как строки типа</span><span class="sxs-lookup"><span data-stu-id="d6b4b-133">Type Properties That Support Typename-as-String</span></span>  
 <span data-ttu-id="d6b4b-134">WPF поддерживает методы, позволяющие указывать значения некоторых свойств типа <xref:System.Type> без необходимости `x:Type` использование расширения разметки.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-134">WPF supports techniques that enable specifying the value of some properties of type <xref:System.Type> without requiring an `x:Type` markup extension usage.</span></span> <span data-ttu-id="d6b4b-135">Вместо этого можно указать значение как строка с именем типа.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-135">Instead, you can specify the value as a string that names the type.</span></span> <span data-ttu-id="d6b4b-136">Примером <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> и <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-136">Examples of this are <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> and <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d6b4b-137">Поддержка этого поведения не обеспечивается через преобразователи типов или расширения разметки.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-137">Support for this behavior is not provided through either type converters or markup extensions.</span></span> <span data-ttu-id="d6b4b-138">Вместо этого это реализуется с помощью поведения отсрочки <xref:System.Windows.FrameworkElementFactory>.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-138">Instead, this is a deferral behavior implemented through <xref:System.Windows.FrameworkElementFactory>.</span></span>  
  
 <span data-ttu-id="d6b4b-139">Silverlight поддерживает аналогичные соглашения.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-139">Silverlight supports a similar convention.</span></span> <span data-ttu-id="d6b4b-140">На самом деле Silverlight не поддерживается `{x:Type}` в его поддержки языка XAML и не принимает `{x:Type}` варианты использования за пределами в некоторых случаях, которые предназначены для поддержки миграции XAML WPF Silverlight.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-140">In fact, Silverlight does not currently support `{x:Type}` in its XAML language support, and does not accept `{x:Type}` usages outside of a few circumstances that are intended to support WPF-Silverlight XAML migration.</span></span> <span data-ttu-id="d6b4b-141">Таким образом, поведение typename как строки встроенных все ознакомительную версию Silverlight встроенного свойства где <xref:System.Type> значение.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-141">Therefore, the typename-as-string behavior is built-in to all Silverlight native property evaluation where a <xref:System.Type> is the value.</span></span>  
  
## <a name="xaml-2009"></a><span data-ttu-id="d6b4b-142">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="d6b4b-142">XAML 2009</span></span>  
 <span data-ttu-id="d6b4b-143">XAML 2009 обеспечивает дополнительную поддержку для универсальные типы и изменяет поведение функции `x:TypeArguments` и `x:Type` поддержки.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-143">XAML 2009 provides additional support for generic types and modifies the feature behavior of `x:TypeArguments` and `x:Type` to provide this support.</span></span>  
  
-   <span data-ttu-id="d6b4b-144">`x:TypeArguments`и элемент связанного объекта для создания экземпляра универсального объекта могут быть в элементах, отличные от корневого.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-144">`x:TypeArguments` and the associated object element for a generic object instantiation can be on elements other than the root.</span></span> <span data-ttu-id="d6b4b-145">Дополнительные сведения см. раздел «XAML 2009» [директива x: TypeArguments](../../../docs/framework/xaml-services/x-typearguments-directive.md).</span><span class="sxs-lookup"><span data-stu-id="d6b4b-145">For more information, see the "XAML 2009" section of [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).</span></span>  
  
-   <span data-ttu-id="d6b4b-146">XAML 2009 поддерживает синтаксис для указания ограничения универсального типа в разметку.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-146">XAML 2009 supports a syntax for specifying a generic type's constraint in markup.</span></span> <span data-ttu-id="d6b4b-147">Это может использоваться `x:TypeArguments`, `x:Type`, или эти две функции в сочетании.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-147">This can be used by `x:TypeArguments`, by `x:Type`, or by the two features in combination.</span></span>  
  
-   <span data-ttu-id="d6b4b-148">Реализация WPF XAML при обработке XAML 2009 для загрузки также добавляет эту возможность неявного преобразования типов для определенных свойств платформы, которые используют тип <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-148">WPF XAML implementation when processing XAML 2009 for load also adds this capability to the implicit type conversion behavior for certain framework properties that use type <xref:System.Type>.</span></span>  
  
 <span data-ttu-id="d6b4b-149">В WPF можно использовать возможности XAML 2009, но только для свободного XAML (XAML, который не является компилированной разметки).</span><span class="sxs-lookup"><span data-stu-id="d6b4b-149">In WPF, you can use XAML 2009 features but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="d6b4b-150">Скомпилированный с разметкой XAML и форма BAML кода XAML в настоящее время не поддерживают ключевые слова и компоненты XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="d6b4b-150">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6b4b-151">См. также</span><span class="sxs-lookup"><span data-stu-id="d6b4b-151">See Also</span></span>  
 <xref:System.Windows.Style>  
 [<span data-ttu-id="d6b4b-152">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="d6b4b-152">Styling and Templating</span></span>](../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="d6b4b-153">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="d6b4b-153">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="d6b4b-154">Расширения разметки и XAML WPF</span><span class="sxs-lookup"><span data-stu-id="d6b4b-154">Markup Extensions and WPF XAML</span></span>](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
