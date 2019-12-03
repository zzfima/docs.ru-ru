---
title: Тип bool. Справочник по C#
ms.date: 11/26/2019
f1_keywords:
- bool
- bool_CSharpKeyword
helpviewer_keywords:
- bool data type [C#]
- Boolean [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 1e79de6d9e5cf973ce394bfb06871777c562c8ac
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552999"
---
# <a name="bool-c-reference"></a><span data-ttu-id="89319-102">bool (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="89319-102">bool (C# reference)</span></span>

<span data-ttu-id="89319-103">Ключевое слово типа `bool` — это псевдоним для типа структуры <xref:System.Boolean?displayProperty=nameWithType> .NET, представляющий логическое значение: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="89319-103">The `bool` type keyword is an alias for the .NET <xref:System.Boolean?displayProperty=nameWithType> structure type that represents a Boolean value, which can be either `true` or `false`.</span></span>

<span data-ttu-id="89319-104">Для выполнения логических операций со значениями типа `bool` используйте [логические](../operators/boolean-logical-operators.md) операторы.</span><span class="sxs-lookup"><span data-stu-id="89319-104">To perform logical operations with values of the `bool` type, use [Boolean logical](../operators/boolean-logical-operators.md) operators.</span></span> <span data-ttu-id="89319-105">Тип `bool` является типом результата операторов [сравнения](../operators/comparison-operators.md) и [равенства](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="89319-105">The `bool` type is the result type of [comparison](../operators/comparison-operators.md) and [equality](../operators/equality-operators.md) operators.</span></span> <span data-ttu-id="89319-106">Выражение `bool` может быть управляющим условным выражением в операторах [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md) и [for](../keywords/for.md) и [условном операторе `?:`](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="89319-106">A `bool` expression can be a controlling conditional expression in the [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md), and [for](../keywords/for.md) statements and in the [conditional operator `?:`](../operators/conditional-operator.md).</span></span>

<span data-ttu-id="89319-107">Значение по умолчанию для типа `bool` — `false`.</span><span class="sxs-lookup"><span data-stu-id="89319-107">The default value of the `bool` type is `false`.</span></span>

## <a name="literals"></a><span data-ttu-id="89319-108">Литералы</span><span class="sxs-lookup"><span data-stu-id="89319-108">Literals</span></span>

<span data-ttu-id="89319-109">Вы можете использовать литералы `true` и `false` для инициализации переменной `bool` или передачи значения `bool`:</span><span class="sxs-lookup"><span data-stu-id="89319-109">You can use the `true` and `false` literals to initialize a `bool` variable or to pass a `bool` value:</span></span>

[!code-csharp-interactive[bool literals](~/samples/csharp/language-reference/builtin-types/BoolType.cs#Literals)]

## <a name="conversions"></a><span data-ttu-id="89319-110">Преобразования</span><span class="sxs-lookup"><span data-stu-id="89319-110">Conversions</span></span>

<span data-ttu-id="89319-111">В C# доступно только два преобразования, использующих тип `bool`.</span><span class="sxs-lookup"><span data-stu-id="89319-111">C# provides only two conversions that involve the `bool` type.</span></span> <span data-ttu-id="89319-112">Это неявное преобразование в соответствующий тип `bool?`, допускающий значение NULL, и явное преобразование из типа `bool?`.</span><span class="sxs-lookup"><span data-stu-id="89319-112">Those are an implicit conversion to the corresponding nullable `bool?` type and an explicit conversion from the `bool?` type.</span></span> <span data-ttu-id="89319-113">Однако .NET предоставляет дополнительные методы, позволяющие выполнять преобразование в тип `bool` или из него.</span><span class="sxs-lookup"><span data-stu-id="89319-113">However, .NET provides additional methods that you can use to convert to or from the `bool` type.</span></span> <span data-ttu-id="89319-114">Дополнительные сведения см. в разделе о [преобразовании в логические значения и из них](/dotnet/api/system.boolean#converting-to-and-from-boolean-values) справочника по API <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="89319-114">For more information, see the [Converting to and from Boolean values](/dotnet/api/system.boolean#converting-to-and-from-boolean-values) section of the <xref:System.Boolean?displayProperty=nameWithType> API reference page.</span></span>

## <a name="three-valued-boolean-logic"></a><span data-ttu-id="89319-115">Трехзначная булева логика</span><span class="sxs-lookup"><span data-stu-id="89319-115">Three-valued Boolean logic</span></span>

<span data-ttu-id="89319-116">Используйте тип `bool?`, допускающий значение NULL, если нужно использовать трехзначную логику, например, при работе с базами данных, которые поддерживают трехзначный логический тип.</span><span class="sxs-lookup"><span data-stu-id="89319-116">Use the nullable `bool?` type, if you need to support the three-valued logic, for example, when you work with databases that support a three-valued Boolean type.</span></span> <span data-ttu-id="89319-117">Для операндов `bool?` предопределенные операторы `&` и `|` поддерживают троичную логику.</span><span class="sxs-lookup"><span data-stu-id="89319-117">For the `bool?` operands, the predefined `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="89319-118">См. подробнее о [логических операторах, поддерживающих значение NULL](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) в описании [логических операторов](../operators/boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="89319-118">For more information, see the [Nullable Boolean logical operators](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../operators/boolean-logical-operators.md) article.</span></span>

<span data-ttu-id="89319-119">См. дополнительные сведения о [типах значений, допускающих значение NULL](nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="89319-119">For more information about nullable value types, see [Nullable value types](nullable-value-types.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="89319-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="89319-120">C# language specification</span></span>

<span data-ttu-id="89319-121">Дополнительные сведения см. в разделе [Тип bool](~/_csharplang/spec/types.md#the-bool-type) [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="89319-121">For more information, see [The bool type](~/_csharplang/spec/types.md#the-bool-type) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="89319-122">См. также</span><span class="sxs-lookup"><span data-stu-id="89319-122">See also</span></span>

- [<span data-ttu-id="89319-123">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="89319-123">C# reference</span></span>](../index.md)
- [<span data-ttu-id="89319-124">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="89319-124">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="89319-125">Операторы true и false</span><span class="sxs-lookup"><span data-stu-id="89319-125">true and false operators</span></span>](../operators/true-false-operators.md)
