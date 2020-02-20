---
title: Атрибуты
description: Узнайте, F# как атрибуты позволяют применять метаданные к конструкции программирования.
ms.date: 05/16/2016
ms.openlocfilehash: 1e42dc61d44f31930a7b34799f28a68a2db69c8c
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504115"
---
# <a name="attributes"></a><span data-ttu-id="08aa5-103">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="08aa5-103">Attributes</span></span>

<span data-ttu-id="08aa5-104">Атрибуты позволяют применять метаданные к конструкции программирования.</span><span class="sxs-lookup"><span data-stu-id="08aa5-104">Attributes enable metadata to be applied to a programming construct.</span></span>

## <a name="syntax"></a><span data-ttu-id="08aa5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08aa5-105">Syntax</span></span>

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a><span data-ttu-id="08aa5-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="08aa5-106">Remarks</span></span>

<span data-ttu-id="08aa5-107">В предыдущем синтаксисе *целевой объект* является необязательным и, если он есть, указывает тип сущности программы, к которой применяется атрибут.</span><span class="sxs-lookup"><span data-stu-id="08aa5-107">In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to.</span></span> <span data-ttu-id="08aa5-108">Допустимые значения для *Target* показаны в таблице ниже в этом документе.</span><span class="sxs-lookup"><span data-stu-id="08aa5-108">Valid values for *target* are shown in the table that appears later in this document.</span></span>

<span data-ttu-id="08aa5-109">*Имя атрибута —* это имя (возможно, дополненное пространствами имен) допустимого типа атрибута с суффиксом или без него `Attribute`, который обычно используется в именах типов атрибутов.</span><span class="sxs-lookup"><span data-stu-id="08aa5-109">The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix `Attribute` that is usually used in attribute type names.</span></span> <span data-ttu-id="08aa5-110">Например, тип `ObsoleteAttribute` можно сократить, чтобы просто `Obsolete` в этом контексте.</span><span class="sxs-lookup"><span data-stu-id="08aa5-110">For example, the type `ObsoleteAttribute` can be shortened to just `Obsolete` in this context.</span></span>

<span data-ttu-id="08aa5-111">*Аргументы* являются аргументами конструктора для типа атрибута.</span><span class="sxs-lookup"><span data-stu-id="08aa5-111">The *arguments* are the arguments to the constructor for the attribute type.</span></span> <span data-ttu-id="08aa5-112">Если атрибут имеет конструктор без параметров, список аргументов и круглые скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="08aa5-112">If an attribute has a parameterless constructor, the argument list and parentheses can be omitted.</span></span> <span data-ttu-id="08aa5-113">Атрибуты поддерживают как аргументы, так и именованные аргументы.</span><span class="sxs-lookup"><span data-stu-id="08aa5-113">Attributes support both positional arguments and named arguments.</span></span> <span data-ttu-id="08aa5-114">*Позиционированные аргументы* — это аргументы, которые используются в том порядке, в котором они отображаются.</span><span class="sxs-lookup"><span data-stu-id="08aa5-114">*Positional arguments* are arguments that are used in the order in which they appear.</span></span> <span data-ttu-id="08aa5-115">Именованные аргументы можно использовать, если атрибут имеет открытые свойства.</span><span class="sxs-lookup"><span data-stu-id="08aa5-115">Named arguments can be used if the attribute has public properties.</span></span> <span data-ttu-id="08aa5-116">Эти значения можно задать с помощью следующего синтаксиса в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="08aa5-116">You can set these by using the following syntax in the argument list.</span></span>

```fsharp
property-name = property-value
```

<span data-ttu-id="08aa5-117">Такие инициализации свойств могут быть в любом порядке, но они должны следовать любым запозиционированным аргументам.</span><span class="sxs-lookup"><span data-stu-id="08aa5-117">Such property initializations can be in any order, but they must follow any positional arguments.</span></span> <span data-ttu-id="08aa5-118">Ниже приведен пример атрибута, в котором используются позиционированные аргументы и инициализации свойств.</span><span class="sxs-lookup"><span data-stu-id="08aa5-118">The following is an example of an attribute that uses positional arguments and property initializations:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

