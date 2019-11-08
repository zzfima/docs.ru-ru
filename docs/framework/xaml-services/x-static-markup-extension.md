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
ms.openlocfilehash: bf94f1d61ee3080c9d3582e55e0695b269801c80
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733359"
---
# <a name="xstatic-markup-extension"></a><span data-ttu-id="176e7-102">Расширение разметки x:Static</span><span class="sxs-lookup"><span data-stu-id="176e7-102">x:Static Markup Extension</span></span>
<span data-ttu-id="176e7-103">Ссылается на любую статическую сущность кода по значению, определенную в соответствии с CLS-совместимой спецификацией.</span><span class="sxs-lookup"><span data-stu-id="176e7-103">References any static by-value code entity that is defined in a Common Language Specification (CLS)–compliant way.</span></span> <span data-ttu-id="176e7-104">Статическое свойство, на которое указывает ссылка, можно использовать для предоставления значения свойства в XAML.</span><span class="sxs-lookup"><span data-stu-id="176e7-104">The static property that is referenced can be used to provide the value of a property in XAML.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="176e7-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="176e7-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="176e7-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="176e7-106">XAML Values</span></span>  
  
| | |  
|-|-|  
|`prefix`|<span data-ttu-id="176e7-107">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="176e7-107">Optional.</span></span> <span data-ttu-id="176e7-108">Префикс, который ссылается на сопоставленное пространство имен XAML, отличное от используемого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="176e7-108">A prefix that refers to a mapped, non-default XAML namespace.</span></span> <span data-ttu-id="176e7-109">`prefix` отображается явно в использовании, так как редко используются статические свойства, полученные из пространства имен XAML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="176e7-109">`prefix` is shown explicitly in the usage because you rarely reference static properties that come from a default XAML namespace.</span></span> <span data-ttu-id="176e7-110">См. заметки.</span><span class="sxs-lookup"><span data-stu-id="176e7-110">See Remarks.</span></span>|  
|`typeName`|<span data-ttu-id="176e7-111">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="176e7-111">Required.</span></span> <span data-ttu-id="176e7-112">Имя типа, определяющего нужный статический элемент.</span><span class="sxs-lookup"><span data-stu-id="176e7-112">The name of the type that defines the desired static member.</span></span>|  
|`staticMemberName`|<span data-ttu-id="176e7-113">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="176e7-113">Required.</span></span> <span data-ttu-id="176e7-114">Имя нужного статического элемента значения (константа, статическое свойство, поле или значение перечисления).</span><span class="sxs-lookup"><span data-stu-id="176e7-114">The name of the desired static value member (a constant, a static property, a field, or an enumeration value).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="176e7-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="176e7-115">Remarks</span></span>  

<span data-ttu-id="176e7-116">Сущность кода, на которую указывает ссылка, должна быть одной из следующих:</span><span class="sxs-lookup"><span data-stu-id="176e7-116">The code entity that is referenced must be one of the following:</span></span>  
  
- <span data-ttu-id="176e7-117">Константа</span><span class="sxs-lookup"><span data-stu-id="176e7-117">A constant</span></span>  
- <span data-ttu-id="176e7-118">Статическое свойство</span><span class="sxs-lookup"><span data-stu-id="176e7-118">A static property</span></span>  
- <span data-ttu-id="176e7-119">Поле</span><span class="sxs-lookup"><span data-stu-id="176e7-119">A field</span></span>  
- <span data-ttu-id="176e7-120">Значение перечисления</span><span class="sxs-lookup"><span data-stu-id="176e7-120">An enumeration value</span></span>

<span data-ttu-id="176e7-121">Указание любой другой сущности кода, например нестатического свойства, вызывает ошибку времени компиляции, если XAML размещается в компилированном виде, или исключение синтаксического анализа времени загрузки XAML.</span><span class="sxs-lookup"><span data-stu-id="176e7-121">Specifying any other code entity, such as a nonstatic property, causes a compile-time error if the XAML is markup compiled, or a XAML load-time parse exception.</span></span>  

<span data-ttu-id="176e7-122">Можно сделать `x:Static` ссылки на статические поля или свойства, которые не находятся в пространстве имен XAML по умолчанию для текущего документа XAML. Однако для этого требуется сопоставление префикса.</span><span class="sxs-lookup"><span data-stu-id="176e7-122">You can make `x:Static` references to static fields or properties that are not in the default XAML namespace for the current XAML document; however, this requires a prefix mapping.</span></span> <span data-ttu-id="176e7-123">Пространства имен XAML практически всегда определяются в корневом элементе документа XAML.</span><span class="sxs-lookup"><span data-stu-id="176e7-123">XAML namespaces are almost always defined on the root element of the XAML document.</span></span>  

