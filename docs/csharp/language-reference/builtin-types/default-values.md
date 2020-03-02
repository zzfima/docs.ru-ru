---
title: Значения по умолчанию типов C# — справка по C#
description: Ознакомьтесь со значениями по умолчанию таких типов C#, как bool, char, int, float, double и др.
ms.date: 12/18/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: 93b6079b9a3bbf6d537094cab9dfb305ace7f6bf
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77625869"
---
# <a name="default-values-of-c-types-c-reference"></a><span data-ttu-id="c1216-103">Значения по умолчанию типов C# (справка по C#)</span><span class="sxs-lookup"><span data-stu-id="c1216-103">Default values of C# types (C# reference)</span></span>

<span data-ttu-id="c1216-104">В следующей таблице показаны значения по умолчанию для типов C#:</span><span class="sxs-lookup"><span data-stu-id="c1216-104">The following table shows the default values of C# types:</span></span>

|<span data-ttu-id="c1216-105">Type</span><span class="sxs-lookup"><span data-stu-id="c1216-105">Type</span></span>|<span data-ttu-id="c1216-106">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="c1216-106">Default value</span></span>|
|---------|------------------|
|<span data-ttu-id="c1216-107">любой ссылочный тип;</span><span class="sxs-lookup"><span data-stu-id="c1216-107">Any reference type</span></span>|`null`|
|<span data-ttu-id="c1216-108">Любой [встроенный целочисленный тип](integral-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="c1216-108">Any [built-in integral numeric type](integral-numeric-types.md)</span></span>|<span data-ttu-id="c1216-109">Ноль (0)</span><span class="sxs-lookup"><span data-stu-id="c1216-109">0 (zero)</span></span>|
|<span data-ttu-id="c1216-110">Любой [встроенный тип с плавающей запятой](floating-point-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="c1216-110">Any [built-in floating-point numeric type](floating-point-numeric-types.md)</span></span>|<span data-ttu-id="c1216-111">Ноль (0)</span><span class="sxs-lookup"><span data-stu-id="c1216-111">0 (zero)</span></span>|
|[<span data-ttu-id="c1216-112">bool</span><span class="sxs-lookup"><span data-stu-id="c1216-112">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="c1216-113">char</span><span class="sxs-lookup"><span data-stu-id="c1216-113">char</span></span>](char.md)|<span data-ttu-id="c1216-114">`'\0'` (U+0000)</span><span class="sxs-lookup"><span data-stu-id="c1216-114">`'\0'` (U+0000)</span></span>|
|[<span data-ttu-id="c1216-115">enum</span><span class="sxs-lookup"><span data-stu-id="c1216-115">enum</span></span>](enum.md)|<span data-ttu-id="c1216-116">Значение, создаваемое выражением `(E)0`, где `E` — это идентификатор перечисления.</span><span class="sxs-lookup"><span data-stu-id="c1216-116">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="c1216-117">struct</span><span class="sxs-lookup"><span data-stu-id="c1216-117">struct</span></span>](struct.md)|<span data-ttu-id="c1216-118">Значение, создаваемое путем установки значений по умолчанию для всех полей с типами значений и значений `null` для всех полей ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="c1216-118">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|<span data-ttu-id="c1216-119">Любой [тип значения, допускающий значение NULL](nullable-value-types.md)</span><span class="sxs-lookup"><span data-stu-id="c1216-119">Any [nullable value type](nullable-value-types.md)</span></span>|<span data-ttu-id="c1216-120">Экземпляр, свойство `false` которого имеет значение <xref:System.Nullable%601.HasValue%2A>, а свойство <xref:System.Nullable%601.Value%2A> не определено.</span><span class="sxs-lookup"><span data-stu-id="c1216-120">An instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span> <span data-ttu-id="c1216-121">Это значение по умолчанию также называется значением *NULL* типа значения, допускающего значение NULL.</span><span class="sxs-lookup"><span data-stu-id="c1216-121">That default value is also known as the *null* value of a nullable value type.</span></span>|

<span data-ttu-id="c1216-122">Используйте [оператор по умолчанию](../operators/default.md), чтобы получить значение типа по умолчанию, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="c1216-122">Use the [default operator](../operators/default.md) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="c1216-123">Начиная с C# 7.1 вы можете использовать литерал [`default`](../operators/default.md#default-literal) для инициализации переменной со значением по умолчанию для ее типа:</span><span class="sxs-lookup"><span data-stu-id="c1216-123">Beginning with C# 7.1, you can use the [`default` literal](../operators/default.md#default-literal) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="c1216-124">Для типа значения неявный конструктор без параметров также создает значение по умолчанию для типа, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="c1216-124">For a value type, the implicit parameterless constructor also produces the default value of the type, as the following example shows:</span></span>

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

<span data-ttu-id="c1216-125">Если экземпляр <xref:System.Type?displayProperty=nameWithType> представляет тип значения, во время выполнения можно использовать метод <xref:System.Activator.CreateInstance(System.Type)?displayProperty=nameWithType>, чтобы вызвать конструктор без параметров и получить значение типа по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c1216-125">At run time, if the <xref:System.Type?displayProperty=nameWithType> instance represents a value type, you can use the <xref:System.Activator.CreateInstance(System.Type)?displayProperty=nameWithType> method to invoke the parameterless constructor to obtain the default value of the type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c1216-126">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="c1216-126">C# language specification</span></span>

<span data-ttu-id="c1216-127">Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="c1216-127">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="c1216-128">Значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="c1216-128">Default values</span></span>](~/_csharplang/spec/variables.md#default-values)
- [<span data-ttu-id="c1216-129">Конструкторы по умолчанию</span><span class="sxs-lookup"><span data-stu-id="c1216-129">Default constructors</span></span>](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a><span data-ttu-id="c1216-130">См. также</span><span class="sxs-lookup"><span data-stu-id="c1216-130">See also</span></span>

- [<span data-ttu-id="c1216-131">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="c1216-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c1216-132">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="c1216-132">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)
