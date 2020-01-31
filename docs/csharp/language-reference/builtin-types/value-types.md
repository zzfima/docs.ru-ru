---
title: Справочник по C#. Типы значений
ms.date: 01/22/2020
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 6b96d65f657f2af1af5c9a245e956640ee06260e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76748491"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="3ea90-102">Типы значений (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="3ea90-102">Value types (C# reference)</span></span>

<span data-ttu-id="3ea90-103">*Типы значений* и [ссылочные типы](../keywords/reference-types.md) — это две основные категории типов C#.</span><span class="sxs-lookup"><span data-stu-id="3ea90-103">*Value types* and [reference types](../keywords/reference-types.md) are the two main categories of C# types.</span></span> <span data-ttu-id="3ea90-104">Переменная типа значения содержит экземпляр типа.</span><span class="sxs-lookup"><span data-stu-id="3ea90-104">A variable of a value type contains an instance of the type.</span></span> <span data-ttu-id="3ea90-105">Это отличается от переменной ссылочного типа, которая содержит ссылку на экземпляр типа.</span><span class="sxs-lookup"><span data-stu-id="3ea90-105">This differs from a variable of a reference type, which contains a reference to an instance of the type.</span></span> <span data-ttu-id="3ea90-106">По умолчанию при [назначении](../operators/assignment-operator.md), передаче аргумента в метод или возврате результата метода копируются значения переменных.</span><span class="sxs-lookup"><span data-stu-id="3ea90-106">By default, on [assignment](../operators/assignment-operator.md), passing an argument to a method, or returning a method result, variable values are copied.</span></span> <span data-ttu-id="3ea90-107">В случае переменных типа значения копируются соответствующие экземпляры типа.</span><span class="sxs-lookup"><span data-stu-id="3ea90-107">In the case of value-type variables, the corresponding type instances are copied.</span></span> <span data-ttu-id="3ea90-108">В следующем примере продемонстрировано такое поведение.</span><span class="sxs-lookup"><span data-stu-id="3ea90-108">The following example demonstrates that behavior:</span></span>

