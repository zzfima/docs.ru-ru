---
title: Расширение разметки x:Array
ms.date: 03/30/2017
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
ms.openlocfilehash: 4f4e26eb3e5ccaf66b2173c7fc9952375c5f2a58
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139143"
---
# <a name="xarray-markup-extension"></a><span data-ttu-id="9c062-102">Расширение разметки x:Array</span><span class="sxs-lookup"><span data-stu-id="9c062-102">x:Array Markup Extension</span></span>
<span data-ttu-id="9c062-103">Предоставляет общую поддержку для массивов объектов в XAML посредством расширения разметки.</span><span class="sxs-lookup"><span data-stu-id="9c062-103">Provides general support for arrays of objects in XAML through a markup extension.</span></span> <span data-ttu-id="9c062-104">Это соответствует `x:ArrayExtension` тип XAML в [MS-XAML].</span><span class="sxs-lookup"><span data-stu-id="9c062-104">This corresponds to the `x:ArrayExtension` XAML type in [MS-XAML].</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="9c062-105">Использование элемента объекта XAML</span><span class="sxs-lookup"><span data-stu-id="9c062-105">XAML Object Element Usage</span></span>  
  
```  
<x:Array Type="typeName">  
  arrayContents  
</x:Array>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="9c062-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="9c062-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`typeName`|<span data-ttu-id="9c062-107">Имя типа, ваш `x:Array` будет содержать.</span><span class="sxs-lookup"><span data-stu-id="9c062-107">The name of the type that your `x:Array` will contain.</span></span> `typeName` <span data-ttu-id="9c062-108">может быть (и часто является) с префиксом для XAML определения типов пространство имен, содержащее XAML.</span><span class="sxs-lookup"><span data-stu-id="9c062-108">may be (and often is) prefixed for a XAML namespace that contains the XAML type definitions.</span></span>|  
|`arrayContents`|<span data-ttu-id="9c062-109">Элементы содержимого, назначенного к встроенным `ArrayExtension.Items` свойство.</span><span class="sxs-lookup"><span data-stu-id="9c062-109">The items content that is assigned to the intrinsic `ArrayExtension.Items` property.</span></span> <span data-ttu-id="9c062-110">Как правило, эти элементы задаются в виде одного или нескольких элементов объектов, содержащихся в `x:Array` открывающих и закрывающих тегов.</span><span class="sxs-lookup"><span data-stu-id="9c062-110">Typically, these items are specified as one or more object elements contained within the `x:Array` opening and closing tags.</span></span> <span data-ttu-id="9c062-111">Объекты, указанные здесь, должны содержать может быть назначен для типа XAML, указанного в `typeName`.</span><span class="sxs-lookup"><span data-stu-id="9c062-111">Objects specified here are expected to be assignable to the XAML type specified in `typeName`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c062-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="9c062-112">Remarks</span></span>  
 `Type` <span data-ttu-id="9c062-113">атрибут является обязательным для всех `x:Array` объектных элемента.</span><span class="sxs-lookup"><span data-stu-id="9c062-113">is a required attribute for all `x:Array` object elements.</span></span> <span data-ttu-id="9c062-114">Объект `Type` значение параметра не требуется использовать `x:Type` расширение разметки; короткое имя типа является типом XAML, который может быть указан как строка.</span><span class="sxs-lookup"><span data-stu-id="9c062-114">A `Type` parameter value does not need to use an `x:Type` markup extension; the short name of the type is   a XAML type, which can be specified as a string.</span></span>  
  
 <span data-ttu-id="9c062-115">В реализации служб XAML .NET Framework, отображается связь между тип входных данных XAML и выходных данных среды CLR <xref:System.Type> созданный массива зависит от контекста службы для расширения разметки.</span><span class="sxs-lookup"><span data-stu-id="9c062-115">In the .NET Framework XAML Services implementation, the relationship between the input XAML type and the output CLR <xref:System.Type> of the created array is influenced by service context for markup extensions.</span></span> <span data-ttu-id="9c062-116">Выходные данные <xref:System.Type> — <xref:System.Xaml.XamlType.UnderlyingType%2A> входного типа XAML, после поиска необходимого <xref:System.Xaml.XamlType> на основе контекста схемы XAML и <xref:System.Windows.Markup.IXamlTypeResolver> предоставляет контекст службы.</span><span class="sxs-lookup"><span data-stu-id="9c062-116">The output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input XAML type, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>  
  
 <span data-ttu-id="9c062-117">При обработке содержимое массива назначаются `ArrayExtension.Items` внутреннее свойство.</span><span class="sxs-lookup"><span data-stu-id="9c062-117">When processed, the array contents are assigned to the `ArrayExtension.Items` intrinsic property.</span></span> <span data-ttu-id="9c062-118">В <xref:System.Windows.Markup.ArrayExtension> реализации, оно представлено <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9c062-118">In the <xref:System.Windows.Markup.ArrayExtension> implementation, this is represented by <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="9c062-119">В реализации служб XAML .NET Framework, обработка данного расширения разметки определяется <xref:System.Windows.Markup.ArrayExtension> класса.</span><span class="sxs-lookup"><span data-stu-id="9c062-119">In the .NET Framework XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.ArrayExtension> class.</span></span> <xref:System.Windows.Markup.ArrayExtension> <span data-ttu-id="9c062-120">не запечатан и может использоваться в качестве основы для реализации расширения разметки для пользовательского типа массива.</span><span class="sxs-lookup"><span data-stu-id="9c062-120">is not sealed, and could be used as the basis for a markup extension implementation for a custom array type.</span></span>  
  
 `x:Array` <span data-ttu-id="9c062-121">— Это сведения предназначены для общих расширения языка в XAML.</span><span class="sxs-lookup"><span data-stu-id="9c062-121">is more intended for general language extensibility in XAML.</span></span> <span data-ttu-id="9c062-122">Но `x:Array` также можно использовать для указания XAML значений определенных свойств, которые принимают в качестве их структурированного содержимого свойств коллекций поддерживается в XAML.</span><span class="sxs-lookup"><span data-stu-id="9c062-122">But `x:Array` can also be useful for specifying XAML values of certain properties that take XAML-supported collections as their structured property content.</span></span> <span data-ttu-id="9c062-123">Например, можно указать содержимое <xref:System.Collections.IEnumerable> свойство с `x:Array` использования.</span><span class="sxs-lookup"><span data-stu-id="9c062-123">For example, you could specify the contents of an <xref:System.Collections.IEnumerable> property with an `x:Array` usage.</span></span>  
  
 `x:Array` <span data-ttu-id="9c062-124">является расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="9c062-124">is a markup extension.</span></span> <span data-ttu-id="9c062-125">Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами.</span><span class="sxs-lookup"><span data-stu-id="9c062-125">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> `x:Array` <span data-ttu-id="9c062-126">частично является исключением из этого правила, так как вместо предоставления альтернативной обработки значения атрибута, `x:Array` обеспечивает альтернативную обработку его внутреннего текстового содержимого.</span><span class="sxs-lookup"><span data-stu-id="9c062-126">is partially an exception to that rule because instead of providing alternative attribute value handling, `x:Array` provides alternative handling of its inner text content.</span></span> <span data-ttu-id="9c062-127">Такое поведение позволяет типов, которые могут не поддерживаться существующей модели содержимого сгруппированы в массив и ссылается позже в коде доступа к именованным массива. Вы можете вызвать <xref:System.Array> методы для получения отдельных элементов массива.</span><span class="sxs-lookup"><span data-stu-id="9c062-127">This behavior enables types that might not be supported by an existing content model to be grouped into an array and referenced later in code-behind by accessing the named array; you can call <xref:System.Array> methods to get individual array items.</span></span>  
  
 <span data-ttu-id="9c062-128">Все расширения разметки в XAML используйте фигурные скобки ({,} `)` в синтаксисе их атрибутов, который является соглашением, по которому обработчик XAML узнает, что расширение разметки должно обработать значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="9c062-128">All markup extensions in XAML use the braces ({,}`)` in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute value.</span></span> <span data-ttu-id="9c062-129">Дополнительные сведения о расширениях разметки в целом см. в разделе [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions-for-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="9c062-129">For more information about markup extensions in general, see [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions-for-xaml.md).</span></span>  
  
 <span data-ttu-id="9c062-130">В XAML 2009 г. `x:Array` определяется как примитив вместо расширения разметки языка.</span><span class="sxs-lookup"><span data-stu-id="9c062-130">In XAML 2009, `x:Array` is defined as a language primitive instead of a markup extension.</span></span> <span data-ttu-id="9c062-131">Дополнительные сведения см. в разделе [встроенные типы для общих примитивов языка XAML](built-in-types-for-common-xaml-language-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="9c062-131">For more information, see [Built-in Types for Common XAML Language Primitives](built-in-types-for-common-xaml-language-primitives.md).</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="9c062-132">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="9c062-132">WPF Usage Notes</span></span>  
 <span data-ttu-id="9c062-133">Как правило, объектные элементы, заполняющие `x:Array` , не являются элементами, которые существуют в [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] пространства имен XAML и необходимо выполнить сопоставление префикса пространства имен XAML не по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9c062-133">Typically, the object elements that populate an `x:Array` are not elements that exist in the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML namespace, and require a prefix mapping to a non-default XAML namespace.</span></span>  
  
 <span data-ttu-id="9c062-134">Например, ниже приведен простой массив из двух строк с `sys` префикс (и также `x`) определены на уровне массива.</span><span class="sxs-lookup"><span data-stu-id="9c062-134">For example, the following is a simple array of two strings, with the `sys` prefix (and also `x`) defined at the level of the array.</span></span>  
  
 <span data-ttu-id="9c062-135">[xaml]</span><span class="sxs-lookup"><span data-stu-id="9c062-135">[xaml]</span></span>  
  
 `<x:Array Type="sys:String" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 `xmlns:sys="clr-namespace:System;assembly=mscorlib">`  
  
 `<sys:String>Hello</sys:String>`  
  
 `<sys:String>World</sys:String>`  
  
 `</x:Array>`  
  
 <span data-ttu-id="9c062-136">Для пользовательских типов, которые используются в качестве элементов массива класс должен также поддерживать требования для создания экземпляров в XAML как элементы объекта.</span><span class="sxs-lookup"><span data-stu-id="9c062-136">For custom types that are used as array elements, the class must also support the requirements for being instantiated in XAML as object elements.</span></span> <span data-ttu-id="9c062-137">Дополнительные сведения см. в разделе [XAML и пользовательские классы для WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="9c062-137">For more information, see [XAML and Custom Classes for WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c062-138">См. также</span><span class="sxs-lookup"><span data-stu-id="9c062-138">See also</span></span>

- [<span data-ttu-id="9c062-139">Расширения разметки и XAML WPF</span><span class="sxs-lookup"><span data-stu-id="9c062-139">Markup Extensions and WPF XAML</span></span>](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="9c062-140">Типы, перенесенные из WPF в System.Xaml</span><span class="sxs-lookup"><span data-stu-id="9c062-140">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
