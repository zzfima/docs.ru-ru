---
title: Операторы пользовательского преобразования — справочник по C#
description: Узнайте, как определить пользовательские явные и неявные преобразования типа в C#.
ms.date: 07/09/2019
f1_keywords:
- explicit_CSharpKeyword
- implicit_CSharpKeyword
helpviewer_keywords:
- explicit keyword [C#]
- implicit keyword [C#]
- conversion operator [C#]
- user-defined conversion [C#]
ms.openlocfilehash: 25f042dec5fd5594b7e166cc064394e90db01c27
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036118"
---
# <a name="user-defined-conversion-operators-c-reference"></a><span data-ttu-id="b16b3-103">Операторы пользовательского преобразования (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b16b3-103">User-defined conversion operators (C# reference)</span></span>

<span data-ttu-id="b16b3-104">Пользовательский тип может определять неявное или явное пользовательское преобразование в другой тип или из него.</span><span class="sxs-lookup"><span data-stu-id="b16b3-104">A user-defined type can define a custom implicit or explicit conversion from or to another type.</span></span>

<span data-ttu-id="b16b3-105">Неявные преобразования не требуют специального синтаксиса для вызова и могут происходить в различных ситуациях, например при вызовах методов и в назначениях.</span><span class="sxs-lookup"><span data-stu-id="b16b3-105">Implicit conversions don't require special syntax to be invoked and can occur in a variety of situations, for example, in assignments and methods invocations.</span></span> <span data-ttu-id="b16b3-106">Предопределенные неявные преобразования на C# всегда завершаются успешно и никогда не вызывают исключение.</span><span class="sxs-lookup"><span data-stu-id="b16b3-106">Predefined C# implicit conversions always succeed and never throw an exception.</span></span> <span data-ttu-id="b16b3-107">Неявные пользовательские преобразования должны вести себя таким же образом.</span><span class="sxs-lookup"><span data-stu-id="b16b3-107">User-defined implicit conversions should behave in that way as well.</span></span> <span data-ttu-id="b16b3-108">Если пользовательское преобразование может вызвать исключение или привести к потере данных, определите его как явное преобразование.</span><span class="sxs-lookup"><span data-stu-id="b16b3-108">If a custom conversion can throw an exception or lose information, define it as an explicit conversion.</span></span>

<span data-ttu-id="b16b3-109">Пользовательские преобразования не рассматриваются операторами [is](type-testing-and-cast.md#is-operator) и [as](type-testing-and-cast.md#as-operator).</span><span class="sxs-lookup"><span data-stu-id="b16b3-109">User-defined conversions are not considered by the [is](type-testing-and-cast.md#is-operator) and [as](type-testing-and-cast.md#as-operator) operators.</span></span> <span data-ttu-id="b16b3-110">Используйте [оператор приведения ()](type-testing-and-cast.md#cast-operator-) для вызова явного пользовательского преобразования.</span><span class="sxs-lookup"><span data-stu-id="b16b3-110">Use the [cast operator ()](type-testing-and-cast.md#cast-operator-) to invoke a user-defined explicit conversion.</span></span>

<span data-ttu-id="b16b3-111">Используйте ключевые слова `operator` и `implicit` или `explicit` для определения явного или неявного преобразования соответственно.</span><span class="sxs-lookup"><span data-stu-id="b16b3-111">Use the `operator` and `implicit` or `explicit` keywords to define an implicit or explicit conversion, respectively.</span></span> <span data-ttu-id="b16b3-112">Тип, который определяет преобразование, должен быть типом источника или целевого объекта этого преобразования.</span><span class="sxs-lookup"><span data-stu-id="b16b3-112">The type that defines a conversion must be either a source type or a target type of that conversion.</span></span> <span data-ttu-id="b16b3-113">Преобразование между двумя пользовательскими типами можно определить одним из двух типов.</span><span class="sxs-lookup"><span data-stu-id="b16b3-113">A conversion between two user-defined types can be defined in either of the two types.</span></span>

<span data-ttu-id="b16b3-114">Следующий пример иллюстрирует, как определить неявное и явное преобразования:</span><span class="sxs-lookup"><span data-stu-id="b16b3-114">The following example demonstrates how to define an implicit and explicit conversion:</span></span>

[!code-csharp[implicit an explicit conversions](~/samples/csharp/language-reference/operators/UserDefinedConversions.cs)]

<span data-ttu-id="b16b3-115">Можно также использовать ключевое слово `operator` для перегрузки предопределенного оператора C#.</span><span class="sxs-lookup"><span data-stu-id="b16b3-115">You also use the `operator` keyword to overload a predefined C# operator.</span></span> <span data-ttu-id="b16b3-116">Для получения дополнительной информации см. раздел [Перегрузка операторов](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="b16b3-116">For more information, see [Operator overloading](operator-overloading.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b16b3-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="b16b3-117">C# language specification</span></span>

<span data-ttu-id="b16b3-118">Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="b16b3-118">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="b16b3-119">Операторы преобразования</span><span class="sxs-lookup"><span data-stu-id="b16b3-119">Conversion operators</span></span>](~/_csharplang/spec/classes.md#conversion-operators)
- [<span data-ttu-id="b16b3-120">Пользовательские преобразования</span><span class="sxs-lookup"><span data-stu-id="b16b3-120">User-defined conversions</span></span>](~/_csharplang/spec/conversions.md#user-defined-conversions)
- [<span data-ttu-id="b16b3-121">Неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="b16b3-121">Implicit conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-conversions)
- [<span data-ttu-id="b16b3-122">Явные преобразования</span><span class="sxs-lookup"><span data-stu-id="b16b3-122">Explicit conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-conversions)

## <a name="see-also"></a><span data-ttu-id="b16b3-123">См. также</span><span class="sxs-lookup"><span data-stu-id="b16b3-123">See also</span></span>

- [<span data-ttu-id="b16b3-124">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b16b3-124">C# reference</span></span>](../index.md)
- [<span data-ttu-id="b16b3-125">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="b16b3-125">C# operators</span></span>](index.md)
- [<span data-ttu-id="b16b3-126">Перегрузка операторов</span><span class="sxs-lookup"><span data-stu-id="b16b3-126">Operator overloading</span></span>](operator-overloading.md)
- [<span data-ttu-id="b16b3-127">Операторы приведения и тестирования типов</span><span class="sxs-lookup"><span data-stu-id="b16b3-127">Type-testing and cast operators</span></span>](type-testing-and-cast.md)
- [<span data-ttu-id="b16b3-128">Приведение и преобразование типов</span><span class="sxs-lookup"><span data-stu-id="b16b3-128">Casting and type conversion</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="b16b3-129">Связанные пользовательские явные преобразования в C#</span><span class="sxs-lookup"><span data-stu-id="b16b3-129">Chained user-defined explicit conversions in C#</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)
