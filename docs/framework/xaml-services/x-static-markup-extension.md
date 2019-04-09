---
title: Расширение разметки x:Static
ms.date: 03/30/2017
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
ms.openlocfilehash: eb0c34f259220a0326238b27ab43efd3078b0bcc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207088"
---
# <a name="xstatic-markup-extension"></a><span data-ttu-id="fe1ba-102">Расширение разметки x:Static</span><span class="sxs-lookup"><span data-stu-id="fe1ba-102">x:Static Markup Extension</span></span>
<span data-ttu-id="fe1ba-103">Ссылается на любой сущности кода статический по значению, определенному в [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]— надлежащим способом.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-103">References any static by-value code entity that is defined in a [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]–compliant way.</span></span> <span data-ttu-id="fe1ba-104">Статическое свойство, которое указывается может использоваться для предоставления значения свойства в XAML.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-104">The static property that is referenced can be used to provide the value of a property in XAML.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="fe1ba-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="fe1ba-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="fe1ba-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="fe1ba-106">XAML Values</span></span>  
  
| | |  
|-|-|  
|`prefix`|<span data-ttu-id="fe1ba-107">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-107">Optional.</span></span> <span data-ttu-id="fe1ba-108">Префикс, который ссылается на сопоставленные, не по умолчанию пространство имен XAML.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-108">A prefix that refers to a mapped, non-default XAML namespace.</span></span> `prefix` <span data-ttu-id="fe1ba-109">явно приведен в использовании, так как редко создаются ссылки на статические свойства, полученные из пространства имен XAML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-109">is shown explicitly in the usage because you rarely reference static properties that come from a default XAML namespace.</span></span> <span data-ttu-id="fe1ba-110">См. заметки.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-110">See Remarks.</span></span>|  
|`typeName`|<span data-ttu-id="fe1ba-111">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-111">Required.</span></span> <span data-ttu-id="fe1ba-112">Имя типа, который определяет требуемый статический член.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-112">The name of the type that defines the desired static member.</span></span>|  
|`staticMemberName`|<span data-ttu-id="fe1ba-113">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-113">Required.</span></span> <span data-ttu-id="fe1ba-114">Имя требуемого статического значения члена (константа, статическое свойство, поле или значение перечисления).</span><span class="sxs-lookup"><span data-stu-id="fe1ba-114">The name of the desired static value member (a constant, a static property, a field, or an enumeration value).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe1ba-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="fe1ba-115">Remarks</span></span>  

<span data-ttu-id="fe1ba-116">Код, на который приведена ссылка должна быть одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="fe1ba-116">The code entity that is referenced must be one of the following:</span></span>  
  
-   <span data-ttu-id="fe1ba-117">Константа</span><span class="sxs-lookup"><span data-stu-id="fe1ba-117">A constant</span></span>  
-   <span data-ttu-id="fe1ba-118">Статическое свойство</span><span class="sxs-lookup"><span data-stu-id="fe1ba-118">A static property</span></span>  
-   <span data-ttu-id="fe1ba-119">Поле</span><span class="sxs-lookup"><span data-stu-id="fe1ba-119">A field</span></span>  
-   <span data-ttu-id="fe1ba-120">Значение перечисления</span><span class="sxs-lookup"><span data-stu-id="fe1ba-120">An enumeration value</span></span>

<span data-ttu-id="fe1ba-121">Указание любой другой сущности кода, например нестатического свойства, приводит к ошибке времени компиляции, если XAML компиляции разметки или исключения во время загрузки синтаксического анализа XAML.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-121">Specifying any other code entity, such as a nonstatic property, causes a compile-time error if the XAML is markup compiled, or a XAML load-time parse exception.</span></span>  

<span data-ttu-id="fe1ba-122">Чтобы `x:Static` ссылки на статические поля или свойства, не входящие в пространство имен XAML по умолчанию для текущего документа XAML; Однако это требует сопоставления префикса.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-122">You can make `x:Static` references to static fields or properties that are not in the default XAML namespace for the current XAML document; however, this requires a prefix mapping.</span></span> <span data-ttu-id="fe1ba-123">Пространства имен XAML, почти всегда определяются в корневом элементе документа XAML.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-123">XAML namespaces are almost always defined on the root element of the XAML document.</span></span>  

