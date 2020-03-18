---
title: Справочник по C#. Неуправляемые типы
ms.date: 09/06/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 8a4599514115aa21f17c32848ce203fea704072e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846472"
---
# <a name="unmanaged-types-c-reference"></a><span data-ttu-id="3d56e-102">Справочник по C#. Неуправляемые типы</span><span class="sxs-lookup"><span data-stu-id="3d56e-102">Unmanaged types (C# reference)</span></span>

<span data-ttu-id="3d56e-103">Тип является **неуправляемым типом**, если он принадлежит к одному из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="3d56e-103">A type is an **unmanaged type** if it's any of the following types:</span></span>

- <span data-ttu-id="3d56e-104">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` или `bool`;</span><span class="sxs-lookup"><span data-stu-id="3d56e-104">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal`, or `bool`</span></span>
- <span data-ttu-id="3d56e-105">любой тип [перечисления](enum.md);</span><span class="sxs-lookup"><span data-stu-id="3d56e-105">Any [enum](enum.md) type</span></span>
- <span data-ttu-id="3d56e-106">любой тип [указателя](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="3d56e-106">Any [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md) type</span></span>
- <span data-ttu-id="3d56e-107">Любой определенный пользователем тип [структуры](struct.md), который содержит поля только неуправляемых типов в C# 7.3 и более ранних версиях, не является сконструированным типом (тип, который включает по крайней мере один аргумент типа)</span><span class="sxs-lookup"><span data-stu-id="3d56e-107">Any user-defined [struct](struct.md) type that contains fields of unmanaged types only and, in C# 7.3 and earlier, is not a constructed type (a type that includes at least one type argument)</span></span>

<span data-ttu-id="3d56e-108">Начиная с C# 7.3 можно использовать [ограничение `unmanaged`](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint), чтобы указать, что параметр типа является отличным от указателя неуправляемым типом, не допускающим значения NULL.</span><span class="sxs-lookup"><span data-stu-id="3d56e-108">Beginning with C# 7.3, you can use the [`unmanaged` constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to specify that a type parameter is a non-pointer, non-nullable unmanaged type.</span></span>

<span data-ttu-id="3d56e-109">Начиная с C# 8.0, *сконструированный* тип структуры, содержащий поля только неуправляемых типов, также является неуправляемым, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="3d56e-109">Beginning with C# 8.0, a *constructed* struct type that contains fields of unmanaged types only is also unmanaged, as the following example shows:</span></span>

[!code-csharp[unmanaged constructed types](snippets/UnmanagedTypes.cs#ProgramExample)]

<span data-ttu-id="3d56e-110">Универсальная структура может быть источником как для неуправляемых сконструированных типов, так и для сконструированных типов, отличных от неуправляемых.</span><span class="sxs-lookup"><span data-stu-id="3d56e-110">A generic struct may be the source of both unmanaged and not unmanaged constructed types.</span></span> <span data-ttu-id="3d56e-111">В предыдущем примере определяется универсальная структура `Coords<T>`, а также представлены примеры неуправляемых сконструированных типов.</span><span class="sxs-lookup"><span data-stu-id="3d56e-111">The preceding example defines a generic struct `Coords<T>` and presents the examples of unmanaged constructed types.</span></span> <span data-ttu-id="3d56e-112">Примером типа, отличного от неуправляемого, является `Coords<object>`.</span><span class="sxs-lookup"><span data-stu-id="3d56e-112">The example of not an unmanaged type is `Coords<object>`.</span></span> <span data-ttu-id="3d56e-113">Он не является неуправляемым, так как содержит поля типа `object`, которые являются отличными от неуправляемых.</span><span class="sxs-lookup"><span data-stu-id="3d56e-113">It's not unmanaged because it has the fields of the `object` type, which is not unmanaged.</span></span> <span data-ttu-id="3d56e-114">Если необходимо, чтобы *все* сконструированные типы были неуправляемыми, используйте ограничение `unmanaged` в определении универсальной структуры:</span><span class="sxs-lookup"><span data-stu-id="3d56e-114">If you want *all* constructed types to be unmanaged types, use the `unmanaged` constraint in the definition of a generic struct:</span></span>

[!code-csharp[unmanaged constraint in type definition](snippets/UnmanagedTypes.cs#AlwaysUnmanaged)]

## <a name="c-language-specification"></a><span data-ttu-id="3d56e-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="3d56e-115">C# language specification</span></span>

<span data-ttu-id="3d56e-116">Дополнительные сведения см. в разделе [Типы указателей](~/_csharplang/spec/unsafe-code.md#pointer-types) в статье [Спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="3d56e-116">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3d56e-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3d56e-117">See also</span></span>

- [<span data-ttu-id="3d56e-118">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="3d56e-118">C# reference</span></span>](../index.md)
- [<span data-ttu-id="3d56e-119">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="3d56e-119">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="3d56e-120">Типы, связанные с памятью и диапазонами</span><span class="sxs-lookup"><span data-stu-id="3d56e-120">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="3d56e-121">Оператор sizeof</span><span class="sxs-lookup"><span data-stu-id="3d56e-121">sizeof operator</span></span>](../operators/sizeof.md)
- [<span data-ttu-id="3d56e-122">Оператор stackalloc</span><span class="sxs-lookup"><span data-stu-id="3d56e-122">stackalloc operator</span></span>](../operators/stackalloc.md)