<span data-ttu-id="08aa5-119">В этом примере атрибут имеет значение `DllImportAttribute`, который используется в сокращенной форме.</span><span class="sxs-lookup"><span data-stu-id="08aa5-119">In this example, the attribute is `DllImportAttribute`, here used in shortened form.</span></span> <span data-ttu-id="08aa5-120">Первый аргумент — это параметр с позиционированием, а второй — свойством.</span><span class="sxs-lookup"><span data-stu-id="08aa5-120">The first argument is a positional parameter and the second is a property.</span></span>

<span data-ttu-id="08aa5-121">Атрибуты — это конструкция программирования .NET, которая позволяет объекту, известному как *атрибут* , быть связанным с типом или другим программным элементом.</span><span class="sxs-lookup"><span data-stu-id="08aa5-121">Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element.</span></span> <span data-ttu-id="08aa5-122">Элемент Program, к которому применяется атрибут, называется *целевым объектом атрибута*.</span><span class="sxs-lookup"><span data-stu-id="08aa5-122">The program element to which an attribute is applied is known as the *attribute target*.</span></span> <span data-ttu-id="08aa5-123">Атрибут обычно содержит метаданные о своем целевом объекте.</span><span class="sxs-lookup"><span data-stu-id="08aa5-123">The attribute usually contains metadata about its target.</span></span> <span data-ttu-id="08aa5-124">В этом контексте метаданные могут быть любыми данными о типе, отличном от его полей и членов.</span><span class="sxs-lookup"><span data-stu-id="08aa5-124">In this context, metadata could be any data about the type other than its fields and members.</span></span>

<span data-ttu-id="08aa5-125">Атрибуты в F# могут применяться к следующим конструкциям программирования: функциям, методам, сборкам, модулям, типам (классам, записям, структурам, интерфейсам, делегатам, перечислениям, объединениям и т. д.), конструкторам, свойствам, полям, параметрам, параметрам типа и возвращаемым значениям.</span><span class="sxs-lookup"><span data-stu-id="08aa5-125">Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values.</span></span> <span data-ttu-id="08aa5-126">Атрибуты не допускаются в привязках `let` в классах, выражениях или выражениях рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="08aa5-126">Attributes are not allowed on `let` bindings inside classes, expressions, or workflow expressions.</span></span>

<span data-ttu-id="08aa5-127">Как правило, объявление атрибута отображается непосредственно перед объявлением целевого объекта атрибута.</span><span class="sxs-lookup"><span data-stu-id="08aa5-127">Typically, the attribute declaration appears directly before the declaration of the attribute target.</span></span> <span data-ttu-id="08aa5-128">Несколько объявлений атрибутов можно использовать вместе следующим образом:</span><span class="sxs-lookup"><span data-stu-id="08aa5-128">Multiple attribute declarations can be used together, as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

<span data-ttu-id="08aa5-129">Вы можете запрашивать атрибуты во время выполнения с помощью отражения .NET.</span><span class="sxs-lookup"><span data-stu-id="08aa5-129">You can query attributes at run time by using .NET reflection.</span></span>

<span data-ttu-id="08aa5-130">Можно объявить несколько атрибутов по отдельности, как в предыдущем примере кода, или можно объявить их в одном наборе квадратных скобок, если использовать точку с запятой для разделения отдельных атрибутов и конструкторов следующим образом:</span><span class="sxs-lookup"><span data-stu-id="08aa5-130">You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

<span data-ttu-id="08aa5-131">Обычно такие атрибуты включают атрибут `Obsolete`, атрибуты для обеспечения безопасности, атрибуты для поддержки COM, атрибуты, относящиеся к владению кодом, и атрибуты, указывающие, можно ли сериализовать тип.</span><span class="sxs-lookup"><span data-stu-id="08aa5-131">Typically encountered attributes include the `Obsolete` attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized.</span></span> <span data-ttu-id="08aa5-132">В следующем примере демонстрируется использование атрибута `Obsolete`.</span><span class="sxs-lookup"><span data-stu-id="08aa5-132">The following example demonstrates the use of the `Obsolete` attribute.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

<span data-ttu-id="08aa5-133">Для целевых объектов атрибута `assembly` и `module`атрибуты применяются к привязке `do` верхнего уровня в сборке.</span><span class="sxs-lookup"><span data-stu-id="08aa5-133">For the attribute targets `assembly` and `module`, you apply the attributes to a top-level `do` binding in your assembly.</span></span> <span data-ttu-id="08aa5-134">В объявление атрибута можно включить слово `assembly` или `module` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="08aa5-134">You can include the word `assembly` or `module` in the attribute declaration, as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