<span data-ttu-id="fe1ba-124">Операции поиска для статических свойств могут выполняться служб XAML .NET Framework и средства чтения XAML и записи XAML, если они выполняются с контекстом схемы XAML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-124">The lookup operations for static properties can be performed by .NET Framework XAML Services and its XAML readers and XAML writers, when they are running with the default XAML schema context.</span></span> <span data-ttu-id="fe1ba-125">Этот контекст схемы XAML можно использовать отражение среды CLR для предоставления необходимых статических значений для построения графа объекта.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-125">This XAML schema context can use CLR reflection to provide the necessary static values for object graph construction.</span></span> <span data-ttu-id="fe1ba-126">`typeName` Указать, является фактически XAML имени типа и не имя типа CLR, несмотря на то, что это по сути тем же именем, при использовании контекста схемы XAML по умолчанию или при использовании всех существующих платформ, основанных на среде CLR реализация XAML.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-126">The `typeName` you specify is actually a XAML type name, not a CLR type name, although these are essentially the same name when using the default XAML schema context or when using all existing CLR-based XAML-implementing frameworks.</span></span>  

<span data-ttu-id="fe1ba-127">Соблюдайте осторожность при внесении `x:Static` ссылки, которые непосредственно не принадлежат к типу значения свойства.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-127">Use caution when you make `x:Static` references that are not directly the type of a property's value.</span></span> <span data-ttu-id="fe1ba-128">В XAML обработки последовательности, предоставленных значений из расширения разметки не вызывают дополнительное значение преобразования.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-128">In the XAML processing sequence, provided values from a markup extension do not invoke additional value conversion.</span></span> <span data-ttu-id="fe1ba-129">Это верно даже в том случае, если ваш `x:Static` ссылка создает строку текста и преобразование значений атрибутов на основе текста строки обычно возникает для этого конкретного элемента или для любого значения членов типа возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-129">This is true even if your `x:Static` reference creates a text string, and a value conversion for attribute values based on text string typically occurs either for that specific member or for any member values of the return type.</span></span>  

<span data-ttu-id="fe1ba-130">Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-130">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="fe1ba-131">Строковая лексема, указываемая после строки идентификатора `x:Static`, присваивается в качестве значения <xref:System.Windows.Markup.StaticExtension.Member%2A> соответствующего класса расширения <xref:System.Windows.Markup.StaticExtension>.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-131">The string token provided after the `x:Static` identifier string is assigned as the <xref:System.Windows.Markup.StaticExtension.Member%2A> value of the underlying <xref:System.Windows.Markup.StaticExtension> extension class.</span></span>  

<span data-ttu-id="fe1ba-132">Существует два сценария XAML, которые являются технически возможно.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-132">There are two other XAML usages that are technically possible.</span></span> <span data-ttu-id="fe1ba-133">Тем не менее эти данные об использовании применяется реже, поскольку они являются излишним:</span><span class="sxs-lookup"><span data-stu-id="fe1ba-133">However, these usages are less common because they are unnecessarily verbose:</span></span>  

1.  <span data-ttu-id="fe1ba-134">Синтаксис объектных элементов.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-134">Object element syntax.</span></span>

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

2.  <span data-ttu-id="fe1ba-135">Синтаксис атрибута с явным свойством элемента для строки инициализации.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-135">Attribute syntax with explicit Member property for initialization string.</span></span>

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

<span data-ttu-id="fe1ba-136">В реализации служб XAML .NET Framework, обработка данного расширения разметки определяется <xref:System.Windows.Markup.StaticExtension> класса.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-136">In the .NET Framework XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.StaticExtension> class.</span></span>  

