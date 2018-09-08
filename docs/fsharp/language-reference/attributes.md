---
title: Атрибуты (F#)
description: 'Узнайте, как F # атрибуты позволяют применять к программным конструкциям метаданные.'
ms.date: 05/16/2016
ms.openlocfilehash: 3e7f1d0ff383e1070b3db72e633f80ea37150548
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44207438"
---
# <a name="attributes"></a><span data-ttu-id="8e56e-103">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8e56e-103">Attributes</span></span>

<span data-ttu-id="8e56e-104">Атрибуты позволяют применять к программным конструкциям метаданные.</span><span class="sxs-lookup"><span data-stu-id="8e56e-104">Attributes enable metadata to be applied to a programming construct.</span></span>

## <a name="syntax"></a><span data-ttu-id="8e56e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e56e-105">Syntax</span></span>

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a><span data-ttu-id="8e56e-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="8e56e-106">Remarks</span></span>

<span data-ttu-id="8e56e-107">В приведенном выше синтаксисе *целевой* является необязательным и, если он присутствует, указывает тип сущности программы, к которому применяется атрибут.</span><span class="sxs-lookup"><span data-stu-id="8e56e-107">In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to.</span></span> <span data-ttu-id="8e56e-108">Допустимые значения для *целевой* приведены в таблице, который приводится далее в этом документе.</span><span class="sxs-lookup"><span data-stu-id="8e56e-108">Valid values for *target* are shown in the table that appears later in this document.</span></span>

<span data-ttu-id="8e56e-109">*Имя атрибута* ссылается на (возможно полное с пространствами имен) имя допустимого атрибута типа, с или без суффикса `Attribute` , обычно используется в именах типов атрибутов.</span><span class="sxs-lookup"><span data-stu-id="8e56e-109">The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix `Attribute` that is usually used in attribute type names.</span></span> <span data-ttu-id="8e56e-110">Например, тип `ObsoleteAttribute` может быть сокращено до `Obsolete` в данном контексте.</span><span class="sxs-lookup"><span data-stu-id="8e56e-110">For example, the type `ObsoleteAttribute` can be shortened to just `Obsolete` in this context.</span></span>

<span data-ttu-id="8e56e-111">*Аргументы* аргументы в конструктор для типа атрибута.</span><span class="sxs-lookup"><span data-stu-id="8e56e-111">The *arguments* are the arguments to the constructor for the attribute type.</span></span> <span data-ttu-id="8e56e-112">Если атрибут имеет конструктор по умолчанию, можно опустить список аргументов и круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="8e56e-112">If an attribute has a default constructor, the argument list and parentheses can be omitted.</span></span> <span data-ttu-id="8e56e-113">Атрибуты поддерживают позиционные аргументы и именованные аргументы.</span><span class="sxs-lookup"><span data-stu-id="8e56e-113">Attributes support both positional arguments and named arguments.</span></span> <span data-ttu-id="8e56e-114">*Позиционные аргументы* являются аргументами, которые используются в порядке, в котором они появляются.</span><span class="sxs-lookup"><span data-stu-id="8e56e-114">*Positional arguments* are arguments that are used in the order in which they appear.</span></span> <span data-ttu-id="8e56e-115">Именованные аргументы можно использовать, если атрибут содержит открытые свойства.</span><span class="sxs-lookup"><span data-stu-id="8e56e-115">Named arguments can be used if the attribute has public properties.</span></span> <span data-ttu-id="8e56e-116">Можно задать с помощью следующего синтаксиса в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="8e56e-116">You can set these by using the following syntax in the argument list.</span></span>

```
*property-name* = *property-value*
```

<span data-ttu-id="8e56e-117">Такие инициализации свойств можно в любом порядке, но они должны следовать позиционные аргументы.</span><span class="sxs-lookup"><span data-stu-id="8e56e-117">Such property initializations can be in any order, but they must follow any positional arguments.</span></span> <span data-ttu-id="8e56e-118">Ниже приведен пример атрибута, которые используются позиционные аргументы и инициализации свойств.</span><span class="sxs-lookup"><span data-stu-id="8e56e-118">Following is an example of an attribute that uses positional arguments and property initializations.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

<span data-ttu-id="8e56e-119">В этом примере атрибут имеет `DllImportAttribute`, здесь используется в сокращенной форме.</span><span class="sxs-lookup"><span data-stu-id="8e56e-119">In this example, the attribute is `DllImportAttribute`, here used in shortened form.</span></span> <span data-ttu-id="8e56e-120">Первым аргументом является позиционным параметром, а второй — это свойство.</span><span class="sxs-lookup"><span data-stu-id="8e56e-120">The first argument is a positional parameter and the second is a property.</span></span>

<span data-ttu-id="8e56e-121">Атрибуты, конструкции программирования .NET, которая позволяет объект, известный как *атрибут* необходимо сопоставить с типом или других программных элементов.</span><span class="sxs-lookup"><span data-stu-id="8e56e-121">Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element.</span></span> <span data-ttu-id="8e56e-122">Элемент программы, к которому применяется атрибут называется *конечного объекта атрибута*.</span><span class="sxs-lookup"><span data-stu-id="8e56e-122">The program element to which an attribute is applied is known as the *attribute target*.</span></span> <span data-ttu-id="8e56e-123">Атрибут обычно содержит метаданные о своей цели.</span><span class="sxs-lookup"><span data-stu-id="8e56e-123">The attribute usually contains metadata about its target.</span></span> <span data-ttu-id="8e56e-124">В этом контексте метаданные могут быть любые данные о типе, отличные от его полей и членов.</span><span class="sxs-lookup"><span data-stu-id="8e56e-124">In this context, metadata could be any data about the type other than its fields and members.</span></span>

<span data-ttu-id="8e56e-125">Атрибуты в F # можно применять для следующих конструкций программирования: функции, методы, сборки, модули, типы (классы, записи, структуры, интерфейсы, делегаты, перечисления, объединения и т. д.), конструкторы, свойства, поля, параметры, Введите параметры и возвращаемые значения.</span><span class="sxs-lookup"><span data-stu-id="8e56e-125">Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values.</span></span> <span data-ttu-id="8e56e-126">Атрибуты не допускаются в `let` привязки внутри классов, выражений и выражений рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="8e56e-126">Attributes are not allowed on `let` bindings inside classes, expressions, or workflow expressions.</span></span>

<span data-ttu-id="8e56e-127">Как правило объявление атрибута появляется непосредственно перед объявлением конечного объекта атрибута.</span><span class="sxs-lookup"><span data-stu-id="8e56e-127">Typically, the attribute declaration appears directly before the declaration of the attribute target.</span></span> <span data-ttu-id="8e56e-128">Несколько объявлений атрибутов можно использовать вместе, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="8e56e-128">Multiple attribute declarations can be used together, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

<span data-ttu-id="8e56e-129">Атрибуты во время выполнения можно запрашивать с помощью отражения .NET.</span><span class="sxs-lookup"><span data-stu-id="8e56e-129">You can query attributes at run time by using .NET reflection.</span></span>

<span data-ttu-id="8e56e-130">Можно объявить несколько атрибутов по отдельности, как показано в предыдущем примере, или можно объявлять их в один набор квадратных скобок при использовании точки с запятой для разделения отдельных атрибутов и конструкторов, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="8e56e-130">You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as shown here.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

<span data-ttu-id="8e56e-131">Обычно встречаются следующие атрибуты: `Obsolete` атрибутов, атрибуты для обеспечения безопасности, атрибуты для поддержки COM, атрибуты, относящиеся к владение кодом и атрибуты, указывающее, может ли быть сериализован тип.</span><span class="sxs-lookup"><span data-stu-id="8e56e-131">Typically encountered attributes include the `Obsolete` attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized.</span></span> <span data-ttu-id="8e56e-132">В следующем примере показано использование `Obsolete` атрибута.</span><span class="sxs-lookup"><span data-stu-id="8e56e-132">The following example demonstrates the use of the `Obsolete` attribute.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

<span data-ttu-id="8e56e-133">Для целей атрибут `assembly` и `module`, можно применить атрибуты верхнего уровня `do` привязки сборки.</span><span class="sxs-lookup"><span data-stu-id="8e56e-133">For the attribute targets `assembly` and `module`, you apply the attributes to a top-level `do` binding in your assembly.</span></span> <span data-ttu-id="8e56e-134">Можно включить слово `assembly` или `module` в объявление атрибута, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="8e56e-134">You can include the word `assembly` or `module` in the attribute declaration, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

<span data-ttu-id="8e56e-135">Если опустить конечного объекта атрибута для атрибута, применяемых к `do` привязки, компилятор F # пытается определить целевой объект атрибута, который лучше всего подходит для этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="8e56e-135">If you omit the attribute target for an attribute applied to a `do` binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute.</span></span> <span data-ttu-id="8e56e-136">Многие классы атрибутов имеют атрибут типа `System.AttributeUsageAttribute` , включает в себя сведения о возможных целевых объектах, поддерживаемых для этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="8e56e-136">Many attribute classes have an attribute of type `System.AttributeUsageAttribute` that includes information about the possible targets supported for that attribute.</span></span> <span data-ttu-id="8e56e-137">Если `System.AttributeUsageAttribute` указывает, что атрибут поддерживает функции в качестве целевых объектов, этот атрибут выбирается для применения к главную точку входа программы.</span><span class="sxs-lookup"><span data-stu-id="8e56e-137">If the `System.AttributeUsageAttribute` indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program.</span></span> <span data-ttu-id="8e56e-138">Если `System.AttributeUsageAttribute` указывает, что атрибут поддерживает сборки в качестве целевых объектов, компилятор выбирает этот атрибут, чтобы применить к сборке.</span><span class="sxs-lookup"><span data-stu-id="8e56e-138">If the `System.AttributeUsageAttribute` indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly.</span></span> <span data-ttu-id="8e56e-139">Большинство атрибутов не применяются к функции и сборок, но в случаях, когда это делается, этот атрибут выбирается для применения к главной функции программы.</span><span class="sxs-lookup"><span data-stu-id="8e56e-139">Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function.</span></span> <span data-ttu-id="8e56e-140">Если целевой атрибут указан явно, атрибут применяется для указанного целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="8e56e-140">If the attribute target is specified explicitly, the attribute is applied to the specified target.</span></span>

<span data-ttu-id="8e56e-141">Несмотря на то, что вы обычно не требуется указать целевой объект атрибута явным образом, допустимые значения для *целевой* в атрибуте показаны в следующей таблице, а также примеры использования.</span><span class="sxs-lookup"><span data-stu-id="8e56e-141">Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute are shown in the following table, along with examples of usage.</span></span>

<table>
  <tr>
    <th><span data-ttu-id="8e56e-142">Целевой атрибут</span><span class="sxs-lookup"><span data-stu-id="8e56e-142">Attribute target</span></span></td>
    <th><span data-ttu-id="8e56e-143">Пример</span><span class="sxs-lookup"><span data-stu-id="8e56e-143">Example</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="8e56e-144">сборка</span><span class="sxs-lookup"><span data-stu-id="8e56e-144">assembly</span></span></td>
    <td><span data-ttu-id="8e56e-145">`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</span><span class="sxs-lookup"><span data-stu-id="8e56e-145">`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="8e56e-146">return</span><span class="sxs-lookup"><span data-stu-id="8e56e-146">return</span></span></td>
    <td><span data-ttu-id="8e56e-147">"функция1 let x: [<return: Obsolete>] int = x + 1"</span><span class="sxs-lookup"><span data-stu-id="8e56e-147">`let function1 x : [<return: Obsolete>] int = x + 1`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="8e56e-148">поле</span><span class="sxs-lookup"><span data-stu-id="8e56e-148">field</span></span></td>
    <td><span data-ttu-id="8e56e-149">"[<field: DefaultValue>] val изменяемый x: int"</span><span class="sxs-lookup"><span data-stu-id="8e56e-149">`[<field: DefaultValue>] val mutable x: int`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="8e56e-150">свойство;</span><span class="sxs-lookup"><span data-stu-id="8e56e-150">property</span></span></td>
    <td><span data-ttu-id="8e56e-151">"[<property: Obsolete>] это. MyProperty = x "</span><span class="sxs-lookup"><span data-stu-id="8e56e-151">`[<property: Obsolete>] this.MyProperty = x`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="8e56e-152">param</span><span class="sxs-lookup"><span data-stu-id="8e56e-152">param</span></span></td>
    <td><span data-ttu-id="8e56e-153">"член это. MyMethod ([<param: Out>] x: ref<int>) = x: = 10".</span><span class="sxs-lookup"><span data-stu-id="8e56e-153">`member this.MyMethod([<param: Out>] x : ref<int>) = x := 10`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="8e56e-154">type</span><span class="sxs-lookup"><span data-stu-id="8e56e-154">type</span></span></td>
    <td><span data-ttu-id="8e56e-155">
        ```
        [<type: StructLayout(Sequential)>] введите MyStruct = структура x: y байтов: int end ```
    </span><span class="sxs-lookup"><span data-stu-id="8e56e-155">
        ```
        [<type: StructLayout(Sequential)>] type MyStruct = struct x : byte y : int end ```
    </span></span></td> 
  </tr>
</table>

## <a name="see-also"></a><span data-ttu-id="8e56e-156">См. также</span><span class="sxs-lookup"><span data-stu-id="8e56e-156">See also</span></span>

- [<span data-ttu-id="8e56e-157">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="8e56e-157">F# Language Reference</span></span>](index.md)
