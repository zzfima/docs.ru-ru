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
ms.openlocfilehash: 9fa9e51e66af6df4d1a6b1ec94c5010651bbb21d
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401512"
---
# <a name="xstatic-markup-extension"></a><span data-ttu-id="c669f-102">Расширение разметки x:Static</span><span class="sxs-lookup"><span data-stu-id="c669f-102">x:Static Markup Extension</span></span>
<span data-ttu-id="c669f-103">Ссылается на любую статическую сущность кода по значению, определенную в соответствии с CLS-совместимой спецификацией.</span><span class="sxs-lookup"><span data-stu-id="c669f-103">References any static by-value code entity that is defined in a Common Language Specification (CLS)–compliant way.</span></span> <span data-ttu-id="c669f-104">Статическое свойство, на которое указывает ссылка, можно использовать для предоставления значения свойства в XAML.</span><span class="sxs-lookup"><span data-stu-id="c669f-104">The static property that is referenced can be used to provide the value of a property in XAML.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="c669f-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="c669f-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="c669f-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="c669f-106">XAML Values</span></span>  
  
| | |  
|-|-|  
|`prefix`|<span data-ttu-id="c669f-107">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="c669f-107">Optional.</span></span> <span data-ttu-id="c669f-108">Префикс, который ссылается на сопоставленное пространство имен XAML, отличное от используемого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c669f-108">A prefix that refers to a mapped, non-default XAML namespace.</span></span> <span data-ttu-id="c669f-109">`prefix`явно указывается в использовании, так как редко используются ссылки на статические свойства, полученные из пространства имен XAML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c669f-109">`prefix` is shown explicitly in the usage because you rarely reference static properties that come from a default XAML namespace.</span></span> <span data-ttu-id="c669f-110">См. заметки.</span><span class="sxs-lookup"><span data-stu-id="c669f-110">See Remarks.</span></span>|  
|`typeName`|<span data-ttu-id="c669f-111">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="c669f-111">Required.</span></span> <span data-ttu-id="c669f-112">Имя типа, определяющего нужный статический элемент.</span><span class="sxs-lookup"><span data-stu-id="c669f-112">The name of the type that defines the desired static member.</span></span>|  
|`staticMemberName`|<span data-ttu-id="c669f-113">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="c669f-113">Required.</span></span> <span data-ttu-id="c669f-114">Имя нужного статического элемента значения (константа, статическое свойство, поле или значение перечисления).</span><span class="sxs-lookup"><span data-stu-id="c669f-114">The name of the desired static value member (a constant, a static property, a field, or an enumeration value).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c669f-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="c669f-115">Remarks</span></span>  

<span data-ttu-id="c669f-116">Сущность кода, на которую указывает ссылка, должна быть одной из следующих:</span><span class="sxs-lookup"><span data-stu-id="c669f-116">The code entity that is referenced must be one of the following:</span></span>  
  
- <span data-ttu-id="c669f-117">Константа</span><span class="sxs-lookup"><span data-stu-id="c669f-117">A constant</span></span>  
- <span data-ttu-id="c669f-118">Статическое свойство</span><span class="sxs-lookup"><span data-stu-id="c669f-118">A static property</span></span>  
- <span data-ttu-id="c669f-119">Поле</span><span class="sxs-lookup"><span data-stu-id="c669f-119">A field</span></span>  
- <span data-ttu-id="c669f-120">Значение перечисления</span><span class="sxs-lookup"><span data-stu-id="c669f-120">An enumeration value</span></span>

<span data-ttu-id="c669f-121">Указание любой другой сущности кода, например нестатического свойства, вызывает ошибку времени компиляции, если XAML размещается в компилированном виде, или исключение синтаксического анализа времени загрузки XAML.</span><span class="sxs-lookup"><span data-stu-id="c669f-121">Specifying any other code entity, such as a nonstatic property, causes a compile-time error if the XAML is markup compiled, or a XAML load-time parse exception.</span></span>  

<span data-ttu-id="c669f-122">Можно сделать `x:Static` ссылки на статические поля или свойства, которые не находятся в пространстве имен XAML по умолчанию для текущего документа XAML, однако для этого требуется сопоставление префикса.</span><span class="sxs-lookup"><span data-stu-id="c669f-122">You can make `x:Static` references to static fields or properties that are not in the default XAML namespace for the current XAML document; however, this requires a prefix mapping.</span></span> <span data-ttu-id="c669f-123">Пространства имен XAML практически всегда определяются в корневом элементе документа XAML.</span><span class="sxs-lookup"><span data-stu-id="c669f-123">XAML namespaces are almost always defined on the root element of the XAML document.</span></span>  

