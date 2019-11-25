---
title: Атрибуты (C#)
ms.date: 04/26/2018
ms.openlocfilehash: 2a07035ea97bb0ff1a8f4793fe8a30d3a42c34a7
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141565"
---
# <a name="attributes-c"></a><span data-ttu-id="df9d8-102">Атрибуты (C#)</span><span class="sxs-lookup"><span data-stu-id="df9d8-102">Attributes (C#)</span></span>

<span data-ttu-id="df9d8-103">Атрибуты предоставляют мощное средство для связывания метаданных или декларативной информации с кодом (сборки, типы, методы, свойства и т. д.).</span><span class="sxs-lookup"><span data-stu-id="df9d8-103">Attributes provide a powerful method of associating metadata, or declarative information, with code (assemblies, types, methods, properties, and so forth).</span></span> <span data-ttu-id="df9d8-104">Связав атрибут связан с сущностью программы, вы можете проверять этот атрибут во время выполнения, используя технику *отражения*.</span><span class="sxs-lookup"><span data-stu-id="df9d8-104">After an attribute is associated with a program entity, the attribute can be queried at run time by using a technique called *reflection*.</span></span> <span data-ttu-id="df9d8-105">Подробнее см. в разделе [Отражение (C#)](../reflection.md).</span><span class="sxs-lookup"><span data-stu-id="df9d8-105">For more information, see [Reflection (C#)](../reflection.md).</span></span>

<span data-ttu-id="df9d8-106">Атрибуты имеют следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="df9d8-106">Attributes have the following properties:</span></span>

- <span data-ttu-id="df9d8-107">Атрибуты добавляют в программу метаданные.</span><span class="sxs-lookup"><span data-stu-id="df9d8-107">Attributes add metadata to your program.</span></span> <span data-ttu-id="df9d8-108">*Метаданные* — это сведения о типах, определенных в программе.</span><span class="sxs-lookup"><span data-stu-id="df9d8-108">*Metadata* is information about the types defined in a program.</span></span> <span data-ttu-id="df9d8-109">Все сборки .NET содержат некоторый набор метаданных, описывающих типы и члены типов, определенные в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="df9d8-109">All .NET assemblies contain a specified set of metadata that describes the types and type members defined in the assembly.</span></span> <span data-ttu-id="df9d8-110">Вы можете добавить пользовательские атрибуты, чтобы указать любую дополнительную информацию.</span><span class="sxs-lookup"><span data-stu-id="df9d8-110">You can add custom attributes to specify any additional information that is required.</span></span> <span data-ttu-id="df9d8-111">Подробнее см. в разделе [Создание настраиваемых атрибутов (C#)](creating-custom-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="df9d8-111">For more information, see, [Creating Custom Attributes (C#)](creating-custom-attributes.md).</span></span>
- <span data-ttu-id="df9d8-112">Вы можете применить один или несколько атрибутов ко всей сборке, к модулю или к более мелким элементам программы, например к классам и свойствам.</span><span class="sxs-lookup"><span data-stu-id="df9d8-112">You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.</span></span>
- <span data-ttu-id="df9d8-113">Атрибуты могут принимать аргументы, так же как методы и свойства.</span><span class="sxs-lookup"><span data-stu-id="df9d8-113">Attributes can accept arguments in the same way as methods and properties.</span></span>
- <span data-ttu-id="df9d8-114">Программа может проверить собственные метаданные или метаданные в других программах, используя отражение.</span><span class="sxs-lookup"><span data-stu-id="df9d8-114">Your program can examine its own metadata or the metadata in other programs by using reflection.</span></span> <span data-ttu-id="df9d8-115">Дополнительные сведения см. в разделе [Обращение к атрибутам с помощью отражения (C#)](accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="df9d8-115">For more information, see [Accessing Attributes by Using Reflection (C#)](accessing-attributes-by-using-reflection.md).</span></span>

## <a name="using-attributes"></a><span data-ttu-id="df9d8-116">Использование атрибутов</span><span class="sxs-lookup"><span data-stu-id="df9d8-116">Using attributes</span></span>

<span data-ttu-id="df9d8-117">Атрибуты можно использовать почти в любых объявлениях, но для каждого атрибута можно ограничить типы объявлений, в которых он является допустимым.</span><span class="sxs-lookup"><span data-stu-id="df9d8-117">Attributes can be placed on most any declaration, though a specific attribute might restrict the types of declarations on which it is valid.</span></span> <span data-ttu-id="df9d8-118">Чтобы указать атрибут на C#, поместите имя атрибута в квадратных скобках ([]) над объявлением сущности, к которой он применяется.</span><span class="sxs-lookup"><span data-stu-id="df9d8-118">In C#, you specify an attribute by placing the name of the attribute enclosed in square brackets ([]) above the declaration of the entity to which it applies.</span></span>

<span data-ttu-id="df9d8-119">В этом примере атрибут <xref:System.SerializableAttribute> используется для применения определенной характеристики к классу:</span><span class="sxs-lookup"><span data-stu-id="df9d8-119">In this example, the <xref:System.SerializableAttribute> attribute is used to apply a specific characteristic to a class:</span></span>

[!code-csharp[Using the serializable attribute](~/samples/snippets/csharp/attributes/AttributesOverview.cs#1)]

<span data-ttu-id="df9d8-120">Метод с атрибутом <xref:System.Runtime.InteropServices.DllImportAttribute> объявляется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="df9d8-120">A method with the attribute <xref:System.Runtime.InteropServices.DllImportAttribute> is declared like the following example:</span></span>

[!code-csharp[Declaring a method to import from an external library](../../../../../samples/snippets/csharp/attributes/AttributesOverview.cs#2)]

<span data-ttu-id="df9d8-121">В объявлении можно разместить несколько атрибутов, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="df9d8-121">More than one attribute can be placed on a declaration as the following example shows:</span></span>

[!code-csharp[Including the interop namespace](~/samples/snippets/csharp/attributes/AttributesOverview.cs#3)]
[!code-csharp[Declaring two way marshaling for arguments](~/samples/snippets/csharp/attributes/AttributesOverview.cs#4)]

<span data-ttu-id="df9d8-122">Некоторые атрибуты можно указать для одной сущности более одного раза.</span><span class="sxs-lookup"><span data-stu-id="df9d8-122">Some attributes can be specified more than once for a given entity.</span></span> <span data-ttu-id="df9d8-123">Пример такого многократно используемого атрибута — <xref:System.Diagnostics.ConditionalAttribute>:</span><span class="sxs-lookup"><span data-stu-id="df9d8-123">An example of such a multiuse attribute is <xref:System.Diagnostics.ConditionalAttribute>:</span></span>

[!code-csharp[Using the conditional attribute](~/samples/snippets/csharp/attributes/AttributesOverview.cs#5)]

> [!NOTE]
> <span data-ttu-id="df9d8-124">По соглашению все имена атрибутов заканчиваются словом Attribute, чтобы отличать их от других элементов библиотек .NET.</span><span class="sxs-lookup"><span data-stu-id="df9d8-124">By convention, all attribute names end with the word "Attribute" to distinguish them from other items in the .NET libraries.</span></span> <span data-ttu-id="df9d8-125">Но при использовании атрибута в коде этот суффикс можно не указывать.</span><span class="sxs-lookup"><span data-stu-id="df9d8-125">However, you do not need to specify the attribute suffix when using attributes in code.</span></span> <span data-ttu-id="df9d8-126">Например, обращение `[DllImport]` эквивалентно `[DllImportAttribute]`, хотя в библиотеке классов .NET Framework этот атрибут имеет имя `DllImportAttribute`.</span><span class="sxs-lookup"><span data-stu-id="df9d8-126">For example, `[DllImport]` is equivalent to `[DllImportAttribute]`, but `DllImportAttribute` is the attribute's actual name in the .NET Framework Class Library.</span></span>

### <a name="attribute-parameters"></a><span data-ttu-id="df9d8-127">Параметры атрибутов</span><span class="sxs-lookup"><span data-stu-id="df9d8-127">Attribute parameters</span></span>

<span data-ttu-id="df9d8-128">Многие атрибуты имеют параметры, которые могут быть позиционными, неименованными или именованными.</span><span class="sxs-lookup"><span data-stu-id="df9d8-128">Many attributes have parameters, which can be positional, unnamed, or named.</span></span> <span data-ttu-id="df9d8-129">Позиционные параметры должны указываться в определенном порядке и не могут опускаться.</span><span class="sxs-lookup"><span data-stu-id="df9d8-129">Any positional parameters must be specified in a certain order and cannot be omitted.</span></span> <span data-ttu-id="df9d8-130">Именованные параметры являются необязательными и могут указываться в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="df9d8-130">Named parameters are optional and can be specified in any order.</span></span> <span data-ttu-id="df9d8-131">Сначала указываются позиционные параметры.</span><span class="sxs-lookup"><span data-stu-id="df9d8-131">Positional parameters are specified first.</span></span> <span data-ttu-id="df9d8-132">Например, эти три атрибута являются эквивалентными:</span><span class="sxs-lookup"><span data-stu-id="df9d8-132">For example, these three attributes are equivalent:</span></span>

```csharp
[DllImport("user32.dll")]
[DllImport("user32.dll", SetLastError=false, ExactSpelling=false)]
[DllImport("user32.dll", ExactSpelling=false, SetLastError=false)]
```

<span data-ttu-id="df9d8-133">Первый параметр (имя библиотеки DLL) является позиционным и всегда располагается первым, остальные параметры являются именованными.</span><span class="sxs-lookup"><span data-stu-id="df9d8-133">The first parameter, the DLL name, is positional and always comes first; the others are named.</span></span> <span data-ttu-id="df9d8-134">В этом примере оба именованных параметра имеют значение по умолчанию (false), и мы можем их опустить.</span><span class="sxs-lookup"><span data-stu-id="df9d8-134">In this case, both named parameters default to false, so they can be omitted.</span></span> <span data-ttu-id="df9d8-135">Позиционные параметры соответствуют параметрам конструктора атрибутов.</span><span class="sxs-lookup"><span data-stu-id="df9d8-135">Positional parameters correspond to the parameters of the attribute constructor.</span></span> <span data-ttu-id="df9d8-136">Именованные (или необязательные) параметры соответствуют свойствам или полям атрибута.</span><span class="sxs-lookup"><span data-stu-id="df9d8-136">Named or optional parameters correspond to either properties or fields of the attribute.</span></span> <span data-ttu-id="df9d8-137">Сведения о значениях параметров по умолчанию указываются в документации по каждому отдельному атрибуту.</span><span class="sxs-lookup"><span data-stu-id="df9d8-137">Refer to the individual attribute's documentation for information on default parameter values.</span></span>

### <a name="attribute-targets"></a><span data-ttu-id="df9d8-138">Целевые объекты атрибутов</span><span class="sxs-lookup"><span data-stu-id="df9d8-138">Attribute targets</span></span>

<span data-ttu-id="df9d8-139">*Целевой объект* атрибута — это сущность, к которой применяется атрибут.</span><span class="sxs-lookup"><span data-stu-id="df9d8-139">The *target* of an attribute is the entity which the attribute applies to.</span></span> <span data-ttu-id="df9d8-140">Например, атрибут можно применить к классу, отдельному методу или ко всей сборке.</span><span class="sxs-lookup"><span data-stu-id="df9d8-140">For example, an attribute may apply to a class, a particular method, or an entire assembly.</span></span> <span data-ttu-id="df9d8-141">По умолчанию атрибут применяется к тому элементу, который следует за ним.</span><span class="sxs-lookup"><span data-stu-id="df9d8-141">By default, an attribute applies to the element that follows it.</span></span> <span data-ttu-id="df9d8-142">Но у вас есть возможность явным образом указать, например, что атрибут применяется к методу, параметру или возвращаемому значению.</span><span class="sxs-lookup"><span data-stu-id="df9d8-142">But you can also explicitly identify, for example, whether an attribute is applied to a method, or to its parameter, or to its return value.</span></span>

<span data-ttu-id="df9d8-143">Чтобы явным образом определить целевой объект атрибута, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="df9d8-143">To explicitly identify an attribute target, use the following syntax:</span></span>

```csharp
[target : attribute-list]
```

<span data-ttu-id="df9d8-144">Возможные значения `target` перечислены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="df9d8-144">The list of possible `target` values is shown in the following table.</span></span>

|<span data-ttu-id="df9d8-145">Целевое значение</span><span class="sxs-lookup"><span data-stu-id="df9d8-145">Target value</span></span>|<span data-ttu-id="df9d8-146">Применение</span><span class="sxs-lookup"><span data-stu-id="df9d8-146">Applies to</span></span>|
|------------------|----------------|
|`assembly`|<span data-ttu-id="df9d8-147">Вся сборка</span><span class="sxs-lookup"><span data-stu-id="df9d8-147">Entire assembly</span></span>|
|`module`|<span data-ttu-id="df9d8-148">Модуль текущей сборки</span><span class="sxs-lookup"><span data-stu-id="df9d8-148">Current assembly module</span></span>|
|`field`|<span data-ttu-id="df9d8-149">Поле в классе или структуре</span><span class="sxs-lookup"><span data-stu-id="df9d8-149">Field in a class or a struct</span></span>|
|`event`|<span data-ttu-id="df9d8-150">событие</span><span class="sxs-lookup"><span data-stu-id="df9d8-150">Event</span></span>|
|`method`|<span data-ttu-id="df9d8-151">Метод либо методы доступа к свойствам `get` и `set`</span><span class="sxs-lookup"><span data-stu-id="df9d8-151">Method or `get` and `set` property accessors</span></span>|
|`param`|<span data-ttu-id="df9d8-152">Параметры метода или параметры метода доступа `set`</span><span class="sxs-lookup"><span data-stu-id="df9d8-152">Method parameters or `set` property accessor parameters</span></span>|
|`property`|<span data-ttu-id="df9d8-153">Свойство.</span><span class="sxs-lookup"><span data-stu-id="df9d8-153">Property</span></span>|
|`return`|<span data-ttu-id="df9d8-154">Возвращаемое значение метода, индексатора свойства или метода доступа к свойствам `get`</span><span class="sxs-lookup"><span data-stu-id="df9d8-154">Return value of a method, property indexer, or `get` property accessor</span></span>|
|`type`|<span data-ttu-id="df9d8-155">Структура, класс, интерфейс, перечисление или делегат</span><span class="sxs-lookup"><span data-stu-id="df9d8-155">Struct, class, interface, enum, or delegate</span></span>|

<span data-ttu-id="df9d8-156">Следует указать целевое значение `field`, чтобы применить атрибут к резервной переменной, созданной для [автоматически реализуемого свойства](../../../properties.md).</span><span class="sxs-lookup"><span data-stu-id="df9d8-156">You would specify the `field` target value to apply an attribute to the backing field created for an [auto-implemented property](../../../properties.md).</span></span>

<span data-ttu-id="df9d8-157">Следующий пример демонстрирует, как применить атрибуты к сборкам и модулям.</span><span class="sxs-lookup"><span data-stu-id="df9d8-157">The following example shows how to apply attributes to assemblies and modules.</span></span> <span data-ttu-id="df9d8-158">Дополнительные сведения см. в разделе [Общие атрибуты (C#)](common-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="df9d8-158">For more information, see [Common Attributes (C#)](common-attributes.md).</span></span>

```csharp
using System;
using System.Reflection;
[assembly: AssemblyTitleAttribute("Production assembly 4")]
[module: CLSCompliant(true)]
```

<span data-ttu-id="df9d8-159">В следующем примере показано, как применять атрибуты к методам, параметрам и возвращаемым значениям методов в C#.</span><span class="sxs-lookup"><span data-stu-id="df9d8-159">The following example shows how to apply attributes to methods, method parameters, and method return values in C#.</span></span>

[!code-csharp[Applying attributes to different code elements](../../../../../samples/snippets/csharp/attributes/AttributesOverview.cs#6)]

> [!NOTE]
> <span data-ttu-id="df9d8-160">Вне зависимости от целевых объектов, для которых действует атрибут `ValidatedContract`, необходимо задать целевой объект для `return`, даже если атрибут `ValidatedContract` назначен только возвращаемым значениям.</span><span class="sxs-lookup"><span data-stu-id="df9d8-160">Regardless of the targets on which `ValidatedContract` is defined to be valid, the `return` target has to be specified, even if `ValidatedContract` were defined to apply only to return values.</span></span> <span data-ttu-id="df9d8-161">Другими словами, компилятор не будет использовать сведения `AttributeUsage` для разрешения конфликтов между неоднозначными целевыми объектами атрибута.</span><span class="sxs-lookup"><span data-stu-id="df9d8-161">In other words, the compiler will not use `AttributeUsage` information to resolve ambiguous attribute targets.</span></span> <span data-ttu-id="df9d8-162">Подробнее см. в разделе [AttributeUsage (C#)](attributeusage.md).</span><span class="sxs-lookup"><span data-stu-id="df9d8-162">For more information, see [AttributeUsage (C#)](attributeusage.md).</span></span>

## <a name="common-uses-for-attributes"></a><span data-ttu-id="df9d8-163">Популярные методы применения атрибутов</span><span class="sxs-lookup"><span data-stu-id="df9d8-163">Common uses for attributes</span></span>

<span data-ttu-id="df9d8-164">В следующем списке перечислены несколько распространенных применений для атрибутов.</span><span class="sxs-lookup"><span data-stu-id="df9d8-164">The following list includes a few of the common uses of attributes in code:</span></span>

- <span data-ttu-id="df9d8-165">Указание для методов в веб-службах атрибута `WebMethod`, который обозначает, что метод должен вызываться по протоколу SOAP.</span><span class="sxs-lookup"><span data-stu-id="df9d8-165">Marking methods using the `WebMethod` attribute in Web services to indicate that the method should be callable over the SOAP protocol.</span></span> <span data-ttu-id="df9d8-166">Дополнительные сведения можно найти по адресу: <xref:System.Web.Services.WebMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="df9d8-166">For more information, see <xref:System.Web.Services.WebMethodAttribute>.</span></span>
- <span data-ttu-id="df9d8-167">Описание способов упаковки параметров методов при взаимодействии с машинным кодом.</span><span class="sxs-lookup"><span data-stu-id="df9d8-167">Describing how to marshal method parameters when interoperating with native code.</span></span> <span data-ttu-id="df9d8-168">Дополнительные сведения можно найти по адресу: <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="df9d8-168">For more information, see <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>
- <span data-ttu-id="df9d8-169">Описание свойств COM для классов, методов и интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="df9d8-169">Describing the COM properties for classes, methods, and interfaces.</span></span>
- <span data-ttu-id="df9d8-170">Вызов неуправляемого кода с помощью класса <xref:System.Runtime.InteropServices.DllImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="df9d8-170">Calling unmanaged code using the <xref:System.Runtime.InteropServices.DllImportAttribute> class.</span></span>
- <span data-ttu-id="df9d8-171">Указание для сборки таких параметров, как заголовок, версия, описание или товарный знак.</span><span class="sxs-lookup"><span data-stu-id="df9d8-171">Describing your assembly in terms of title, version, description, or trademark.</span></span>
- <span data-ttu-id="df9d8-172">Указание членов класса, которые будут сериализованы при сохранении класса.</span><span class="sxs-lookup"><span data-stu-id="df9d8-172">Describing which members of a class to serialize for persistence.</span></span>
- <span data-ttu-id="df9d8-173">Описание правил сопоставления членов класса с XML-узлами при XML-сериализации.</span><span class="sxs-lookup"><span data-stu-id="df9d8-173">Describing how to map between class members and XML nodes for XML serialization.</span></span>
- <span data-ttu-id="df9d8-174">Описание требований безопасности для методов.</span><span class="sxs-lookup"><span data-stu-id="df9d8-174">Describing the security requirements for methods.</span></span>
- <span data-ttu-id="df9d8-175">Указание характеристик, используемых для обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="df9d8-175">Specifying characteristics used to enforce security.</span></span>
- <span data-ttu-id="df9d8-176">Управление оптимизацией для JIT-компилятора, сохраняя при этом простоту отладки кода.</span><span class="sxs-lookup"><span data-stu-id="df9d8-176">Controlling optimizations by the just-in-time (JIT) compiler so the code remains easy to debug.</span></span>
- <span data-ttu-id="df9d8-177">Получение сведений об объекте, вызывающем метод.</span><span class="sxs-lookup"><span data-stu-id="df9d8-177">Obtaining information about the caller to a method.</span></span>

## <a name="related-sections"></a><span data-ttu-id="df9d8-178">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="df9d8-178">Related sections</span></span>

<span data-ttu-id="df9d8-179">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="df9d8-179">For more information, see:</span></span>

- [<span data-ttu-id="df9d8-180">Создание настраиваемых атрибутов (C#)</span><span class="sxs-lookup"><span data-stu-id="df9d8-180">Creating Custom Attributes (C#)</span></span>](creating-custom-attributes.md)  
- [<span data-ttu-id="df9d8-181">Обращение к атрибутам с помощью отражения (C#)</span><span class="sxs-lookup"><span data-stu-id="df9d8-181">Accessing Attributes by Using Reflection (C#)</span></span>](accessing-attributes-by-using-reflection.md)  
- [<span data-ttu-id="df9d8-182">Практическое руководство. Создание объединения C/C++ с помощью атрибутов (C#)</span><span class="sxs-lookup"><span data-stu-id="df9d8-182">How to create a C/C++ union by using attributes (C#)</span></span>](how-to-create-a-c-cpp-union-by-using-attributes.md)  
- [<span data-ttu-id="df9d8-183">Общие атрибуты (C#)</span><span class="sxs-lookup"><span data-stu-id="df9d8-183">Common Attributes (C#)</span></span>](common-attributes.md)  
- <span data-ttu-id="df9d8-184">[Caller Information (C#)](../caller-information.md) (Сведения о вызывающем объекте (C#))</span><span class="sxs-lookup"><span data-stu-id="df9d8-184">[Caller Information (C#)](../caller-information.md)</span></span>  

## <a name="see-also"></a><span data-ttu-id="df9d8-185">См. также</span><span class="sxs-lookup"><span data-stu-id="df9d8-185">See also</span></span>

- [<span data-ttu-id="df9d8-186">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="df9d8-186">C# Programming Guide</span></span>](../../index.md)
- <span data-ttu-id="df9d8-187">[Reflection (C#)](../reflection.md) (Отражение (C#))</span><span class="sxs-lookup"><span data-stu-id="df9d8-187">[Reflection (C#)](../reflection.md)</span></span>
- [<span data-ttu-id="df9d8-188">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="df9d8-188">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="df9d8-189">Использование атрибутов в C#</span><span class="sxs-lookup"><span data-stu-id="df9d8-189">Using Attributes in C#</span></span>](../../../tutorials/attributes.md)
