---
title: Справочник по C#. Таблица значений по умолчанию
ms.custom: seodec18
description: Узнайте значения по умолчанию для типов значений в C#.
ms.date: 08/23/2018
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.openlocfilehash: 19e9e4f94ab573f2313c185a08192d89103b98fd
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237042"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="de8ec-103">Таблица значений по умолчанию (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="de8ec-103">Default values table (C# Reference)</span></span>

<span data-ttu-id="de8ec-104">В следующей таблице показаны значения по умолчанию для [типов значений](value-types.md).</span><span class="sxs-lookup"><span data-stu-id="de8ec-104">The following table shows the default values of [value types](value-types.md).</span></span>

|<span data-ttu-id="de8ec-105">Тип значения</span><span class="sxs-lookup"><span data-stu-id="de8ec-105">Value type</span></span>|<span data-ttu-id="de8ec-106">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="de8ec-106">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="de8ec-107">bool</span><span class="sxs-lookup"><span data-stu-id="de8ec-107">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="de8ec-108">byte</span><span class="sxs-lookup"><span data-stu-id="de8ec-108">byte</span></span>](byte.md)|<span data-ttu-id="de8ec-109">0</span><span class="sxs-lookup"><span data-stu-id="de8ec-109">0</span></span>|
|[<span data-ttu-id="de8ec-110">char</span><span class="sxs-lookup"><span data-stu-id="de8ec-110">char</span></span>](char.md)|<span data-ttu-id="de8ec-111">'\0'</span><span class="sxs-lookup"><span data-stu-id="de8ec-111">'\0'</span></span>|
|[<span data-ttu-id="de8ec-112">decimal</span><span class="sxs-lookup"><span data-stu-id="de8ec-112">decimal</span></span>](decimal.md)|<span data-ttu-id="de8ec-113">0M</span><span class="sxs-lookup"><span data-stu-id="de8ec-113">0M</span></span>|
|[<span data-ttu-id="de8ec-114">double</span><span class="sxs-lookup"><span data-stu-id="de8ec-114">double</span></span>](double.md)|<span data-ttu-id="de8ec-115">0,0D</span><span class="sxs-lookup"><span data-stu-id="de8ec-115">0.0D</span></span>|
|[<span data-ttu-id="de8ec-116">enum</span><span class="sxs-lookup"><span data-stu-id="de8ec-116">enum</span></span>](enum.md)|<span data-ttu-id="de8ec-117">Значение, создаваемое выражением `(E)0`, где `E` — это идентификатор перечисления.</span><span class="sxs-lookup"><span data-stu-id="de8ec-117">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="de8ec-118">float</span><span class="sxs-lookup"><span data-stu-id="de8ec-118">float</span></span>](float.md)|<span data-ttu-id="de8ec-119">0,0F</span><span class="sxs-lookup"><span data-stu-id="de8ec-119">0.0F</span></span>|
|[<span data-ttu-id="de8ec-120">int</span><span class="sxs-lookup"><span data-stu-id="de8ec-120">int</span></span>](int.md)|<span data-ttu-id="de8ec-121">0</span><span class="sxs-lookup"><span data-stu-id="de8ec-121">0</span></span>|
|[<span data-ttu-id="de8ec-122">long</span><span class="sxs-lookup"><span data-stu-id="de8ec-122">long</span></span>](long.md)|<span data-ttu-id="de8ec-123">0L</span><span class="sxs-lookup"><span data-stu-id="de8ec-123">0L</span></span>|
|[<span data-ttu-id="de8ec-124">sbyte</span><span class="sxs-lookup"><span data-stu-id="de8ec-124">sbyte</span></span>](sbyte.md)|<span data-ttu-id="de8ec-125">0</span><span class="sxs-lookup"><span data-stu-id="de8ec-125">0</span></span>|
|[<span data-ttu-id="de8ec-126">short</span><span class="sxs-lookup"><span data-stu-id="de8ec-126">short</span></span>](short.md)|<span data-ttu-id="de8ec-127">0</span><span class="sxs-lookup"><span data-stu-id="de8ec-127">0</span></span>|
|[<span data-ttu-id="de8ec-128">struct</span><span class="sxs-lookup"><span data-stu-id="de8ec-128">struct</span></span>](struct.md)|<span data-ttu-id="de8ec-129">Значение, создаваемое путем установки значений по умолчанию для всех полей с типами значений и значений `null` для всех полей ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="de8ec-129">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="de8ec-130">uint</span><span class="sxs-lookup"><span data-stu-id="de8ec-130">uint</span></span>](uint.md)|<span data-ttu-id="de8ec-131">0</span><span class="sxs-lookup"><span data-stu-id="de8ec-131">0</span></span>|
|[<span data-ttu-id="de8ec-132">ulong</span><span class="sxs-lookup"><span data-stu-id="de8ec-132">ulong</span></span>](ulong.md)|<span data-ttu-id="de8ec-133">0</span><span class="sxs-lookup"><span data-stu-id="de8ec-133">0</span></span>|
|[<span data-ttu-id="de8ec-134">ushort</span><span class="sxs-lookup"><span data-stu-id="de8ec-134">ushort</span></span>](ushort.md)|<span data-ttu-id="de8ec-135">0</span><span class="sxs-lookup"><span data-stu-id="de8ec-135">0</span></span>|