<span data-ttu-id="c669f-124">Операции уточняющего запроса для статических свойств можно выполнять с помощью .NET Framework служб XAML и их средств чтения и записи XAML, когда они выполняются с контекстом схемы XAML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c669f-124">The lookup operations for static properties can be performed by .NET Framework XAML Services and its XAML readers and XAML writers, when they are running with the default XAML schema context.</span></span> <span data-ttu-id="c669f-125">Этот контекст схемы XAML может использовать отражение CLR для предоставления необходимых статических значений для построения графа объекта.</span><span class="sxs-lookup"><span data-stu-id="c669f-125">This XAML schema context can use CLR reflection to provide the necessary static values for object graph construction.</span></span> <span data-ttu-id="c669f-126">В `typeName` действительности указывается имя типа XAML, а не имя типа CLR, хотя при использовании контекста схемы XAML по умолчанию или при использовании всех существующих платформ, основанных на XAML в среде CLR, они по сути совпадают.</span><span class="sxs-lookup"><span data-stu-id="c669f-126">The `typeName` you specify is actually a XAML type name, not a CLR type name, although these are essentially the same name when using the default XAML schema context or when using all existing CLR-based XAML-implementing frameworks.</span></span>  

<span data-ttu-id="c669f-127">Будьте внимательны при создании `x:Static` ссылок, которые не относятся непосредственно к типу значения свойства.</span><span class="sxs-lookup"><span data-stu-id="c669f-127">Use caution when you make `x:Static` references that are not directly the type of a property's value.</span></span> <span data-ttu-id="c669f-128">В последовательности обработки XAML указанные значения из расширения разметки не вызывают преобразование дополнительного значения.</span><span class="sxs-lookup"><span data-stu-id="c669f-128">In the XAML processing sequence, provided values from a markup extension do not invoke additional value conversion.</span></span> <span data-ttu-id="c669f-129">Это справедливо, даже если ваша `x:Static` ссылка создает текстовую строку, а преобразование значения для значений атрибутов на основе текстовой строки обычно происходит либо для этого конкретного элемента, либо для любых значений элементов типа возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="c669f-129">This is true even if your `x:Static` reference creates a text string, and a value conversion for attribute values based on text string typically occurs either for that specific member or for any member values of the return type.</span></span>  

<span data-ttu-id="c669f-130">Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="c669f-130">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="c669f-131">Строковая лексема, указываемая после строки идентификатора `x:Static`, присваивается в качестве значения <xref:System.Windows.Markup.StaticExtension.Member%2A> соответствующего класса расширения <xref:System.Windows.Markup.StaticExtension>.</span><span class="sxs-lookup"><span data-stu-id="c669f-131">The string token provided after the `x:Static` identifier string is assigned as the <xref:System.Windows.Markup.StaticExtension.Member%2A> value of the underlying <xref:System.Windows.Markup.StaticExtension> extension class.</span></span>  

<span data-ttu-id="c669f-132">Существует еще два варианта использования XAML, которые технически возможны.</span><span class="sxs-lookup"><span data-stu-id="c669f-132">There are two other XAML usages that are technically possible.</span></span> <span data-ttu-id="c669f-133">Однако эти случаи использования менее распространены, так как они необязательно являются подробными:</span><span class="sxs-lookup"><span data-stu-id="c669f-133">However, these usages are less common because they are unnecessarily verbose:</span></span>  

1. <span data-ttu-id="c669f-134">Синтаксис объектного элемента.</span><span class="sxs-lookup"><span data-stu-id="c669f-134">Object element syntax.</span></span>

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

2. <span data-ttu-id="c669f-135">Синтаксис атрибута с явным свойством элемента для строки инициализации.</span><span class="sxs-lookup"><span data-stu-id="c669f-135">Attribute syntax with explicit Member property for initialization string.</span></span>

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

<span data-ttu-id="c669f-136">В .NET Framework реализации служб XAML обработка этого расширения разметки определяется <xref:System.Windows.Markup.StaticExtension> классом.</span><span class="sxs-lookup"><span data-stu-id="c669f-136">In the .NET Framework XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.StaticExtension> class.</span></span>  