<span data-ttu-id="08aa5-135">Если опустить атрибут Target для атрибута, применяемого к привязке `do`, F# компилятор пытается определить целевой объект атрибута, который имеет смысл для этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="08aa5-135">If you omit the attribute target for an attribute applied to a `do` binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute.</span></span> <span data-ttu-id="08aa5-136">Многие классы атрибутов имеют атрибут типа `System.AttributeUsageAttribute`, который содержит сведения о возможных целевых объектах, поддерживаемых для этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="08aa5-136">Many attribute classes have an attribute of type `System.AttributeUsageAttribute` that includes information about the possible targets supported for that attribute.</span></span> <span data-ttu-id="08aa5-137">Если `System.AttributeUsageAttribute` указывает, что атрибут поддерживает функции в качестве целевых объектов, то атрибут применяется к главной точке входа программы.</span><span class="sxs-lookup"><span data-stu-id="08aa5-137">If the `System.AttributeUsageAttribute` indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program.</span></span> <span data-ttu-id="08aa5-138">Если `System.AttributeUsageAttribute` указывает, что атрибут поддерживает сборки в качестве целевых объектов, компилятор принимает атрибут для применения к сборке.</span><span class="sxs-lookup"><span data-stu-id="08aa5-138">If the `System.AttributeUsageAttribute` indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly.</span></span> <span data-ttu-id="08aa5-139">Большинство атрибутов не применяются к функциям и сборкам, но в тех случаях, когда они делают, применяется атрибут для применения к функции Main программы.</span><span class="sxs-lookup"><span data-stu-id="08aa5-139">Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function.</span></span> <span data-ttu-id="08aa5-140">Если целевой объект атрибута указан явно, атрибут применяется к указанному целевому объекту.</span><span class="sxs-lookup"><span data-stu-id="08aa5-140">If the attribute target is specified explicitly, the attribute is applied to the specified target.</span></span>

<span data-ttu-id="08aa5-141">Хотя обычно не требуется явно указывать целевой объект атрибута, допустимые значения для *Target* в атрибуте вместе с примерами использования показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="08aa5-141">Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute along with examples of usage are shown in the following table:</span></span>

<table>
  <tr>
    <th><span data-ttu-id="08aa5-142">Целевой объект атрибута</span><span class="sxs-lookup"><span data-stu-id="08aa5-142">Attribute target</span></span></td>
    <th><span data-ttu-id="08aa5-143">Пример</span><span class="sxs-lookup"><span data-stu-id="08aa5-143">Example</span></span></td>
  </tr>
  <tr>
    <td><span data-ttu-id="08aa5-144">сборка</span><span class="sxs-lookup"><span data-stu-id="08aa5-144">assembly</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;assembly: AssemblyVersionAttribute("1.0.0.0")&gt;]</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="08aa5-145">return</span><span class="sxs-lookup"><span data-stu-id="08aa5-145">return</span></span></td>
    <td><pre lang="fsharp"><code>let function1 x : [&lt;return: Obsolete&gt;] int = x + 1</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="08aa5-146">поле</span><span class="sxs-lookup"><span data-stu-id="08aa5-146">field</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;field: DefaultValue&gt;] val mutable x: int</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="08aa5-147">свойство;</span><span class="sxs-lookup"><span data-stu-id="08aa5-147">property</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;property: Obsolete&gt;] this.MyProperty = x</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="08aa5-148">param</span><span class="sxs-lookup"><span data-stu-id="08aa5-148">param</span></span></td>
    <td><pre lang="fsharp"><code>member this.MyMethod([&lt;param: Out&gt;] x : ref&lt;int&gt;) = x := 10</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="08aa5-149">тип</span><span class="sxs-lookup"><span data-stu-id="08aa5-149">type</span></span></td>
    <td>
        <pre lang="fsharp"><code>
[&lt;type: StructLayout(LayoutKind.Sequential)&gt;]
type MyStruct =
  struct
    val x : byte
    val y : int
  end</code></pre>
    </td>
  </tr>
</table>

## <a name="see-also"></a><span data-ttu-id="08aa5-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="08aa5-150">See also</span></span>

- [<span data-ttu-id="08aa5-151">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="08aa5-151">F# Language Reference</span></span>](index.md)