[!code-csharp[copy of values](~/samples/csharp/language-reference/builtin-types/ValueTypes.cs#ValueTypeCopied)]

<span data-ttu-id="3ea90-109">Как показано в предыдущем примере, операции с переменной типа значения влияют только на этот экземпляр типа значения, хранящийся в переменной.</span><span class="sxs-lookup"><span data-stu-id="3ea90-109">As the preceding example shows, operations on a value-type variable affect only that instance of the value type, stored in the variable.</span></span>

<span data-ttu-id="3ea90-110">Если тип значения содержит элемент данных ссылочного типа, то при копировании экземпляра типа значения копируется только ссылка на экземпляр ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="3ea90-110">If a value type contains a data member of a reference type, only the reference to the instance of the reference type is copied when a value-type instance is copied.</span></span> <span data-ttu-id="3ea90-111">Как скопированный, так и исходный экземпляр типа значения имеют доступ к одному и тому же экземпляру ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="3ea90-111">Both the copy and original value-type instance have access to the same reference-type instance.</span></span> <span data-ttu-id="3ea90-112">В следующем примере продемонстрировано такое поведение.</span><span class="sxs-lookup"><span data-stu-id="3ea90-112">The following example demonstrates that behavior:</span></span>

[!code-csharp[shallow copy](~/samples/csharp/language-reference/builtin-types/ValueTypes.cs#ShallowCopy)]

> [!NOTE]
> <span data-ttu-id="3ea90-113">Чтобы сделать код менее подверженным ошибкам и более надежным, определите и используйте неизменяемые типы значений.</span><span class="sxs-lookup"><span data-stu-id="3ea90-113">To make your code less error-prone and more robust, define and use immutable value types.</span></span> <span data-ttu-id="3ea90-114">В этой статье изменяемые типы значений используются только в демонстрационных целях.</span><span class="sxs-lookup"><span data-stu-id="3ea90-114">This article uses mutable value types only for demonstration purposes.</span></span>

## <a name="kinds-of-value-types"></a><span data-ttu-id="3ea90-115">Виды типов значений</span><span class="sxs-lookup"><span data-stu-id="3ea90-115">Kinds of value types</span></span>

<span data-ttu-id="3ea90-116">Тип значения может относится к одному из двух следующих видов:</span><span class="sxs-lookup"><span data-stu-id="3ea90-116">A value type can be one of the two following kinds:</span></span>

- <span data-ttu-id="3ea90-117">[тип структуры](../keywords/struct.md), который инкапсулирует данные и связанные функции;</span><span class="sxs-lookup"><span data-stu-id="3ea90-117">a [structure type](../keywords/struct.md), which encapsulates data and related functionality</span></span>
- <span data-ttu-id="3ea90-118">[тип перечисления](enum.md), который определяется набором именованных констант и представляет выбор или сочетание вариантов для выбора.</span><span class="sxs-lookup"><span data-stu-id="3ea90-118">an [enumeration type](enum.md), which is defined by a set of named constants and represents a choice or a combination of choices</span></span>

<span data-ttu-id="3ea90-119">[Тип значений `T?`, допускающий значение NULL](nullable-value-types.md), представляет все значения своего базового типа значения `T`, а также дополнительное значение [NULL](../keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="3ea90-119">A [nullable value type](nullable-value-types.md) `T?` represents all values of its underlying value type `T` and an additional [null](../keywords/null.md) value.</span></span> <span data-ttu-id="3ea90-120">Вы не можете назначить `null` переменной типа значения, если только это не тип, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="3ea90-120">You cannot assign `null` to a variable of a value type, unless it's a nullable value type.</span></span>

## <a name="built-in-value-types"></a><span data-ttu-id="3ea90-121">Встроенные типы значений</span><span class="sxs-lookup"><span data-stu-id="3ea90-121">Built-in value types</span></span>

<span data-ttu-id="3ea90-122">C# предоставляет следующие встроенные типы значений, которые также называются *простыми типами*.</span><span class="sxs-lookup"><span data-stu-id="3ea90-122">C# provides the following built-in value types, also known as *simple types*:</span></span>

- [<span data-ttu-id="3ea90-123">Целочисленные типы</span><span class="sxs-lookup"><span data-stu-id="3ea90-123">Integral numeric types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="3ea90-124">Числовые типы с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="3ea90-124">Floating-point numeric types</span></span>](floating-point-numeric-types.md)
- <span data-ttu-id="3ea90-125">[bool](bool.md), представляющий логическое значение</span><span class="sxs-lookup"><span data-stu-id="3ea90-125">[bool](bool.md) that represents a Boolean value</span></span>
- <span data-ttu-id="3ea90-126">[char](char.md), представляющий символ Юникода UTF-16</span><span class="sxs-lookup"><span data-stu-id="3ea90-126">[char](char.md) that represents a Unicode UTF-16 character</span></span>

<span data-ttu-id="3ea90-127">Все простые типы являются типами структур и отличаются от других типов структур тем, что разрешают некоторые дополнительные операции.</span><span class="sxs-lookup"><span data-stu-id="3ea90-127">All simple types are structure types and differ from other structure types in that they permit certain additional operations:</span></span>

- <span data-ttu-id="3ea90-128">Литералы можно использовать для предоставления значения простого типа.</span><span class="sxs-lookup"><span data-stu-id="3ea90-128">You can use literals to provide a value of a simple type.</span></span> <span data-ttu-id="3ea90-129">Например, `'A'` — это литерал типа `char`, а `2001` — литерал типа `int`.</span><span class="sxs-lookup"><span data-stu-id="3ea90-129">For example, `'A'` is a literal of the type `char` and `2001` is a literal of the type `int`.</span></span>

- <span data-ttu-id="3ea90-130">Константы простых типов можно объявить с помощью ключевого слова [const](../keywords/const.md).</span><span class="sxs-lookup"><span data-stu-id="3ea90-130">You can declare constants of the simple types with the [const](../keywords/const.md) keyword.</span></span> <span data-ttu-id="3ea90-131">Невозможно использовать константы других типов структур.</span><span class="sxs-lookup"><span data-stu-id="3ea90-131">It's not possible to have constants of other structure types.</span></span>

- <span data-ttu-id="3ea90-132">Константные выражения, операнды которых являются константами простых типов, вычисляются во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="3ea90-132">Constant expressions, whose operands are all constants of the simple types, are evaluated at compile time.</span></span>

<span data-ttu-id="3ea90-133">Начиная с версии 7.0 в языке C# поддерживаются [кортежи значений](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="3ea90-133">Beginning with C# 7.0, C# supports [value tuples](../../tuples.md).</span></span> <span data-ttu-id="3ea90-134">Кортеж значений — это тип значения, не являющийся простым.</span><span class="sxs-lookup"><span data-stu-id="3ea90-134">A value tuple is a value type, but not a simple type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3ea90-135">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="3ea90-135">C# language specification</span></span>

<span data-ttu-id="3ea90-136">Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="3ea90-136">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="3ea90-137">Типы значений</span><span class="sxs-lookup"><span data-stu-id="3ea90-137">Value types</span></span>](~/_csharplang/spec/types.md#value-types)
- [<span data-ttu-id="3ea90-138">Простые типы</span><span class="sxs-lookup"><span data-stu-id="3ea90-138">Simple types</span></span>](~/_csharplang/spec/types.md#simple-types)
- [<span data-ttu-id="3ea90-139">Переменные</span><span class="sxs-lookup"><span data-stu-id="3ea90-139">Variables</span></span>](~/_csharplang/spec/variables.md)

## <a name="see-also"></a><span data-ttu-id="3ea90-140">См. также</span><span class="sxs-lookup"><span data-stu-id="3ea90-140">See also</span></span>

- [<span data-ttu-id="3ea90-141">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="3ea90-141">C# reference</span></span>](../index.md)
- <xref:System.ValueType?displayProperty=nameWithType>
- [<span data-ttu-id="3ea90-142">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="3ea90-142">Reference types</span></span>](../keywords/reference-types.md)
