---
title: Перечисления
description: Узнайте, как использовать F# перечисления вместо литералов, чтобы сделать код более читаемым и удобным в обслуживании.
ms.date: 05/16/2016
ms.openlocfilehash: 784cd9612b199e4648bb64432d3b4422ad35f649
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630338"
---
# <a name="enumerations"></a><span data-ttu-id="f3392-103">Перечисления</span><span class="sxs-lookup"><span data-stu-id="f3392-103">Enumerations</span></span>

<span data-ttu-id="f3392-104">*Перечисления*, также известные как *перечисления*, являются целочисленными типами, где метки присваиваются подмножеству значений.</span><span class="sxs-lookup"><span data-stu-id="f3392-104">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="f3392-105">Их можно использовать вместо литералов, чтобы сделать код более понятным и простым в обслуживании.</span><span class="sxs-lookup"><span data-stu-id="f3392-105">You can use them in place of literals to make code more readable and maintainable.</span></span>

## <a name="syntax"></a><span data-ttu-id="f3392-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3392-106">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="f3392-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f3392-107">Remarks</span></span>

<span data-ttu-id="f3392-108">Перечисление во многом похоже на размеченное объединение с простыми значениями, за исключением того, что можно указать значения.</span><span class="sxs-lookup"><span data-stu-id="f3392-108">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="f3392-109">Значениями обычно являются целые числа, начинающиеся с 0 или 1, или целые числа, представляющие битовые позиции.</span><span class="sxs-lookup"><span data-stu-id="f3392-109">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="f3392-110">Если перечисление предназначено для представления битовых позиций, следует также использовать атрибут [Flags](xref:System.FlagsAttribute).</span><span class="sxs-lookup"><span data-stu-id="f3392-110">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="f3392-111">Базовый тип перечисления определяется из используемого литерала, поэтому, например, можно использовать литералы с суффиксом, например `1u`, `2u`и т. д., для типа целого числа без знака (`uint32`).</span><span class="sxs-lookup"><span data-stu-id="f3392-111">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="f3392-112">При ссылке на именованные значения необходимо использовать имя самого типа перечисления в качестве квалификатора, то есть `enum-name.value1`, а не только. `value1`</span><span class="sxs-lookup"><span data-stu-id="f3392-112">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="f3392-113">Это поведение отличается от различенных объединений.</span><span class="sxs-lookup"><span data-stu-id="f3392-113">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="f3392-114">Это происходит потому, что перечисления всегда имеют атрибут [рекуирекуалифиедакцесс](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) .</span><span class="sxs-lookup"><span data-stu-id="f3392-114">This is because enumerations always have the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute.</span></span>

<span data-ttu-id="f3392-115">В следующем коде показано объявление и использование перечисления.</span><span class="sxs-lookup"><span data-stu-id="f3392-115">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="f3392-116">Можно легко преобразовать перечисления в базовый тип с помощью соответствующего оператора, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="f3392-116">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="f3392-117">`sbyte`Перечисляемые типы могут иметь один из следующих базовых типов:, `uint64` `int64` `int16` `uint32` `uint16` `byte`,, `int32`,,,, `uint16`, и `char`.</span><span class="sxs-lookup"><span data-stu-id="f3392-117">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="f3392-118">Типы перечисления представлены в .NET Framework как типы, унаследованные от `System.Enum`, которые, в свою очередь, наследуются от. `System.ValueType`</span><span class="sxs-lookup"><span data-stu-id="f3392-118">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="f3392-119">Таким образом, они являются типами значений, расположенными в стеке или встроенными в содержащий их объект, а любое значение базового типа является допустимым значением перечисления.</span><span class="sxs-lookup"><span data-stu-id="f3392-119">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="f3392-120">Это важно при сопоставлении шаблонов со значениями перечисления, поскольку необходимо предоставить шаблон, который перехватывает неименованные значения.</span><span class="sxs-lookup"><span data-stu-id="f3392-120">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="f3392-121">Функцию в F# библиотеке можно использовать для создания значения перечисления, даже для значения, отличного от одного из стандартных именованных значений. `enum`</span><span class="sxs-lookup"><span data-stu-id="f3392-121">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="f3392-122">Используйте `enum` функцию следующим образом.</span><span class="sxs-lookup"><span data-stu-id="f3392-122">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="f3392-123">Функция по `enum` умолчанию работает с `int32`типом.</span><span class="sxs-lookup"><span data-stu-id="f3392-123">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="f3392-124">Поэтому его нельзя использовать с типами перечисления, имеющими другие базовые типы.</span><span class="sxs-lookup"><span data-stu-id="f3392-124">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="f3392-125">Вместо этого используйте следующий.</span><span class="sxs-lookup"><span data-stu-id="f3392-125">Instead, use the following.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

<span data-ttu-id="f3392-126">Кроме того, варианты для перечислений всегда создаются как `public`.</span><span class="sxs-lookup"><span data-stu-id="f3392-126">Additionally, cases for enums are always emitted as `public`.</span></span> <span data-ttu-id="f3392-127">Это так, что они согласовываются C# с и остальной частью платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="f3392-127">This is so that they align with C# and the rest of the .NET platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3392-128">См. также</span><span class="sxs-lookup"><span data-stu-id="f3392-128">See also</span></span>

- [<span data-ttu-id="f3392-129">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="f3392-129">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="f3392-130">Приведение и преобразование</span><span class="sxs-lookup"><span data-stu-id="f3392-130">Casting and Conversions</span></span>](casting-and-conversions.md)
