---
title: Справочник по C#. Оператор sizeof
ms.date: 07/25/2019
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: 8e4518718d0975f8b4a65870f15d8c52d692c2f5
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77625739"
---
# <a name="sizeof-operator-c-reference"></a><span data-ttu-id="8bb01-102">Справочник по C#. Оператор sizeof</span><span class="sxs-lookup"><span data-stu-id="8bb01-102">sizeof operator (C# reference)</span></span>

<span data-ttu-id="8bb01-103">Оператор `sizeof` позволяет получать число байт, занятых переменной заданного типа.</span><span class="sxs-lookup"><span data-stu-id="8bb01-103">The `sizeof` operator returns the number of bytes occupied by a variable of a given type.</span></span> <span data-ttu-id="8bb01-104">Аргумент оператора `sizeof` должен быть именем [неуправляемого типа](../builtin-types/unmanaged-types.md) или параметром типа, к которому применяется [ограничение](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint), указывающее, что он является неуправляемым типом.</span><span class="sxs-lookup"><span data-stu-id="8bb01-104">The argument to the `sizeof` operator must be the name of an [unmanaged type](../builtin-types/unmanaged-types.md) or a type parameter that is [constrained](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to be an unmanaged type.</span></span>

<span data-ttu-id="8bb01-105">Для использования оператора `sizeof` требуется [небезопасный](../keywords/unsafe.md) контекст.</span><span class="sxs-lookup"><span data-stu-id="8bb01-105">The `sizeof` operator requires an [unsafe](../keywords/unsafe.md) context.</span></span> <span data-ttu-id="8bb01-106">Однако выражения, приведенные в следующей таблице, вычисляются во время компиляции для получения соответствующих константных значений и им не требуется небезопасный контекст.</span><span class="sxs-lookup"><span data-stu-id="8bb01-106">However, the expressions presented in the following table are evaluated in compile time to the corresponding constant values and don't require an unsafe context:</span></span>

|<span data-ttu-id="8bb01-107">Выражение</span><span class="sxs-lookup"><span data-stu-id="8bb01-107">Expression</span></span>|<span data-ttu-id="8bb01-108">Константа</span><span class="sxs-lookup"><span data-stu-id="8bb01-108">Constant value</span></span>|
|---------|---------------|
|`sizeof(sbyte)`|<span data-ttu-id="8bb01-109">1</span><span class="sxs-lookup"><span data-stu-id="8bb01-109">1</span></span>|
|`sizeof(byte)`|<span data-ttu-id="8bb01-110">1</span><span class="sxs-lookup"><span data-stu-id="8bb01-110">1</span></span>|
|`sizeof(short)`|<span data-ttu-id="8bb01-111">2</span><span class="sxs-lookup"><span data-stu-id="8bb01-111">2</span></span>|
|`sizeof(ushort)`|<span data-ttu-id="8bb01-112">2</span><span class="sxs-lookup"><span data-stu-id="8bb01-112">2</span></span>|
|`sizeof(int)`|<span data-ttu-id="8bb01-113">4</span><span class="sxs-lookup"><span data-stu-id="8bb01-113">4</span></span>|
|`sizeof(uint)`|<span data-ttu-id="8bb01-114">4</span><span class="sxs-lookup"><span data-stu-id="8bb01-114">4</span></span>|
|`sizeof(long)`|<span data-ttu-id="8bb01-115">8</span><span class="sxs-lookup"><span data-stu-id="8bb01-115">8</span></span>|
|`sizeof(ulong)`|<span data-ttu-id="8bb01-116">8</span><span class="sxs-lookup"><span data-stu-id="8bb01-116">8</span></span>|
|`sizeof(char)`|<span data-ttu-id="8bb01-117">2</span><span class="sxs-lookup"><span data-stu-id="8bb01-117">2</span></span>|
|`sizeof(float)`|<span data-ttu-id="8bb01-118">4</span><span class="sxs-lookup"><span data-stu-id="8bb01-118">4</span></span>|
|`sizeof(double)`|<span data-ttu-id="8bb01-119">8</span><span class="sxs-lookup"><span data-stu-id="8bb01-119">8</span></span>|
|`sizeof(decimal)`|<span data-ttu-id="8bb01-120">16</span><span class="sxs-lookup"><span data-stu-id="8bb01-120">16</span></span>|
|`sizeof(bool)`|<span data-ttu-id="8bb01-121">1</span><span class="sxs-lookup"><span data-stu-id="8bb01-121">1</span></span>|

<span data-ttu-id="8bb01-122">Небезопасный контекст также не требуется, если операнд оператора `sizeof` является именем [перечисляемого](../builtin-types/enum.md) типа.</span><span class="sxs-lookup"><span data-stu-id="8bb01-122">You also don't need to use an unsafe context when the operand of the `sizeof` operator is the name of an [enum](../builtin-types/enum.md) type.</span></span>

<span data-ttu-id="8bb01-123">В следующем примере иллюстрируется использование оператора `sizeof`.</span><span class="sxs-lookup"><span data-stu-id="8bb01-123">The following example demonstrates the usage of the `sizeof` operator:</span></span>

[!code-csharp[sizeof examples](~/samples/csharp/language-reference/operators/SizeOfOperator.cs)]

<span data-ttu-id="8bb01-124">Оператор `sizeof` возвращает число байт, выделяемых средой CLR в управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="8bb01-124">The `sizeof` operator returns a number of bytes that would be allocated by the common language runtime in managed memory.</span></span> <span data-ttu-id="8bb01-125">Для типов [структуры](../builtin-types/struct.md) в это значение входит любое заполнение, как показано в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="8bb01-125">For [struct](../builtin-types/struct.md) types, that value includes any padding, as the preceding example demonstrates.</span></span> <span data-ttu-id="8bb01-126">Результат использования оператора `sizeof` может отличаться от результата работы метода <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>, который возвращает размер типа в *неуправляемой* памяти.</span><span class="sxs-lookup"><span data-stu-id="8bb01-126">The result of the `sizeof` operator might differ from the result of the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, which returns the size of a type in *unmanaged* memory.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8bb01-127">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="8bb01-127">C# language specification</span></span>

<span data-ttu-id="8bb01-128">Дополнительные сведения см. в разделе [Оператор sizeof](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator)[спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="8bb01-128">For more information, see [The sizeof operator](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8bb01-129">См. также</span><span class="sxs-lookup"><span data-stu-id="8bb01-129">See also</span></span>

- [<span data-ttu-id="8bb01-130">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="8bb01-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="8bb01-131">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="8bb01-131">C# operators</span></span>](index.md)
- [<span data-ttu-id="8bb01-132">Операторы, связанные с указателем</span><span class="sxs-lookup"><span data-stu-id="8bb01-132">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="8bb01-133">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="8bb01-133">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="8bb01-134">Типы, связанные с памятью и диапазонами</span><span class="sxs-lookup"><span data-stu-id="8bb01-134">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="8bb01-135">Универсальные шаблоны в .NET</span><span class="sxs-lookup"><span data-stu-id="8bb01-135">Generics in .NET</span></span>](../../../standard/generics/index.md)
