---
title: Перечисления (F#)
description: 'Узнайте, как использовать F # перечисления вместо литералов, чтобы сделать код более читаемым и простым в обслуживании.'
ms.date: 05/16/2016
ms.openlocfilehash: 47fb353c2698f8b1474834ebbd1b0eff2c7f76e7
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44268579"
---
# <a name="enumerations"></a><span data-ttu-id="aa684-103">Перечисления</span><span class="sxs-lookup"><span data-stu-id="aa684-103">Enumerations</span></span>

<span data-ttu-id="aa684-104">*Перечисления*, также известных как *перечисления*,, являются целочисленными типами, где метки назначаются подмножество значений.</span><span class="sxs-lookup"><span data-stu-id="aa684-104">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="aa684-105">Их можно использовать вместо литералов, чтобы сделать код более понятным и простым в обслуживании.</span><span class="sxs-lookup"><span data-stu-id="aa684-105">You can use them in place of literals to make code more readable and maintainable.</span></span>

## <a name="syntax"></a><span data-ttu-id="aa684-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa684-106">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="aa684-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="aa684-107">Remarks</span></span>

<span data-ttu-id="aa684-108">Перечисление выглядит очень похожим это размеченное объединение, имеющее простые значения, за исключением того, что значения могут быть указаны.</span><span class="sxs-lookup"><span data-stu-id="aa684-108">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="aa684-109">Значения обычно являются целыми числами, которые начинаются с 0 или 1 или целых чисел, представляющих позиции битов.</span><span class="sxs-lookup"><span data-stu-id="aa684-109">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="aa684-110">Если перечисление предназначен для представления позиции битов, также следует использовать [флаги](xref:System.FlagsAttribute) атрибута.</span><span class="sxs-lookup"><span data-stu-id="aa684-110">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="aa684-111">Базовый тип перечисления определяется из литерал, который используется, чтобы, например, можно использовать литералы с суффиксами, такие как `1u`, `2u`, и т. д., для целого числа без знака (`uint32`) типа.</span><span class="sxs-lookup"><span data-stu-id="aa684-111">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="aa684-112">При ссылке на именованные значения, необходимо использовать имя самого типа перечисления как квалификатор, то есть `enum-name.value1`, а не только `value1`.</span><span class="sxs-lookup"><span data-stu-id="aa684-112">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="aa684-113">Это поведение отличается от размеченных объединений.</span><span class="sxs-lookup"><span data-stu-id="aa684-113">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="aa684-114">Это обусловлено перечисления всегда [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) атрибута.</span><span class="sxs-lookup"><span data-stu-id="aa684-114">This is because enumerations always have the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute.</span></span>

<span data-ttu-id="aa684-115">В следующем коде показано объявление и использование перечисления.</span><span class="sxs-lookup"><span data-stu-id="aa684-115">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="aa684-116">Можно легко преобразовать перечисления с базовым типом с помощью соответствующего оператора, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="aa684-116">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="aa684-117">Тип перечисления может иметь одно из следующих базовых типов: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, и `char`.</span><span class="sxs-lookup"><span data-stu-id="aa684-117">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="aa684-118">Типы перечисления представлены в .NET Framework как типы, унаследованные от `System.Enum`, которое, в свою очередь, наследуется от `System.ValueType`.</span><span class="sxs-lookup"><span data-stu-id="aa684-118">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="aa684-119">Таким образом они являются типами значений, которые находятся в стеке или в содержащем объекте, и любое значение базового типа является допустимым значением перечисления.</span><span class="sxs-lookup"><span data-stu-id="aa684-119">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="aa684-120">Это важно при сопоставления шаблонов в перечисление значений, так как вы должны предоставить шаблон, который перехватывает неименованных значений.</span><span class="sxs-lookup"><span data-stu-id="aa684-120">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="aa684-121">`enum` Функция в библиотеке F # можно использовать для создания значения перечисления, даже значение, отличное от одного из стандартных именованных значений.</span><span class="sxs-lookup"><span data-stu-id="aa684-121">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="aa684-122">Использовании `enum` работать следующим образом.</span><span class="sxs-lookup"><span data-stu-id="aa684-122">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="aa684-123">Значение по умолчанию `enum` функция работает с типом `int32`.</span><span class="sxs-lookup"><span data-stu-id="aa684-123">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="aa684-124">Таким образом он не может использоваться с типами перечисления, имеющими другие базовые типы.</span><span class="sxs-lookup"><span data-stu-id="aa684-124">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="aa684-125">Вместо этого используйте следующий код.</span><span class="sxs-lookup"><span data-stu-id="aa684-125">Instead, use the following.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

<span data-ttu-id="aa684-126">Кроме того, случаи для перечисления всегда передаются в рамках `public`.</span><span class="sxs-lookup"><span data-stu-id="aa684-126">Additionally, cases for enums are always emitted as `public`.</span></span> <span data-ttu-id="aa684-127">Это, чтобы они соотносятся с C# и остальной частью платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="aa684-127">This is so that they align with C# and the rest of the .NET platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa684-128">См. также</span><span class="sxs-lookup"><span data-stu-id="aa684-128">See also</span></span>

- [<span data-ttu-id="aa684-129">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="aa684-129">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="aa684-130">Приведение и преобразование</span><span class="sxs-lookup"><span data-stu-id="aa684-130">Casting and Conversions</span></span>](casting-and-conversions.md)