<span data-ttu-id="c669f-137">`x:Static` является расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="c669f-137">`x:Static` is a markup extension.</span></span> <span data-ttu-id="c669f-138">Все расширения разметки в XAML используют `{` символы `}` и в синтаксисе атрибутов, что является соглашением, по которому обработчик XAML распознает, что расширение разметки должно предоставлять значение.</span><span class="sxs-lookup"><span data-stu-id="c669f-138">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must provide a value.</span></span> <span data-ttu-id="c669f-139">Дополнительные сведения о расширениях разметки см. в разделе [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c669f-139">For more information about markup extensions, see [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md).</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="c669f-140">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="c669f-140">WPF Usage Notes</span></span>  
 <span data-ttu-id="c669f-141">Пространство имен XAML по умолчанию, используемое для программирования WPF, не содержит много полезных статических свойств, а большая часть полезных статических свойств имеет поддержку, например, преобразователи типов, которые упрощают `{x:Static}` использование без необходимости.</span><span class="sxs-lookup"><span data-stu-id="c669f-141">The default XAML namespace you use for WPF programming does not contain many useful static properties, and most of the useful static properties have support such as type converters that facilitate the usage without requiring `{x:Static}` .</span></span> <span data-ttu-id="c669f-142">Для статических свойств необходимо сопоставлять префикс для пространства имен XAML, если выполняется одно из следующих условий.</span><span class="sxs-lookup"><span data-stu-id="c669f-142">For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span></span>  
  
- <span data-ttu-id="c669f-143">Вы ссылаетесь на тип, который существует в WPF, но не является частью пространства имен XAML по умолчанию[!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]для WPF ().</span><span class="sxs-lookup"><span data-stu-id="c669f-143">You are referencing a type that exists in WPF but is not part of the default XAML namespace for WPF ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]).</span></span> <span data-ttu-id="c669f-144">Это довольно распространенный сценарий использования `x:Static`.</span><span class="sxs-lookup"><span data-stu-id="c669f-144">This is a fairly common scenario for using `x:Static`.</span></span> <span data-ttu-id="c669f-145">Например, вы можете использовать `x:Static` ссылку с сопоставлением <xref:System> пространства имен XAML с пространством имен CLR и сборкой mscorlib для ссылки <xref:System.Environment> на статические свойства класса.</span><span class="sxs-lookup"><span data-stu-id="c669f-145">For example, you might use an `x:Static` reference with a XAML namespace mapping to the <xref:System> CLR namespace and mscorlib assembly in order to reference the static properties of the <xref:System.Environment> class.</span></span>  
  
- <span data-ttu-id="c669f-146">Вы ссылаетесь на тип из пользовательской сборки.</span><span class="sxs-lookup"><span data-stu-id="c669f-146">You are referencing a type from a custom assembly.</span></span>  
  
- <span data-ttu-id="c669f-147">Вы ссылаетесь на тип, который существует в сборке WPF, но этот тип находится в пространстве имен CLR, которое не было сопоставлено как часть пространства имен XAML по умолчанию WPF.</span><span class="sxs-lookup"><span data-stu-id="c669f-147">You are referencing a type that exists in a WPF assembly, but that type is within a CLR namespace that was not mapped to be part of the WPF default XAML namespace.</span></span> <span data-ttu-id="c669f-148">Сопоставление пространств имен CLR с пространством имен XAML по умолчанию для WPF выполняется определениями в различных сборках WPF (Дополнительные сведения об этой концепции см. в разделе [пространства имен XAML и сопоставление пространств имен для WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span><span class="sxs-lookup"><span data-stu-id="c669f-148">The mapping of CLR namespaces into the default XAML namespace for WPF is performed by definitions in the various WPF assemblies (for more information about this concept, see [XAML Namespaces and Namespace Mapping for WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span></span> <span data-ttu-id="c669f-149">Несопоставленные пространства имен CLR могут существовать, если пространство имен CLR состоит преимущественно из определений классов, которые обычно не предназначены для XAML, например <xref:System.Windows.Threading>.</span><span class="sxs-lookup"><span data-stu-id="c669f-149">Non-mapped CLR namespaces can exist if that CLR namespace is composed mostly of class definitions that are not typically intended for XAML, such as <xref:System.Windows.Threading>.</span></span>  
  
 <span data-ttu-id="c669f-150">Дополнительные сведения об использовании префиксов и пространств имен XAML для WPF см. в разделе [пространства имен и сопоставление пространств имен XAML для WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="c669f-150">For more information on how to use prefixes and XAML namespaces for WPF, see [XAML Namespaces and Namespace Mapping for WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c669f-151">См. также</span><span class="sxs-lookup"><span data-stu-id="c669f-151">See also</span></span>

- [<span data-ttu-id="c669f-152">Расширение разметки x:Type</span><span class="sxs-lookup"><span data-stu-id="c669f-152">x:Type Markup Extension</span></span>](x-type-markup-extension.md)
- [<span data-ttu-id="c669f-153">Типы, перенесенные из WPF в System.Xaml</span><span class="sxs-lookup"><span data-stu-id="c669f-153">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
