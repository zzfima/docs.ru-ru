---
title: "Перечисления (F#)"
description: "Сведения об использовании языка F # перечисления вместо литералов, чтобы сделать код более читаемым и простым в обслуживании."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9272bf5a-9a9f-4314-9e34-a3248e5244f5
ms.openlocfilehash: de0273900b707c99e6fb1bcc84e5c2b9ef2bc725
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="enumerations"></a><span data-ttu-id="8261d-104">Перечисления</span><span class="sxs-lookup"><span data-stu-id="8261d-104">Enumerations</span></span>

<span data-ttu-id="8261d-105">*Перечисления*, также известных как *перечисления*, относятся к целочисленным типам где метки назначаются набор значений.</span><span class="sxs-lookup"><span data-stu-id="8261d-105">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="8261d-106">Их можно использовать вместо литералов, чтобы сделать код более понятным и простым в обслуживании.</span><span class="sxs-lookup"><span data-stu-id="8261d-106">You can use them in place of literals to make code more readable and maintainable.</span></span>


## <a name="syntax"></a><span data-ttu-id="8261d-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8261d-107">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="8261d-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="8261d-108">Remarks</span></span>
<span data-ttu-id="8261d-109">Перечисление похож размеченного объединения с простыми значениями, но значения могут быть заданы.</span><span class="sxs-lookup"><span data-stu-id="8261d-109">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="8261d-110">Обычно значения являются целыми числами, которые начинаются с 0 или 1, или целые числа, представляющие позиции битов.</span><span class="sxs-lookup"><span data-stu-id="8261d-110">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="8261d-111">Если перечисление предназначен для представления позиции битов, следует использовать [флаги](xref:System.FlagsAttribute) атрибута.</span><span class="sxs-lookup"><span data-stu-id="8261d-111">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="8261d-112">Базовый тип перечисления определяется из литерал, который используется, чтобы, например, можно использовать литералы с суффиксами, такие как `1u`, `2u`и так далее для целое число без знака (`uint32`) тип.</span><span class="sxs-lookup"><span data-stu-id="8261d-112">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="8261d-113">При ссылке на именованные значения, необходимо использовать имя самого типа перечисления как квалификатор, то есть `enum-name.value1`, а не просто `value1`.</span><span class="sxs-lookup"><span data-stu-id="8261d-113">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="8261d-114">Это поведение отличается от размеченных объединений.</span><span class="sxs-lookup"><span data-stu-id="8261d-114">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="8261d-115">Это обусловлено перечисления всегда [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) атрибута.</span><span class="sxs-lookup"><span data-stu-id="8261d-115">This is because enumerations always have the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute.</span></span>

<span data-ttu-id="8261d-116">Ниже показано объявление и использование перечисления.</span><span class="sxs-lookup"><span data-stu-id="8261d-116">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="8261d-117">Можно легко преобразовать перечисления с базовым типом, с помощью соответствующего оператора, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="8261d-117">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="8261d-118">Тип перечисления может иметь одно из следующих базовых типов: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, и `char`.</span><span class="sxs-lookup"><span data-stu-id="8261d-118">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="8261d-119">Перечисление типов представлены в .NET Framework как типы, унаследованные от `System.Enum`, которое в свою очередь наследуется от `System.ValueType`.</span><span class="sxs-lookup"><span data-stu-id="8261d-119">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="8261d-120">Таким образом они являются типами значений, которые находятся в стеке или в вмещающего объекта, и любое значение базового типа является допустимым значением перечисления.</span><span class="sxs-lookup"><span data-stu-id="8261d-120">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="8261d-121">Это важно, когда значения перечисления сопоставления шаблонов, так как вы должны предоставить шаблон, перехватывающий неименованные значения.</span><span class="sxs-lookup"><span data-stu-id="8261d-121">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="8261d-122">`enum` Функции в библиотеке F # можно использовать для создания значения перечисления, даже отличные от заранее заданных именованных значений.</span><span class="sxs-lookup"><span data-stu-id="8261d-122">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="8261d-123">Вы используете `enum` работать следующим образом.</span><span class="sxs-lookup"><span data-stu-id="8261d-123">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="8261d-124">Значение по умолчанию `enum` функция работает с типом `int32`.</span><span class="sxs-lookup"><span data-stu-id="8261d-124">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="8261d-125">Таким образом он не может использоваться с типами перечисления, имеющими другие базовые типы.</span><span class="sxs-lookup"><span data-stu-id="8261d-125">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="8261d-126">Вместо этого используйте следующий код.</span><span class="sxs-lookup"><span data-stu-id="8261d-126">Instead, use the following.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]
    
## <a name="see-also"></a><span data-ttu-id="8261d-127">См. также</span><span class="sxs-lookup"><span data-stu-id="8261d-127">See Also</span></span>
[<span data-ttu-id="8261d-128">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="8261d-128">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="8261d-129">Приведение и преобразование</span><span class="sxs-lookup"><span data-stu-id="8261d-129">Casting and Conversions</span></span>](casting-and-conversions.md)
