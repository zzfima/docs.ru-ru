---
title: Справочник по C#. Таблица значений по умолчанию
ms.custom: seodec18
description: Узнайте значения по умолчанию для типов значений в C#.
ms.date: 08/23/2018
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- parameterless constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], parameterless constructor
- types [C#], parameterless constructor return values
ms.openlocfilehash: 4fc9a35f69540e047a97c21788015ca8e54068a0
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422030"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="d8490-103">Таблица значений по умолчанию (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="d8490-103">Default values table (C# Reference)</span></span>

<span data-ttu-id="d8490-104">В следующей таблице показаны значения по умолчанию для [типов значений](value-types.md).</span><span class="sxs-lookup"><span data-stu-id="d8490-104">The following table shows the default values of [value types](value-types.md).</span></span>

|<span data-ttu-id="d8490-105">Тип значения</span><span class="sxs-lookup"><span data-stu-id="d8490-105">Value type</span></span>|<span data-ttu-id="d8490-106">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d8490-106">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="d8490-107">bool</span><span class="sxs-lookup"><span data-stu-id="d8490-107">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="d8490-108">byte</span><span class="sxs-lookup"><span data-stu-id="d8490-108">byte</span></span>](byte.md)|<span data-ttu-id="d8490-109">0</span><span class="sxs-lookup"><span data-stu-id="d8490-109">0</span></span>|
|[<span data-ttu-id="d8490-110">char</span><span class="sxs-lookup"><span data-stu-id="d8490-110">char</span></span>](char.md)|<span data-ttu-id="d8490-111">'\0'</span><span class="sxs-lookup"><span data-stu-id="d8490-111">'\0'</span></span>|
|[<span data-ttu-id="d8490-112">decimal</span><span class="sxs-lookup"><span data-stu-id="d8490-112">decimal</span></span>](decimal.md)|<span data-ttu-id="d8490-113">0M</span><span class="sxs-lookup"><span data-stu-id="d8490-113">0M</span></span>|
|[<span data-ttu-id="d8490-114">double</span><span class="sxs-lookup"><span data-stu-id="d8490-114">double</span></span>](double.md)|<span data-ttu-id="d8490-115">0,0D</span><span class="sxs-lookup"><span data-stu-id="d8490-115">0.0D</span></span>|
|[<span data-ttu-id="d8490-116">enum</span><span class="sxs-lookup"><span data-stu-id="d8490-116">enum</span></span>](enum.md)|<span data-ttu-id="d8490-117">Значение, создаваемое выражением `(E)0`, где `E` — это идентификатор перечисления.</span><span class="sxs-lookup"><span data-stu-id="d8490-117">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="d8490-118">float</span><span class="sxs-lookup"><span data-stu-id="d8490-118">float</span></span>](float.md)|<span data-ttu-id="d8490-119">0,0F</span><span class="sxs-lookup"><span data-stu-id="d8490-119">0.0F</span></span>|
|[<span data-ttu-id="d8490-120">int</span><span class="sxs-lookup"><span data-stu-id="d8490-120">int</span></span>](int.md)|<span data-ttu-id="d8490-121">0</span><span class="sxs-lookup"><span data-stu-id="d8490-121">0</span></span>|
|[<span data-ttu-id="d8490-122">long</span><span class="sxs-lookup"><span data-stu-id="d8490-122">long</span></span>](long.md)|<span data-ttu-id="d8490-123">0L</span><span class="sxs-lookup"><span data-stu-id="d8490-123">0L</span></span>|
|[<span data-ttu-id="d8490-124">sbyte</span><span class="sxs-lookup"><span data-stu-id="d8490-124">sbyte</span></span>](sbyte.md)|<span data-ttu-id="d8490-125">0</span><span class="sxs-lookup"><span data-stu-id="d8490-125">0</span></span>|
|[<span data-ttu-id="d8490-126">short</span><span class="sxs-lookup"><span data-stu-id="d8490-126">short</span></span>](short.md)|<span data-ttu-id="d8490-127">0</span><span class="sxs-lookup"><span data-stu-id="d8490-127">0</span></span>|
|[<span data-ttu-id="d8490-128">struct</span><span class="sxs-lookup"><span data-stu-id="d8490-128">struct</span></span>](struct.md)|<span data-ttu-id="d8490-129">Значение, создаваемое путем установки значений по умолчанию для всех полей с типами значений и значений `null` для всех полей ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="d8490-129">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="d8490-130">uint</span><span class="sxs-lookup"><span data-stu-id="d8490-130">uint</span></span>](uint.md)|<span data-ttu-id="d8490-131">0</span><span class="sxs-lookup"><span data-stu-id="d8490-131">0</span></span>|
|[<span data-ttu-id="d8490-132">ulong</span><span class="sxs-lookup"><span data-stu-id="d8490-132">ulong</span></span>](ulong.md)|<span data-ttu-id="d8490-133">0</span><span class="sxs-lookup"><span data-stu-id="d8490-133">0</span></span>|
|[<span data-ttu-id="d8490-134">ushort</span><span class="sxs-lookup"><span data-stu-id="d8490-134">ushort</span></span>](ushort.md)|<span data-ttu-id="d8490-135">0</span><span class="sxs-lookup"><span data-stu-id="d8490-135">0</span></span>|

