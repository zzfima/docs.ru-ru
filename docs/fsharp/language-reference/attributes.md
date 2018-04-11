---
title: Атрибуты (F#)
description: 'Узнайте, как атрибуты F # включить метаданные, применяемые к конструкции программирования.'
keywords: visual f#, f#, функциональное программирование
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 95c001e6-3708-4d04-a850-d855f78eb51e
ms.openlocfilehash: 88098e51d19a86f501c35abe3408524378f147b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="attributes"></a><span data-ttu-id="f2c7d-104">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f2c7d-104">Attributes</span></span>

<span data-ttu-id="f2c7d-105">Атрибуты позволяют метаданные для применения к конструкции программирования.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-105">Attributes enable metadata to be applied to a programming construct.</span></span>

## <a name="syntax"></a><span data-ttu-id="f2c7d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2c7d-106">Syntax</span></span>

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a><span data-ttu-id="f2c7d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f2c7d-107">Remarks</span></span>

<span data-ttu-id="f2c7d-108">В предыдущем синтаксисе *целевой* является необязательным и, если он имеется, указывает тип сущности программы, к которому применяется атрибут.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-108">In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to.</span></span> <span data-ttu-id="f2c7d-109">Допустимые значения для *целевой* приведены в таблице, который приводится далее в этом документе.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-109">Valid values for *target* are shown in the table that appears later in this document.</span></span>

<span data-ttu-id="f2c7d-110">*Имя атрибута* ссылается на имя (возможно, дополненное пространствами имен) допустимый атрибут типа, с или без суффикса `Attribute` , обычно используется в именах типов атрибутов.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-110">The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix `Attribute` that is usually used in attribute type names.</span></span> <span data-ttu-id="f2c7d-111">Например, тип `ObsoleteAttribute` может быть сокращено до `Obsolete` в данном контексте.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-111">For example, the type `ObsoleteAttribute` can be shortened to just `Obsolete` in this context.</span></span>

<span data-ttu-id="f2c7d-112">*Аргументы* аргументы в конструктор для типа атрибута.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-112">The *arguments* are the arguments to the constructor for the attribute type.</span></span> <span data-ttu-id="f2c7d-113">Если атрибут содержит конструктор по умолчанию, можно опустить список аргументов и круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-113">If an attribute has a default constructor, the argument list and parentheses can be omitted.</span></span> <span data-ttu-id="f2c7d-114">Атрибуты поддерживают позиционные аргументы и именованные аргументы.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-114">Attributes support both positional arguments and named arguments.</span></span> <span data-ttu-id="f2c7d-115">*Позиционные аргументы* являются аргументами, которые используются в том порядке, в котором они отображаются.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-115">*Positional arguments* are arguments that are used in the order in which they appear.</span></span> <span data-ttu-id="f2c7d-116">Можно использовать именованные аргументы, если атрибут имеет открытые свойства.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-116">Named arguments can be used if the attribute has public properties.</span></span> <span data-ttu-id="f2c7d-117">Можно задать эти значения можно, используя следующий синтаксис в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-117">You can set these by using the following syntax in the argument list.</span></span>

```
*property-name* = *property-value*
```

<span data-ttu-id="f2c7d-118">Такие инициализации свойств могут быть в любом порядке, но они должны следовать все позиционные аргументы.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-118">Such property initializations can be in any order, but they must follow any positional arguments.</span></span> <span data-ttu-id="f2c7d-119">Ниже приведен пример, использующий позиционные аргументы и инициализации свойства атрибута.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-119">Following is an example of an attribute that uses positional arguments and property initializations.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

<span data-ttu-id="f2c7d-120">В этом примере — атрибут `DllImportAttribute`, используется здесь в сокращенной форме.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-120">In this example, the attribute is `DllImportAttribute`, here used in shortened form.</span></span> <span data-ttu-id="f2c7d-121">Первым аргументом является позиционным параметром, а второй — это свойство.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-121">The first argument is a positional parameter and the second is a property.</span></span>

<span data-ttu-id="f2c7d-122">Атрибуты являются конструкции программирования .NET, которая позволяет объект, известный как *атрибута* необходимо сопоставить с типом или других программных элементов.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-122">Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element.</span></span> <span data-ttu-id="f2c7d-123">Элемент программы, к которому применяется атрибут называется *целевой атрибут*.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-123">The program element to which an attribute is applied is known as the *attribute target*.</span></span> <span data-ttu-id="f2c7d-124">Атрибут обычно содержит метаданные о своей цели.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-124">The attribute usually contains metadata about its target.</span></span> <span data-ttu-id="f2c7d-125">В этом контексте метаданные могут быть любые данные о типе, отличные от его полей и членов.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-125">In this context, metadata could be any data about the type other than its fields and members.</span></span>

<span data-ttu-id="f2c7d-126">Атрибуты в языке F # может применяться к следующим конструкциям программирования: функции, методы, сборок, модулей, типов (классы, записи, структуры, интерфейсы, делегаты, перечисления, объединения и т. д), конструкторы, свойства, поля, параметры, Введите параметры и возвращаемые значения.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-126">Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values.</span></span> <span data-ttu-id="f2c7d-127">Атрибуты не допускаются в `let` привязок внутри классов, выражений и выражений рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-127">Attributes are not allowed on `let` bindings inside classes, expressions, or workflow expressions.</span></span>

<span data-ttu-id="f2c7d-128">Как правило объявление атрибута появляется непосредственно перед объявлением конечного объекта атрибута.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-128">Typically, the attribute declaration appears directly before the declaration of the attribute target.</span></span> <span data-ttu-id="f2c7d-129">Несколько объявлений атрибутов можно использовать вместе, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-129">Multiple attribute declarations can be used together, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

<span data-ttu-id="f2c7d-130">Атрибуты можно запрашивать во время выполнения с помощью отражения .NET.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-130">You can query attributes at run time by using .NET reflection.</span></span>

<span data-ttu-id="f2c7d-131">Несколько атрибутов можно объявить по отдельности, как показано в предыдущем примере, или можно объявлять их в одном наборе скобок Если используйте точку с запятой для разделения отдельных атрибутов и конструкторов, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-131">You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as shown here.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

<span data-ttu-id="f2c7d-132">Обычно встречаются следующие атрибуты: `Obsolete` атрибут атрибуты для обеспечения безопасности, атрибуты для поддержки COM, атрибуты, связанные с владельцем код и атрибуты, указывающее, можно ли сериализовать тип.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-132">Typically encountered attributes include the `Obsolete` attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized.</span></span> <span data-ttu-id="f2c7d-133">В следующем примере показано использование `Obsolete` атрибута.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-133">The following example demonstrates the use of the `Obsolete` attribute.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

<span data-ttu-id="f2c7d-134">Для целевых объектов атрибута `assembly` и `module`, можно применить атрибуты верхнего уровня `do` привязки сборки.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-134">For the attribute targets `assembly` and `module`, you apply the attributes to a top-level `do` binding in your assembly.</span></span> <span data-ttu-id="f2c7d-135">Можно включить слово `assembly` или `module` в объявление атрибута, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-135">You can include the word `assembly` or `module` in the attribute declaration, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

<span data-ttu-id="f2c7d-136">Если не указывать целевой атрибут для атрибута, примененного к `do` привязки, компилятор F # пытается определить целевой объект атрибута, который имеет смысл для этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-136">If you omit the attribute target for an attribute applied to a `do` binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute.</span></span> <span data-ttu-id="f2c7d-137">Многие классы атрибутов имеют атрибут типа `System.AttributeUsageAttribute` , включает информацию о возможных целевых объектах, поддерживаемых для этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-137">Many attribute classes have an attribute of type `System.AttributeUsageAttribute` that includes information about the possible targets supported for that attribute.</span></span> <span data-ttu-id="f2c7d-138">Если `System.AttributeUsageAttribute` указывает, что атрибут поддерживает функции в качестве целевых объектов, этот атрибут выбирается для применения к Главная точка входа программы.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-138">If the `System.AttributeUsageAttribute` indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program.</span></span> <span data-ttu-id="f2c7d-139">Если `System.AttributeUsageAttribute` указывает, что атрибут поддерживает сборки в качестве целевых объектов, компилятор выбирает атрибут, чтобы применить к сборке.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-139">If the `System.AttributeUsageAttribute` indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly.</span></span> <span data-ttu-id="f2c7d-140">Большинство атрибутов не применяются к функции и сборок, но в случаях, когда это делается, атрибут выбирается для применения к основной функции программы.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-140">Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function.</span></span> <span data-ttu-id="f2c7d-141">Если целевой атрибут указан явно, атрибут с указанным целевым объектом.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-141">If the attribute target is specified explicitly, the attribute is applied to the specified target.</span></span>

<span data-ttu-id="f2c7d-142">Несмотря на то, что вы обычно не требуется задать целевой объект атрибута явно, допустимыми значениями для *целевой* в атрибуте показаны в следующей таблице, а также примеры использования.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-142">Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute are shown in the following table, along with examples of usage.</span></span>

<table>
  <tr>
    <th><span data-ttu-id="f2c7d-143">Целевой атрибут</span><span class="sxs-lookup"><span data-stu-id="f2c7d-143">Attribute target</span></span></td>
    <th><span data-ttu-id="f2c7d-144">Пример</span><span class="sxs-lookup"><span data-stu-id="f2c7d-144">Example</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="f2c7d-145">сборка</span><span class="sxs-lookup"><span data-stu-id="f2c7d-145">assembly</span></span></td>
    <td><span data-ttu-id="f2c7d-146">`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</span><span class="sxs-lookup"><span data-stu-id="f2c7d-146">`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="f2c7d-147">return</span><span class="sxs-lookup"><span data-stu-id="f2c7d-147">return</span></span></td>
    <td><span data-ttu-id="f2c7d-148">"функция1 let x: [<return: Obsolete>] int = x + 1'</span><span class="sxs-lookup"><span data-stu-id="f2c7d-148">`let function1 x : [<return: Obsolete>] int = x + 1`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="f2c7d-149">поле</span><span class="sxs-lookup"><span data-stu-id="f2c7d-149">field</span></span></td>
    <td><span data-ttu-id="f2c7d-150">"[<field: DefaultValue>] val mutable x: int"</span><span class="sxs-lookup"><span data-stu-id="f2c7d-150">`[<field: DefaultValue>] val mutable x: int`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="f2c7d-151">свойство;</span><span class="sxs-lookup"><span data-stu-id="f2c7d-151">property</span></span></td>
    <td><span data-ttu-id="f2c7d-152">"[<property: Obsolete>] это. MyProperty = x "</span><span class="sxs-lookup"><span data-stu-id="f2c7d-152">`[<property: Obsolete>] this.MyProperty = x`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="f2c7d-153">Param</span><span class="sxs-lookup"><span data-stu-id="f2c7d-153">param</span></span></td>
    <td><span data-ttu-id="f2c7d-154">"член это. MyMethod ([<param: Out>] x: ref<int>) = x: = 10".</span><span class="sxs-lookup"><span data-stu-id="f2c7d-154">`member this.MyMethod([<param: Out>] x : ref<int>) = x := 10`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="f2c7d-155">type</span><span class="sxs-lookup"><span data-stu-id="f2c7d-155">type</span></span></td>
    <td><span data-ttu-id="f2c7d-156">
        ```
        [<type: StructLayout(Sequential)>] введите MyStruct = struct x: y байтов: int end```
    </span><span class="sxs-lookup"><span data-stu-id="f2c7d-156">
        ```
        [<type: StructLayout(Sequential)>] type MyStruct = struct x : byte y : int end ```
    </span></span></td> 
  </tr>
</table>

## <a name="see-also"></a><span data-ttu-id="f2c7d-157">См. также</span><span class="sxs-lookup"><span data-stu-id="f2c7d-157">See Also</span></span>

[<span data-ttu-id="f2c7d-158">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="f2c7d-158">F# Language Reference</span></span>](index.md)