`x:Static` <span data-ttu-id="fe1ba-137">является расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-137">is a markup extension.</span></span> <span data-ttu-id="fe1ba-138">Все расширения разметки в XAML используют `{` и `}` символов в синтаксисе их атрибутов, который является соглашением, по которому обработчик XAML узнает, что расширение разметки необходимо указать значение.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-138">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must provide a value.</span></span> <span data-ttu-id="fe1ba-139">Дополнительные сведения о расширениях разметки см. в разделе [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fe1ba-139">For more information about markup extensions, see [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md).</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="fe1ba-140">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="fe1ba-140">WPF Usage Notes</span></span>  
 <span data-ttu-id="fe1ba-141">Пространство имен XAML по умолчанию, используемое для программирования WPF не содержит множество полезных статических свойств, а большинство полезных статические свойства имеют поддержку, таких как преобразователи типов, которые облегчают использование без необходимости `{x:Static}` .</span><span class="sxs-lookup"><span data-stu-id="fe1ba-141">The default XAML namespace you use for WPF programming does not contain many useful static properties, and most of the useful static properties have support such as type converters that facilitate the usage without requiring `{x:Static}` .</span></span> <span data-ttu-id="fe1ba-142">Для статических свойств его необходимо сопоставить префикс для пространства имен XAML, если выполняется одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="fe1ba-142">For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span></span>  
  
-   <span data-ttu-id="fe1ba-143">Вы ссылаетесь на тип, который существует в WPF, но не является частью пространства имен XAML по умолчанию для WPF ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="fe1ba-143">You are referencing a type that exists in WPF but is not part of the default XAML namespace for WPF ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]).</span></span> <span data-ttu-id="fe1ba-144">Это довольно распространенный сценарий использования `x:Static`.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-144">This is a fairly common scenario for using `x:Static`.</span></span> <span data-ttu-id="fe1ba-145">Например, можно использовать `x:Static` ссылку с сопоставление пространства имен XAML для <xref:System> сборки пространства имен и mscorlib среды CLR, чтобы ссылаться на статические свойства класса <xref:System.Environment> класса.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-145">For example, you might use an `x:Static` reference with a XAML namespace mapping to the <xref:System> CLR namespace and mscorlib assembly in order to reference the static properties of the <xref:System.Environment> class.</span></span>  
  
-   <span data-ttu-id="fe1ba-146">Ссылка на тип из пользовательской сборки.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-146">You are referencing a type from a custom assembly.</span></span>  
  
-   <span data-ttu-id="fe1ba-147">Ссылка типом, который существует в сборке WPF, но этот тип находится в пределах пространства имен CLR, который не был сопоставлен с быть частью пространства имен XAML по умолчанию WPF.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-147">You are referencing a type that exists in a WPF assembly, but that type is within a CLR namespace that was not mapped to be part of the WPF default XAML namespace.</span></span> <span data-ttu-id="fe1ba-148">Сопоставление пространств имен CLR в пространство имен XAML по умолчанию для WPF выполняется путем определения в различных сборках WPF (Дополнительные сведения о трудностях, см. в разделе [пространства имен XAML и сопоставление пространств имен для WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span><span class="sxs-lookup"><span data-stu-id="fe1ba-148">The mapping of CLR namespaces into the default XAML namespace for WPF is performed by definitions in the various WPF assemblies (for more information about this concept, see [XAML Namespaces and Namespace Mapping for WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span></span> <span data-ttu-id="fe1ba-149">Несопоставленные пространства имен CLR могут существовать, если пространство имен CLR состоит главным образом из определения классов, которые обычно не предназначены для XAML, таких как <xref:System.Windows.Threading>.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-149">Non-mapped CLR namespaces can exist if that CLR namespace is composed mostly of class definitions that are not typically intended for XAML, such as <xref:System.Windows.Threading>.</span></span>  
  
 <span data-ttu-id="fe1ba-150">Дополнительные сведения о том, как использовать префиксы и пространства имен XAML для WPF см. в разделе [пространства имен XAML и сопоставление пространств имен для WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="fe1ba-150">For more information on how to use prefixes and XAML namespaces for WPF, see [XAML Namespaces and Namespace Mapping for WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe1ba-151">См. также</span><span class="sxs-lookup"><span data-stu-id="fe1ba-151">See also</span></span>

- [<span data-ttu-id="fe1ba-152">Расширение разметки x:Type</span><span class="sxs-lookup"><span data-stu-id="fe1ba-152">x:Type Markup Extension</span></span>](x-type-markup-extension.md)
- [<span data-ttu-id="fe1ba-153">Типы, перенесенные из WPF в System.Xaml</span><span class="sxs-lookup"><span data-stu-id="fe1ba-153">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