## <a name="remarks"></a><span data-ttu-id="d8490-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="d8490-136">Remarks</span></span>

<span data-ttu-id="d8490-137">Неинициализированные переменные нельзя использовать в C#.</span><span class="sxs-lookup"><span data-stu-id="d8490-137">You cannot use uninitialized variables in C#.</span></span> <span data-ttu-id="d8490-138">Вы можете инициализировать переменную со значением по умолчанию для ее типа.</span><span class="sxs-lookup"><span data-stu-id="d8490-138">You can initialize a variable with the default value of its type.</span></span> <span data-ttu-id="d8490-139">Вы также можете использовать значение типа по умолчанию для указания значения по умолчанию [необязательного аргумента](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments) метода.</span><span class="sxs-lookup"><span data-stu-id="d8490-139">You also can use the default value of a type to specify the default value of a method's [optional argument](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments).</span></span>

<span data-ttu-id="d8490-140">Используйте [выражение значения по умолчанию](../../programming-guide/statements-expressions-operators/default-value-expressions.md), чтобы получить значение типа по умолчанию, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d8490-140">Use the [default value expression](../../programming-guide/statements-expressions-operators/default-value-expressions.md) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="d8490-141">Начиная с C# 7.1 вы можете использовать литерал [`default` ](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) для инициализации переменной со значением по умолчанию для ее типа:</span><span class="sxs-lookup"><span data-stu-id="d8490-141">Beginning with C# 7.1, you can use the [`default` literal](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="d8490-142">Также можно использовать конструктор без параметров или неявный конструктор без параметров, чтобы получить значение по умолчанию для типа значения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d8490-142">You also can use the parameterless constructor or the implicit parameterless constructor to produce the default value of a value type, as the following example shows.</span></span> <span data-ttu-id="d8490-143">Дополнительные сведения о конструкторах см. в статье [Конструкторы](../../programming-guide/classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="d8490-143">For more information about constructors, see the [Constructors](../../programming-guide/classes-and-structs/constructors.md) article.</span></span>

```csharp
int a = new int();
```

<span data-ttu-id="d8490-144">Значение по умолчанию любого [ссылочного типа](reference-types.md) — `null`.</span><span class="sxs-lookup"><span data-stu-id="d8490-144">The default value of any [reference type](reference-types.md) is `null`.</span></span> <span data-ttu-id="d8490-145">Значение по умолчанию для [типа, допускающего значение null](../../programming-guide/nullable-types/index.md), — это экземпляр, свойство <xref:System.Nullable%601.HasValue%2A> которого имеет значение `false` и свойство <xref:System.Nullable%601.Value%2A> которого не определено.</span><span class="sxs-lookup"><span data-stu-id="d8490-145">The default value of a [nullable type](../../programming-guide/nullable-types/index.md) is an instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8490-146">См. также</span><span class="sxs-lookup"><span data-stu-id="d8490-146">See also</span></span>

- [<span data-ttu-id="d8490-147">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="d8490-147">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d8490-148">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d8490-148">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d8490-149">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="d8490-149">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="d8490-150">Типы значений</span><span class="sxs-lookup"><span data-stu-id="d8490-150">Value types</span></span>](value-types.md)
- [<span data-ttu-id="d8490-151">Таблица типов значений</span><span class="sxs-lookup"><span data-stu-id="d8490-151">Value types table</span></span>](value-types-table.md)
- [<span data-ttu-id="d8490-152">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="d8490-152">Built-in types table</span></span>](built-in-types-table.md)