<span data-ttu-id="176e7-124">Операции уточняющего запроса для статических свойств можно выполнять с помощью .NET Framework служб XAML и их средств чтения и записи XAML, когда они выполняются с контекстом схемы XAML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="176e7-124">The lookup operations for static properties can be performed by .NET Framework XAML Services and its XAML readers and XAML writers, when they are running with the default XAML schema context.</span></span> <span data-ttu-id="176e7-125">Этот контекст схемы XAML может использовать отражение CLR для предоставления необходимых статических значений для построения графа объекта.</span><span class="sxs-lookup"><span data-stu-id="176e7-125">This XAML schema context can use CLR reflection to provide the necessary static values for object graph construction.</span></span> <span data-ttu-id="176e7-126">Заданный `typeName` фактически является именем типа XAML, а не именем типа CLR, хотя при использовании контекста схемы XAML по умолчанию или при использовании всех существующих платформ, основанных на XAML на основе среды CLR, они по сути имеют одно и то же имя.</span><span class="sxs-lookup"><span data-stu-id="176e7-126">The `typeName` you specify is actually a XAML type name, not a CLR type name, although these are essentially the same name when using the default XAML schema context or when using all existing CLR-based XAML-implementing frameworks.</span></span>  

<span data-ttu-id="176e7-127">Будьте внимательны при создании `x:Static` ссылок, которые не относятся непосредственно к типу значения свойства.</span><span class="sxs-lookup"><span data-stu-id="176e7-127">Use caution when you make `x:Static` references that are not directly the type of a property's value.</span></span> <span data-ttu-id="176e7-128">В последовательности обработки XAML указанные значения из расширения разметки не вызывают преобразование дополнительного значения.</span><span class="sxs-lookup"><span data-stu-id="176e7-128">In the XAML processing sequence, provided values from a markup extension do not invoke additional value conversion.</span></span> <span data-ttu-id="176e7-129">Это справедливо, даже если ссылка на `x:Static` создает текстовую строку, а преобразование значения для значений атрибутов на основе текстовой строки обычно происходит либо для этого конкретного элемента, либо для любых значений элементов типа возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="176e7-129">This is true even if your `x:Static` reference creates a text string, and a value conversion for attribute values based on text string typically occurs either for that specific member or for any member values of the return type.</span></span>  

<span data-ttu-id="176e7-130">Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="176e7-130">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="176e7-131">Строковая лексема, указываемая после строки идентификатора `x:Static`, присваивается в качестве значения <xref:System.Windows.Markup.StaticExtension.Member%2A> соответствующего класса расширения <xref:System.Windows.Markup.StaticExtension>.</span><span class="sxs-lookup"><span data-stu-id="176e7-131">The string token provided after the `x:Static` identifier string is assigned as the <xref:System.Windows.Markup.StaticExtension.Member%2A> value of the underlying <xref:System.Windows.Markup.StaticExtension> extension class.</span></span>  

<span data-ttu-id="176e7-132">Существует еще два варианта использования XAML, которые технически возможны.</span><span class="sxs-lookup"><span data-stu-id="176e7-132">There are two other XAML usages that are technically possible.</span></span> <span data-ttu-id="176e7-133">Однако эти случаи использования менее распространены, так как они необязательно являются подробными:</span><span class="sxs-lookup"><span data-stu-id="176e7-133">However, these usages are less common because they are unnecessarily verbose:</span></span>  

1. <span data-ttu-id="176e7-134">Синтаксис объектного элемента.</span><span class="sxs-lookup"><span data-stu-id="176e7-134">Object element syntax.</span></span>

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

2. <span data-ttu-id="176e7-135">Синтаксис атрибута с явным свойством элемента для строки инициализации.</span><span class="sxs-lookup"><span data-stu-id="176e7-135">Attribute syntax with explicit Member property for initialization string.</span></span>

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

<span data-ttu-id="176e7-136">В .NET Framework реализации служб XAML обработка этого расширения разметки определяется классом <xref:System.Windows.Markup.StaticExtension>.</span><span class="sxs-lookup"><span data-stu-id="176e7-136">In the .NET Framework XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.StaticExtension> class.</span></span>  

