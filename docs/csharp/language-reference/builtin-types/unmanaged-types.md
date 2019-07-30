---
title: Справочник по C#. Неуправляемые типы
ms.date: 07/23/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 2b675be5dbc61006725549f4b69284326650401d
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512077"
---
# <a name="unmanaged-types-c-reference"></a><span data-ttu-id="18a58-102">Справочник по C#. Неуправляемые типы</span><span class="sxs-lookup"><span data-stu-id="18a58-102">Unmanaged types (C# reference)</span></span>

<span data-ttu-id="18a58-103">**Неуправляемый тип** — это любой тип, который не является ссылочным или сконструированным типом (включающим как минимум один аргумент типа) и не содержит поля ссылочного или сконструированного типа на любом уровне вложенности.</span><span class="sxs-lookup"><span data-stu-id="18a58-103">An **unmanaged type** is any type that isn't a reference type or constructed type (a type that includes at least one type argument), and doesn't contain reference type or constructed type fields at any level of nesting.</span></span> <span data-ttu-id="18a58-104">Другими словами, неуправляемым является один из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="18a58-104">In other words, an unmanaged type is one of the following:</span></span>

- <span data-ttu-id="18a58-105">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` или `bool`;</span><span class="sxs-lookup"><span data-stu-id="18a58-105">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal`, or `bool`</span></span>
- <span data-ttu-id="18a58-106">любой тип [перечисления](../keywords/enum.md);</span><span class="sxs-lookup"><span data-stu-id="18a58-106">Any [enum](../keywords/enum.md) type</span></span>
- <span data-ttu-id="18a58-107">любой тип [указателя](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="18a58-107">Any [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md) type</span></span>
- <span data-ttu-id="18a58-108">Любой пользовательский тип [структуры](../keywords/struct.md), который не является сконструированным и содержит поля только неуправляемых типов.</span><span class="sxs-lookup"><span data-stu-id="18a58-108">Any user-defined [struct](../keywords/struct.md) type that is not a constructed type and contains fields of unmanaged types only</span></span>

<span data-ttu-id="18a58-109">Начиная с C# 7.3 можно использовать [ограничение `unmanaged`](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint), чтобы указать, что параметр типа является отличным от указателя неуправляемым типом.</span><span class="sxs-lookup"><span data-stu-id="18a58-109">Beginning with C# 7.3, you can use the [`unmanaged` constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to specify that a type parameter is a non-pointer unmanaged type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="18a58-110">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="18a58-110">C# language specification</span></span>

<span data-ttu-id="18a58-111">Дополнительные сведения см. в разделе [Типы указателей](~/_csharplang/spec/unsafe-code.md#pointer-types) в статье [Спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="18a58-111">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="18a58-112">См. также</span><span class="sxs-lookup"><span data-stu-id="18a58-112">See also</span></span>

- [<span data-ttu-id="18a58-113">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="18a58-113">C# reference</span></span>](../index.md)
- [<span data-ttu-id="18a58-114">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="18a58-114">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="18a58-115">Типы, связанные с памятью и диапазонами</span><span class="sxs-lookup"><span data-stu-id="18a58-115">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="18a58-116">Оператор sizeof</span><span class="sxs-lookup"><span data-stu-id="18a58-116">sizeof operator</span></span>](../operators/sizeof.md)
- [<span data-ttu-id="18a58-117">Оператор stackalloc</span><span class="sxs-lookup"><span data-stu-id="18a58-117">stackalloc operator</span></span>](../operators/stackalloc.md)
