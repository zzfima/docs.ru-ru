---
title: Справочник по C#. Оператор sizeof
ms.custom: seodec18
ms.date: 07/25/2019
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: 4852e1166a975b1a45c5bd905123a35fc846aa28
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513128"
---
# <a name="sizeof-operator-c-reference"></a><span data-ttu-id="56042-102">Справочник по C#. Оператор sizeof</span><span class="sxs-lookup"><span data-stu-id="56042-102">sizeof operator (C# reference)</span></span>

<span data-ttu-id="56042-103">Оператор `sizeof` позволяет получать число байт, занятых переменной заданного типа.</span><span class="sxs-lookup"><span data-stu-id="56042-103">The `sizeof` operator returns the number of bytes occupied by a variable of a given type.</span></span> <span data-ttu-id="56042-104">Аргумент оператора `sizeof` должен быть именем [неуправляемого типа](../builtin-types/unmanaged-types.md) или параметром типа, к которому применяется [ограничение](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint), указывающее, что он является неуправляемым типом.</span><span class="sxs-lookup"><span data-stu-id="56042-104">An argument of the `sizeof` operator must be the name of an [unmanaged type](../builtin-types/unmanaged-types.md) or a type parameter that is [constrained](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to be an unmanaged type.</span></span>

<span data-ttu-id="56042-105">Для использования оператора `sizeof` требуется [небезопасный](../keywords/unsafe.md) контекст.</span><span class="sxs-lookup"><span data-stu-id="56042-105">The `sizeof` operator requires an [unsafe](../keywords/unsafe.md) context.</span></span> <span data-ttu-id="56042-106">Однако выражения, приведенные в следующей таблице, вычисляются во время компиляции для получения соответствующих константных значений и им не требуется небезопасный контекст.</span><span class="sxs-lookup"><span data-stu-id="56042-106">However, the expressions presented in the following table are evaluated in compile time to the corresponding constant values and don't require an unsafe context:</span></span>

|<span data-ttu-id="56042-107">Выражение</span><span class="sxs-lookup"><span data-stu-id="56042-107">Expression</span></span>|<span data-ttu-id="56042-108">Константа</span><span class="sxs-lookup"><span data-stu-id="56042-108">Constant value</span></span>|
|---------|---------------|
|`sizeof(sbyte)`|<span data-ttu-id="56042-109">1</span><span class="sxs-lookup"><span data-stu-id="56042-109">1</span></span>|
|`sizeof(byte)`|<span data-ttu-id="56042-110">1</span><span class="sxs-lookup"><span data-stu-id="56042-110">1</span></span>|
|`sizeof(short)`|<span data-ttu-id="56042-111">2</span><span class="sxs-lookup"><span data-stu-id="56042-111">2</span></span>|
|`sizeof(ushort)`|<span data-ttu-id="56042-112">2</span><span class="sxs-lookup"><span data-stu-id="56042-112">2</span></span>|
|`sizeof(int)`|<span data-ttu-id="56042-113">4</span><span class="sxs-lookup"><span data-stu-id="56042-113">4</span></span>|
|`sizeof(uint)`|<span data-ttu-id="56042-114">4</span><span class="sxs-lookup"><span data-stu-id="56042-114">4</span></span>|
|`sizeof(long)`|<span data-ttu-id="56042-115">8</span><span class="sxs-lookup"><span data-stu-id="56042-115">8</span></span>|
|`sizeof(ulong)`|<span data-ttu-id="56042-116">8</span><span class="sxs-lookup"><span data-stu-id="56042-116">8</span></span>|
|`sizeof(char)`|<span data-ttu-id="56042-117">2</span><span class="sxs-lookup"><span data-stu-id="56042-117">2</span></span>|
|`sizeof(float)`|<span data-ttu-id="56042-118">4</span><span class="sxs-lookup"><span data-stu-id="56042-118">4</span></span>|
|`sizeof(double)`|<span data-ttu-id="56042-119">8</span><span class="sxs-lookup"><span data-stu-id="56042-119">8</span></span>|
|`sizeof(decimal)`|<span data-ttu-id="56042-120">16</span><span class="sxs-lookup"><span data-stu-id="56042-120">16</span></span>|
|`sizeof(bool)`|<span data-ttu-id="56042-121">1</span><span class="sxs-lookup"><span data-stu-id="56042-121">1</span></span>|

<span data-ttu-id="56042-122">Небезопасный контекст также не требуется, если операнд оператора `sizeof` является именем [перечисляемого](../keywords/enum.md) типа.</span><span class="sxs-lookup"><span data-stu-id="56042-122">You also don't need to use an unsafe context when the operand of the `sizeof` operator is the name of an [enum](../keywords/enum.md) type.</span></span>

<span data-ttu-id="56042-123">В следующем примере иллюстрируется использование оператора `sizeof`.</span><span class="sxs-lookup"><span data-stu-id="56042-123">The following example demonstrates the usage of the `sizeof` operator:</span></span>

[!code-csharp[sizeof examples](~/samples/csharp/language-reference/operators/SizeOfOperator.cs)]

<span data-ttu-id="56042-124">Оператор `sizeof` возвращает число байт, выделяемых средой CLR в управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="56042-124">The `sizeof` operator returns a number of bytes that would be allocated by the common language runtime in managed memory.</span></span> <span data-ttu-id="56042-125">Для типов [структуры](../keywords/struct.md) в это значение входит любое заполнение, как показано в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="56042-125">For [struct](../keywords/struct.md) types, that value includes any padding, as the preceding example demonstrates.</span></span> <span data-ttu-id="56042-126">Результат использования оператора `sizeof` может отличаться от результата работы метода <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>, который возвращает размер типа в *неуправляемой* памяти.</span><span class="sxs-lookup"><span data-stu-id="56042-126">The result of the `sizeof` operator might differ from the result of the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, which returns the size of a type in *unmanaged* memory.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="56042-127">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="56042-127">C# language specification</span></span>

<span data-ttu-id="56042-128">Дополнительные сведения см. в разделе [Оператор sizeof](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="56042-128">For more information, see [The sizeof operator](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="56042-129">См. также</span><span class="sxs-lookup"><span data-stu-id="56042-129">See also</span></span>

- [<span data-ttu-id="56042-130">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="56042-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="56042-131">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="56042-131">C# operators</span></span>](index.md)
- [<span data-ttu-id="56042-132">Операторы, связанные с указателем</span><span class="sxs-lookup"><span data-stu-id="56042-132">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="56042-133">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="56042-133">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="56042-134">Типы, связанные с памятью и диапазонами</span><span class="sxs-lookup"><span data-stu-id="56042-134">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