<span data-ttu-id="176e7-137">`x:Static` является расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="176e7-137">`x:Static` is a markup extension.</span></span> <span data-ttu-id="176e7-138">Все расширения разметки в XAML используют `{` и `}` символов в синтаксисе атрибутов, который является соглашением, по которому обработчик XAML распознает, что расширение разметки должно предоставлять значение.</span><span class="sxs-lookup"><span data-stu-id="176e7-138">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must provide a value.</span></span> <span data-ttu-id="176e7-139">Дополнительные сведения о расширениях разметки см. в разделе [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="176e7-139">For more information about markup extensions, see [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md).</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="176e7-140">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="176e7-140">WPF Usage Notes</span></span>  
 <span data-ttu-id="176e7-141">Пространство имен XAML по умолчанию, используемое для программирования WPF, не содержит много полезных статических свойств, а большинство полезных статических свойств имеют поддержку, например преобразователи типов, которые упрощают использование без необходимости `{x:Static}`.</span><span class="sxs-lookup"><span data-stu-id="176e7-141">The default XAML namespace you use for WPF programming does not contain many useful static properties, and most of the useful static properties have support such as type converters that facilitate the usage without requiring `{x:Static}` .</span></span> <span data-ttu-id="176e7-142">Для статических свойств необходимо сопоставлять префикс для пространства имен XAML, если выполняется одно из следующих условий.</span><span class="sxs-lookup"><span data-stu-id="176e7-142">For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span></span>  
  
- <span data-ttu-id="176e7-143">Вы ссылаетесь на тип, который существует в WPF, но не является частью пространства имен XAML по умолчанию для WPF (`http://schemas.microsoft.com/winfx/2006/xaml/presentation`).</span><span class="sxs-lookup"><span data-stu-id="176e7-143">You are referencing a type that exists in WPF but is not part of the default XAML namespace for WPF (`http://schemas.microsoft.com/winfx/2006/xaml/presentation`).</span></span> <span data-ttu-id="176e7-144">Это довольно распространенный сценарий использования `x:Static`.</span><span class="sxs-lookup"><span data-stu-id="176e7-144">This is a fairly common scenario for using `x:Static`.</span></span> <span data-ttu-id="176e7-145">Например, можно использовать ссылку на `x:Static` с сопоставлением пространства имен XAML с <xref:System> пространством имен CLR и сборкой mscorlib, чтобы ссылаться на статические свойства класса <xref:System.Environment>.</span><span class="sxs-lookup"><span data-stu-id="176e7-145">For example, you might use an `x:Static` reference with a XAML namespace mapping to the <xref:System> CLR namespace and mscorlib assembly in order to reference the static properties of the <xref:System.Environment> class.</span></span>  
  
- <span data-ttu-id="176e7-146">Вы ссылаетесь на тип из пользовательской сборки.</span><span class="sxs-lookup"><span data-stu-id="176e7-146">You are referencing a type from a custom assembly.</span></span>  
  
- <span data-ttu-id="176e7-147">Вы ссылаетесь на тип, который существует в сборке WPF, но этот тип находится в пространстве имен CLR, которое не было сопоставлено как часть пространства имен XAML по умолчанию WPF.</span><span class="sxs-lookup"><span data-stu-id="176e7-147">You are referencing a type that exists in a WPF assembly, but that type is within a CLR namespace that was not mapped to be part of the WPF default XAML namespace.</span></span> <span data-ttu-id="176e7-148">Сопоставление пространств имен CLR с пространством имен XAML по умолчанию для WPF выполняется определениями в различных сборках WPF (Дополнительные сведения об этой концепции см. в разделе [пространства имен XAML и сопоставление пространств имен для WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span><span class="sxs-lookup"><span data-stu-id="176e7-148">The mapping of CLR namespaces into the default XAML namespace for WPF is performed by definitions in the various WPF assemblies (for more information about this concept, see [XAML Namespaces and Namespace Mapping for WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span></span> <span data-ttu-id="176e7-149">Несопоставленные пространства имен CLR могут существовать, если пространство имен CLR состоит преимущественно из определений классов, которые обычно не предназначены для XAML, например <xref:System.Windows.Threading>.</span><span class="sxs-lookup"><span data-stu-id="176e7-149">Non-mapped CLR namespaces can exist if that CLR namespace is composed mostly of class definitions that are not typically intended for XAML, such as <xref:System.Windows.Threading>.</span></span>  
  
 <span data-ttu-id="176e7-150">Дополнительные сведения об использовании префиксов и пространств имен XAML для WPF см. в разделе [пространства имен и сопоставление пространств имен XAML для WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="176e7-150">For more information on how to use prefixes and XAML namespaces for WPF, see [XAML Namespaces and Namespace Mapping for WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="176e7-151">См. также</span><span class="sxs-lookup"><span data-stu-id="176e7-151">See also</span></span>

- [<span data-ttu-id="176e7-152">Расширение разметки x:Type</span><span class="sxs-lookup"><span data-stu-id="176e7-152">x:Type Markup Extension</span></span>](x-type-markup-extension.md)
- [<span data-ttu-id="176e7-153">Типы, перенесенные из WPF в System.Xaml</span><span class="sxs-lookup"><span data-stu-id="176e7-153">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
