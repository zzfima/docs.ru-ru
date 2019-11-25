---
title: Таблица значений по умолчанию — справочник по C#
ms.custom: seodec18
description: Узнайте значения по умолчанию для типов в C#.
ms.date: 07/29/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: 2f1ad5cc029b93261153e46d854cd8bf3e31ce92
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428534"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="a7d65-103">Таблица значений по умолчанию (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a7d65-103">Default values table (C# reference)</span></span>

<span data-ttu-id="a7d65-104">В следующей таблице показаны значения по умолчанию для типов C#:</span><span class="sxs-lookup"><span data-stu-id="a7d65-104">The following table shows the default values of C# types:</span></span>

|<span data-ttu-id="a7d65-105">Тип</span><span class="sxs-lookup"><span data-stu-id="a7d65-105">Type</span></span>|<span data-ttu-id="a7d65-106">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a7d65-106">Default value</span></span>|
|---------|------------------|
|<span data-ttu-id="a7d65-107">любой ссылочный тип;</span><span class="sxs-lookup"><span data-stu-id="a7d65-107">Any reference type</span></span>|`null`|
|<span data-ttu-id="a7d65-108">Любой [встроенный целочисленный тип](../builtin-types/integral-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="a7d65-108">Any [built-in integral numeric type](../builtin-types/integral-numeric-types.md)</span></span>|<span data-ttu-id="a7d65-109">Ноль (0)</span><span class="sxs-lookup"><span data-stu-id="a7d65-109">0 (zero)</span></span>|
|<span data-ttu-id="a7d65-110">Любой [встроенный тип с плавающей запятой](../builtin-types/floating-point-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="a7d65-110">Any [built-in floating-point numeric type](../builtin-types/floating-point-numeric-types.md)</span></span>|<span data-ttu-id="a7d65-111">Ноль (0)</span><span class="sxs-lookup"><span data-stu-id="a7d65-111">0 (zero)</span></span>|
|[<span data-ttu-id="a7d65-112">bool</span><span class="sxs-lookup"><span data-stu-id="a7d65-112">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="a7d65-113">char</span><span class="sxs-lookup"><span data-stu-id="a7d65-113">char</span></span>](../builtin-types/char.md)|<span data-ttu-id="a7d65-114">`'\0'` (U+0000)</span><span class="sxs-lookup"><span data-stu-id="a7d65-114">`'\0'` (U+0000)</span></span>|
|[<span data-ttu-id="a7d65-115">enum</span><span class="sxs-lookup"><span data-stu-id="a7d65-115">enum</span></span>](enum.md)|<span data-ttu-id="a7d65-116">Значение, создаваемое выражением `(E)0`, где `E` — это идентификатор перечисления.</span><span class="sxs-lookup"><span data-stu-id="a7d65-116">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="a7d65-117">struct</span><span class="sxs-lookup"><span data-stu-id="a7d65-117">struct</span></span>](struct.md)|<span data-ttu-id="a7d65-118">Значение, создаваемое путем установки значений по умолчанию для всех полей с типами значений и значений `null` для всех полей ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="a7d65-118">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|<span data-ttu-id="a7d65-119">Любой [тип значения, допускающий значение NULL](../builtin-types/nullable-value-types.md)</span><span class="sxs-lookup"><span data-stu-id="a7d65-119">Any [nullable value type](../builtin-types/nullable-value-types.md)</span></span>|<span data-ttu-id="a7d65-120">Экземпляр, свойство `false` которого имеет значение <xref:System.Nullable%601.HasValue%2A>, а свойство <xref:System.Nullable%601.Value%2A> не определено.</span><span class="sxs-lookup"><span data-stu-id="a7d65-120">An instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span> <span data-ttu-id="a7d65-121">Это значение по умолчанию также называется значением *NULL* типа значения, допускающего значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a7d65-121">That default value is also known as the *null* value of a nullable value type.</span></span>|

<span data-ttu-id="a7d65-122">Используйте [оператор по умолчанию](../operators/default.md), чтобы получить значение типа по умолчанию, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a7d65-122">Use the [default operator](../operators/default.md) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="a7d65-123">Начиная с C# 7.1 вы можете использовать литерал [`default` ](../operators/default.md#default-literal) для инициализации переменной со значением по умолчанию для ее типа:</span><span class="sxs-lookup"><span data-stu-id="a7d65-123">Beginning with C# 7.1, you can use the [`default` literal](../operators/default.md#default-literal) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="a7d65-124">Для типа значения неявный конструктор без параметров также создает значение по умолчанию для типа, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a7d65-124">For a value type, the implicit parameterless constructor also produces the default value of the type, as the following example shows:</span></span>

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

## <a name="c-language-specification"></a><span data-ttu-id="a7d65-125">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a7d65-125">C# language specification</span></span>

<span data-ttu-id="a7d65-126">Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="a7d65-126">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="a7d65-127">Значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a7d65-127">Default values</span></span>](~/_csharplang/spec/variables.md#default-values)
- [<span data-ttu-id="a7d65-128">Конструкторы по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a7d65-128">Default constructors</span></span>](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a><span data-ttu-id="a7d65-129">См. также</span><span class="sxs-lookup"><span data-stu-id="a7d65-129">See also</span></span>

- [<span data-ttu-id="a7d65-130">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a7d65-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a7d65-131">Ключевые слова C#</span><span class="sxs-lookup"><span data-stu-id="a7d65-131">C# keywords</span></span>](index.md)
- [<span data-ttu-id="a7d65-132">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="a7d65-132">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="a7d65-133">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="a7d65-133">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)