## <a name="remarks"></a><span data-ttu-id="de8ec-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="de8ec-136">Remarks</span></span>

<span data-ttu-id="de8ec-137">Неинициализированные переменные нельзя использовать в C#.</span><span class="sxs-lookup"><span data-stu-id="de8ec-137">You cannot use uninitialized variables in C#.</span></span> <span data-ttu-id="de8ec-138">Вы можете инициализировать переменную со значением по умолчанию для ее типа.</span><span class="sxs-lookup"><span data-stu-id="de8ec-138">You can initialize a variable with the default value of its type.</span></span> <span data-ttu-id="de8ec-139">Вы также можете использовать значение типа по умолчанию для указания значения по умолчанию [необязательного аргумента](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments) метода.</span><span class="sxs-lookup"><span data-stu-id="de8ec-139">You also can use the default value of a type to specify the default value of a method's [optional argument](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments).</span></span>

<span data-ttu-id="de8ec-140">Используйте [выражение значения по умолчанию](../../programming-guide/statements-expressions-operators/default-value-expressions.md), чтобы получить значение типа по умолчанию, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="de8ec-140">Use the [default value expression](../../programming-guide/statements-expressions-operators/default-value-expressions.md) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="de8ec-141">Начиная с C# 7.1 вы можете использовать литерал [`default` ](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) для инициализации переменной со значением по умолчанию для ее типа:</span><span class="sxs-lookup"><span data-stu-id="de8ec-141">Beginning with C# 7.1, you can use the [`default` literal](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="de8ec-142">Также можно использовать конструктор по умолчанию или неявный конструктор по умолчанию, чтобы получить значение по умолчанию для типа значения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="de8ec-142">You also can use the default constructor or the implicit default constructor to produce the default value of a value type, as the following example shows.</span></span> <span data-ttu-id="de8ec-143">Дополнительные сведения о конструкторах см. в статье [Конструкторы](../../programming-guide/classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="de8ec-143">For more information about constructors, see the [Constructors](../../programming-guide/classes-and-structs/constructors.md) article.</span></span>

```csharp
int a = new int();
```

<span data-ttu-id="de8ec-144">Значение по умолчанию любого [ссылочного типа](reference-types.md) — `null`.</span><span class="sxs-lookup"><span data-stu-id="de8ec-144">The default value of any [reference type](reference-types.md) is `null`.</span></span> <span data-ttu-id="de8ec-145">Значение по умолчанию для [типа, допускающего значение null](../../programming-guide/nullable-types/index.md), — это экземпляр, свойство <xref:System.Nullable%601.HasValue%2A> которого имеет значение `false` и свойство <xref:System.Nullable%601.Value%2A> которого не определено.</span><span class="sxs-lookup"><span data-stu-id="de8ec-145">The default value of a [nullable type](../../programming-guide/nullable-types/index.md) is an instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span>

## <a name="see-also"></a><span data-ttu-id="de8ec-146">См. также</span><span class="sxs-lookup"><span data-stu-id="de8ec-146">See also</span></span>

- [<span data-ttu-id="de8ec-147">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="de8ec-147">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="de8ec-148">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="de8ec-148">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="de8ec-149">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="de8ec-149">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="de8ec-150">Справочные таблицы по типам</span><span class="sxs-lookup"><span data-stu-id="de8ec-150">Reference tables for types</span></span>](reference-tables-for-types.md)
- [<span data-ttu-id="de8ec-151">Типы значений</span><span class="sxs-lookup"><span data-stu-id="de8ec-151">Value types</span></span>](value-types.md)
- [<span data-ttu-id="de8ec-152">Таблица типов значений</span><span class="sxs-lookup"><span data-stu-id="de8ec-152">Value types table</span></span>](value-types-table.md)
- [<span data-ttu-id="de8ec-153">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="de8ec-153">Built-in types table</span></span>](built-in-types-table.md)
