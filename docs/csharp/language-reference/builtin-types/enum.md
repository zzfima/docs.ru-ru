---
title: Справочник по C#. Типы перечислений
description: Общие сведения о типах перечислений на C#, которые предоставляют выбор или комбинацию вариантов выбора.
ms.date: 12/13/2019
f1_keywords:
- enum
- enum_CSharpKeyword
helpviewer_keywords:
- enum keyword [C#]
- enum type [C#]
- enumeration type [C#]
- bit flags [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
ms.openlocfilehash: ab5eb1679f846bf0e25d90a4d0e0a71f0bdb0096
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847717"
---
# <a name="enumeration-types-c-reference"></a><span data-ttu-id="0c6c8-103">Типы перечислений (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0c6c8-103">Enumeration types (C# reference)</span></span>

<span data-ttu-id="0c6c8-104">*Тип перечисления* (или *тип enum*) — это [тип значения](value-types.md), определенный набором именованных констант применяемого [целочисленного типа](integral-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="0c6c8-104">An *enumeration type* (or *enum type*) is a [value type](value-types.md) defined by a set of named constants of the underlying [integral numeric](integral-numeric-types.md) type.</span></span> <span data-ttu-id="0c6c8-105">Чтобы определить тип перечисления, используйте ключевое слово `enum` и укажите имена *элементов перечисления*:</span><span class="sxs-lookup"><span data-stu-id="0c6c8-105">To define an enumeration type, use the `enum` keyword and specify the names of *enum members*:</span></span>

```csharp
enum Season
{
    Spring,
    Summer,
    Autumn,
    Winter
}
```

<span data-ttu-id="0c6c8-106">По умолчанию связанные значения констант элементов перечисления имеют тип `int`. Они начинаются с нуля и увеличиваются на единицу в соответствии с порядком текста определения.</span><span class="sxs-lookup"><span data-stu-id="0c6c8-106">By default, the associated constant values of enum members are of type `int`; they start with zero and increase by one following the definition text order.</span></span> <span data-ttu-id="0c6c8-107">Вы можете явно указать любой другой [целочисленный](integral-numeric-types.md) тип в качестве базового типа перечисления.</span><span class="sxs-lookup"><span data-stu-id="0c6c8-107">You can explicitly specify any other [integral numeric](integral-numeric-types.md) type as an underlying type of an enumeration type.</span></span> <span data-ttu-id="0c6c8-108">Вы также можете явно указать соответствующие значения констант, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0c6c8-108">You also can explicitly specify the associated constant values, as the following example shows:</span></span>

```csharp
enum ErrorCode : ushort
{
    None = 0,
    Unknown = 1,
    ConnectionLost = 100,
    OutlierReading = 200
}
```

<span data-ttu-id="0c6c8-109">Вы не можете определить метод внутри определения типа перечисления.</span><span class="sxs-lookup"><span data-stu-id="0c6c8-109">You cannot define a method inside the definition of an enumeration type.</span></span> <span data-ttu-id="0c6c8-110">Чтобы добавить функциональные возможности к типу перечисления, создайте [метод расширения](../../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="0c6c8-110">To add functionality to an enumeration type, create an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

<span data-ttu-id="0c6c8-111">Значением по умолчанию для типа перечисления `E` является значение, созданное выражением `(E)0`, даже если ноль не имеет соответствующего элемента перечисления.</span><span class="sxs-lookup"><span data-stu-id="0c6c8-111">The default value of an enumeration type `E` is the value produced by expression `(E)0`, even if zero doesn't have the corresponding enum member.</span></span>

<span data-ttu-id="0c6c8-112">Тип перечисления используется для представления выбора из набора взаимоисключающих значений или комбинации вариантов выбора.</span><span class="sxs-lookup"><span data-stu-id="0c6c8-112">You use an enumeration type to represent a choice from a set of mutually exclusive values or a combination of choices.</span></span> <span data-ttu-id="0c6c8-113">Чтобы представить комбинацию вариантов выбора, определите тип перечисления как битовые флаги.</span><span class="sxs-lookup"><span data-stu-id="0c6c8-113">To represent a combination of choices, define an enumeration type as bit flags.</span></span>

## <a name="enumeration-types-as-bit-flags"></a><span data-ttu-id="0c6c8-114">Типы перечислений как битовые флаги</span><span class="sxs-lookup"><span data-stu-id="0c6c8-114">Enumeration types as bit flags</span></span>

<span data-ttu-id="0c6c8-115">Если вам необходимо, чтобы тип перечисления представлял комбинацию вариантов выбора, определите элементы перечисления для этих вариантов так, чтобы отдельный выбор был битовым полем.</span><span class="sxs-lookup"><span data-stu-id="0c6c8-115">If you want an enumeration type to represent a combination of choices, define enum members for those choices such that an individual choice is a bit field.</span></span> <span data-ttu-id="0c6c8-116">То есть связанные значения этих элементов перечисления должны быть степенями двух.</span><span class="sxs-lookup"><span data-stu-id="0c6c8-116">That is, the associated values of those enum members should be the powers of two.</span></span> <span data-ttu-id="0c6c8-117">Затем вы можете использовать [побитовые логические операторы `|` или `&`](../operators/bitwise-and-shift-operators.md#enumeration-logical-operators), чтобы комбинировать варианты выбора или пересекать комбинации вариантов выбора соответственно.</span><span class="sxs-lookup"><span data-stu-id="0c6c8-117">Then, you can use the [bitwise logical operators `|` or `&`](../operators/bitwise-and-shift-operators.md#enumeration-logical-operators) to combine choices or intersect combinations of choices, respectively.</span></span> <span data-ttu-id="0c6c8-118">Чтобы указать, что тип перечисления объявляет битовые поля, примените к нему атрибут [Flags](xref:System.FlagsAttribute).</span><span class="sxs-lookup"><span data-stu-id="0c6c8-118">To indicate that an enumeration type declares bit fields, apply the [Flags](xref:System.FlagsAttribute) attribute to it.</span></span> <span data-ttu-id="0c6c8-119">Как показано в следующем примере, вы также можете включить некоторые типичные комбинации в определение типа перечисления.</span><span class="sxs-lookup"><span data-stu-id="0c6c8-119">As the following example shows, you also can include some typical combinations in the definition of an enumeration type.</span></span>

[!code-csharp[enum flags](snippets/EnumType.cs#Flags)]

<span data-ttu-id="0c6c8-120">Дополнительные сведения и примеры см. на странице справочника по API <xref:System.FlagsAttribute?displayProperty=nameWithType> и в разделе о [неисключительных элементах и атрибутах Flags](/dotnet/api/system.enum#non-exclusive-members-and-the-flags-attribute) страницы справочника по API <xref:System.Enum?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0c6c8-120">For more information and examples, see the <xref:System.FlagsAttribute?displayProperty=nameWithType> API reference page and the [Non-exclusive members and the Flags attribute](/dotnet/api/system.enum#non-exclusive-members-and-the-flags-attribute) section of the <xref:System.Enum?displayProperty=nameWithType> API reference page.</span></span>

## <a name="the-systemenum-type-and-enum-constraint"></a><span data-ttu-id="0c6c8-121">Тип System.Enum и ограничение перечисления</span><span class="sxs-lookup"><span data-stu-id="0c6c8-121">The System.Enum type and enum constraint</span></span>

<span data-ttu-id="0c6c8-122">Тип <xref:System.Enum?displayProperty=nameWithType> является абстрактным базовым классом всех типов перечисления.</span><span class="sxs-lookup"><span data-stu-id="0c6c8-122">The <xref:System.Enum?displayProperty=nameWithType> type is the abstract base class of all enumeration types.</span></span> <span data-ttu-id="0c6c8-123">Он предоставляет различные методы, позволяющие получить информацию о типе перечисления и его значениях.</span><span class="sxs-lookup"><span data-stu-id="0c6c8-123">It provides a number of methods to get information about an enumeration type and its values.</span></span> <span data-ttu-id="0c6c8-124">Дополнительные сведения и примеры см. на странице справочника по API <xref:System.Enum?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0c6c8-124">For more information and examples, see the <xref:System.Enum?displayProperty=nameWithType> API reference page.</span></span>

<span data-ttu-id="0c6c8-125">Начиная с C# версии 7.3, вы можете использовать тип `System.Enum` в ограничении базового класса (которое известно как [ограничение перечисления](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)), чтобы указать, что параметр типа является типом перечисления.</span><span class="sxs-lookup"><span data-stu-id="0c6c8-125">Beginning with C# 7.3, you can use `System.Enum` in a base class constraint (that is known as the [enum constraint](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)) to specify that a type parameter is an enumeration type.</span></span>

## <a name="conversions"></a><span data-ttu-id="0c6c8-126">Преобразования</span><span class="sxs-lookup"><span data-stu-id="0c6c8-126">Conversions</span></span>

<span data-ttu-id="0c6c8-127">Для любого типа перечисления существуют явные преобразования между типом перечисления и его базовым целочисленным типом.</span><span class="sxs-lookup"><span data-stu-id="0c6c8-127">For any enumeration type, there exist explicit conversions between the enumeration type and its underlying integral type.</span></span> <span data-ttu-id="0c6c8-128">Если вы [привели](../operators/type-testing-and-cast.md#cast-operator-) значение перечисления к его базовому типу, то результатом будет связанное целочисленное значение элемента перечисления.</span><span class="sxs-lookup"><span data-stu-id="0c6c8-128">If you [cast](../operators/type-testing-and-cast.md#cast-operator-) an enum value to its underlying type, the result is the associated integral value of an enum member.</span></span>

[!code-csharp[enum conversions](snippets/EnumType.cs#Conversions)]

<span data-ttu-id="0c6c8-129">Используйте метод <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType>, чтобы определить, содержит ли тип перечисления элемент перечисления с определенным связанным значением.</span><span class="sxs-lookup"><span data-stu-id="0c6c8-129">Use the <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> method to determine whether an enumeration type contains an enum member with the certain associated value.</span></span>

<span data-ttu-id="0c6c8-130">Для любого типа перечисления существует [упаковка — преобразование и распаковка — преобразование](../../programming-guide/types/boxing-and-unboxing.md) в тип <xref:System.Enum?displayProperty=nameWithType> и из него соответственно.</span><span class="sxs-lookup"><span data-stu-id="0c6c8-130">For any enumeration type, there exist [boxing and unboxing](../../programming-guide/types/boxing-and-unboxing.md) conversions to and from the <xref:System.Enum?displayProperty=nameWithType> type, respectively.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0c6c8-131">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0c6c8-131">C# language specification</span></span>

<span data-ttu-id="0c6c8-132">Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="0c6c8-132">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="0c6c8-133">Перечисления</span><span class="sxs-lookup"><span data-stu-id="0c6c8-133">Enums</span></span>](~/_csharplang/spec/enums.md)
- [<span data-ttu-id="0c6c8-134">Значения перечислений и операции с ними</span><span class="sxs-lookup"><span data-stu-id="0c6c8-134">Enum values and operations</span></span>](~/_csharplang/spec/enums.md#enum-values-and-operations)
- <span data-ttu-id="0c6c8-135">[Enumeration logical operators](~/_csharplang/spec/expressions.md#enumeration-logical-operators) (Логические операторы перечисления)</span><span class="sxs-lookup"><span data-stu-id="0c6c8-135">[Enumeration logical operators](~/_csharplang/spec/expressions.md#enumeration-logical-operators)</span></span>
- <span data-ttu-id="0c6c8-136">[Enumeration comparison operators](~/_csharplang/spec/expressions.md#enumeration-comparison-operators) (Операторы сравнения перечислений)</span><span class="sxs-lookup"><span data-stu-id="0c6c8-136">[Enumeration comparison operators](~/_csharplang/spec/expressions.md#enumeration-comparison-operators)</span></span>
- <span data-ttu-id="0c6c8-137">[Explicit enumeration conversions](~/_csharplang/spec/conversions.md#explicit-enumeration-conversions) (Явные преобразования перечислений)</span><span class="sxs-lookup"><span data-stu-id="0c6c8-137">[Explicit enumeration conversions](~/_csharplang/spec/conversions.md#explicit-enumeration-conversions)</span></span>
- <span data-ttu-id="0c6c8-138">[Implicit enumeration conversions](~/_csharplang/spec/conversions.md#implicit-enumeration-conversions) (Неявные преобразования перечислений)</span><span class="sxs-lookup"><span data-stu-id="0c6c8-138">[Implicit enumeration conversions](~/_csharplang/spec/conversions.md#implicit-enumeration-conversions)</span></span>

## <a name="see-also"></a><span data-ttu-id="0c6c8-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0c6c8-139">See also</span></span>

- [<span data-ttu-id="0c6c8-140">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0c6c8-140">C# reference</span></span>](../index.md)
- [<span data-ttu-id="0c6c8-141">Строки форматов перечисления</span><span class="sxs-lookup"><span data-stu-id="0c6c8-141">Enumeration format strings</span></span>](../../../standard/base-types/enumeration-format-strings.md)
- [<span data-ttu-id="0c6c8-142">Рекомендации по разработке перечислений</span><span class="sxs-lookup"><span data-stu-id="0c6c8-142">Design guidelines - Enum design</span></span>](../../../standard/design-guidelines/enum.md)
- [<span data-ttu-id="0c6c8-143">Рекомендации по разработке. Соглашения об именовании перечислений</span><span class="sxs-lookup"><span data-stu-id="0c6c8-143">Design guidelines - Enum naming conventions</span></span>](../../../standard/design-guidelines/names-of-classes-structs-and-interfaces.md#naming-enumerations)
- [<span data-ttu-id="0c6c8-144">Оператор switch</span><span class="sxs-lookup"><span data-stu-id="0c6c8-144">switch statement</span></span>](../keywords/switch.md)
