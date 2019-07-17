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
ms.openlocfilehash: 5d1882048b2af12c29a3771055cbeba9565b7dab
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67787400"
---
# <a name="user-defined-conversion-operators-c-reference"></a><span data-ttu-id="196b0-103">Операторы пользовательского преобразования (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="196b0-103">User-defined conversion operators (C# reference)</span></span>

<span data-ttu-id="196b0-104">Пользовательский тип может определять неявное или явное пользовательское преобразование в другой тип или из него.</span><span class="sxs-lookup"><span data-stu-id="196b0-104">A user-defined type can define a custom implicit or explicit conversion from or to another type.</span></span>

<span data-ttu-id="196b0-105">Неявные преобразования не требуют специального синтаксиса для вызова и могут происходить в различных ситуациях, например при вызовах методов и в назначениях.</span><span class="sxs-lookup"><span data-stu-id="196b0-105">Implicit conversions don't require special syntax to be invoked and can occur in a variety of situations, for example, in assignments and methods invocations.</span></span> <span data-ttu-id="196b0-106">Предопределенные неявные преобразования на C# всегда завершаются успешно и никогда не вызывают исключение или потерю данных.</span><span class="sxs-lookup"><span data-stu-id="196b0-106">Predefined C# implicit conversions always succeed and never throw an exception or lose information.</span></span> <span data-ttu-id="196b0-107">Неявные пользовательские преобразования должны вести себя таким же образом.</span><span class="sxs-lookup"><span data-stu-id="196b0-107">User-defined implicit conversions should behave in that way as well.</span></span> <span data-ttu-id="196b0-108">Если пользовательское преобразование может вызвать исключение или привести к потере данных, определите его как явное преобразование.</span><span class="sxs-lookup"><span data-stu-id="196b0-108">If a custom conversion can throw an exception or lose information, define it as an explicit conversion.</span></span>

<span data-ttu-id="196b0-109">Пользовательские преобразования не рассматриваются операторами [is](type-testing-and-conversion-operators.md#is-operator) и [as](type-testing-and-conversion-operators.md#as-operator).</span><span class="sxs-lookup"><span data-stu-id="196b0-109">User-defined conversions are not considered by the [is](type-testing-and-conversion-operators.md#is-operator) and [as](type-testing-and-conversion-operators.md#as-operator) operators.</span></span> <span data-ttu-id="196b0-110">Используйте [оператор приведения ()](type-testing-and-conversion-operators.md#cast-operator-) для вызова явного пользовательского преобразования.</span><span class="sxs-lookup"><span data-stu-id="196b0-110">Use the [cast operator ()](type-testing-and-conversion-operators.md#cast-operator-) to invoke a user-defined explicit conversion.</span></span>

<span data-ttu-id="196b0-111">Используйте ключевые слова `operator` и `implicit` или `explicit` для определения явного или неявного преобразования соответственно.</span><span class="sxs-lookup"><span data-stu-id="196b0-111">Use the `operator` and `implicit` or `explicit` keywords to define an implicit or explicit conversion, respectively.</span></span> <span data-ttu-id="196b0-112">Тип, который определяет преобразование, должен быть типом источника или целевого объекта этого преобразования.</span><span class="sxs-lookup"><span data-stu-id="196b0-112">The type that defines a conversion must be either a source type or a target type of that conversion.</span></span> <span data-ttu-id="196b0-113">Преобразование между двумя пользовательскими типами можно определить одним из двух типов.</span><span class="sxs-lookup"><span data-stu-id="196b0-113">A conversion between two user-defined types can be defined in either of the two types.</span></span>

<span data-ttu-id="196b0-114">Следующий пример иллюстрирует, как определить неявное и явное преобразования:</span><span class="sxs-lookup"><span data-stu-id="196b0-114">The following example demonstrates how to define an implicit and explicit conversion:</span></span>

[!code-csharp[implicit an explicit conversions](~/samples/csharp/language-reference/operators/UserDefinedConversions.cs)]

<span data-ttu-id="196b0-115">Можно также использовать ключевое слово `operator` для перегрузки предопределенного оператора C#.</span><span class="sxs-lookup"><span data-stu-id="196b0-115">You also use the `operator` keyword to overload a predefined C# operator.</span></span> <span data-ttu-id="196b0-116">Для получения дополнительной информации см. раздел [Перегрузка операторов](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="196b0-116">For more information, see [Operator overloading](operator-overloading.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="196b0-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="196b0-117">C# language specification</span></span>

<span data-ttu-id="196b0-118">Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="196b0-118">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="196b0-119">Операторы преобразования</span><span class="sxs-lookup"><span data-stu-id="196b0-119">Conversion operators</span></span>](~/_csharplang/spec/classes.md#conversion-operators)
- [<span data-ttu-id="196b0-120">Пользовательские преобразования</span><span class="sxs-lookup"><span data-stu-id="196b0-120">User-defined conversions</span></span>](~/_csharplang/spec/conversions.md#user-defined-conversions)
- [<span data-ttu-id="196b0-121">Неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="196b0-121">Implicit conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-conversions)
- [<span data-ttu-id="196b0-122">Явные преобразования</span><span class="sxs-lookup"><span data-stu-id="196b0-122">Explicit conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-conversions)

## <a name="see-also"></a><span data-ttu-id="196b0-123">См. также</span><span class="sxs-lookup"><span data-stu-id="196b0-123">See also</span></span>

- [<span data-ttu-id="196b0-124">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="196b0-124">C# reference</span></span>](../index.md)
- [<span data-ttu-id="196b0-125">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="196b0-125">C# operators</span></span>](index.md)
- [<span data-ttu-id="196b0-126">Перегрузка операторов</span><span class="sxs-lookup"><span data-stu-id="196b0-126">Operator overloading</span></span>](operator-overloading.md)
- [<span data-ttu-id="196b0-127">Операторы тестирования и преобразования типов</span><span class="sxs-lookup"><span data-stu-id="196b0-127">Type-testing and conversion operators</span></span>](type-testing-and-conversion-operators.md)
- [<span data-ttu-id="196b0-128">Приведение и преобразование типов</span><span class="sxs-lookup"><span data-stu-id="196b0-128">Casting and type conversion</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="196b0-129">Связанные пользовательские явные преобразования в C#</span><span class="sxs-lookup"><span data-stu-id="196b0-129">Chained user-defined explicit conversions in C#</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)
