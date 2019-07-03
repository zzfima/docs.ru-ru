---
title: Справочник по C#. Оператор stackalloc
ms.custom: seodec18
ms.date: 06/10/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: 3be4e827e75e4e26a34d9ed70423af5aa317e7fb
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025000"
---
# <a name="stackalloc-operator-c-reference"></a><span data-ttu-id="bbbc1-102">Оператор stackalloc (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="bbbc1-102">stackalloc operator (C# reference)</span></span>

<span data-ttu-id="bbbc1-103">Оператор `stackalloc` выделяет блок памяти в стеке.</span><span class="sxs-lookup"><span data-stu-id="bbbc1-103">The `stackalloc` operator allocates a block of memory on the stack.</span></span> <span data-ttu-id="bbbc1-104">Выделенный в стеке блок памяти, который создает этот метод, автоматически удаляется по завершении выполнения метода.</span><span class="sxs-lookup"><span data-stu-id="bbbc1-104">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="bbbc1-105">Вы не можете явным образом освободить память, выделенную оператором `stackalloc`.</span><span class="sxs-lookup"><span data-stu-id="bbbc1-105">You cannot explicitly free memory allocated with the `stackalloc` operator.</span></span> <span data-ttu-id="bbbc1-106">Выделенный в стеке блок памяти не подвергается [сборке мусора](../../../standard/garbage-collection/index.md), а значит, ее не нужно закреплять с помощью [инструкции `fixed`](../keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="bbbc1-106">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with the [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="bbbc1-107">Результат выполнения оператора `stackalloc` вы можете присвоить переменной любого из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="bbbc1-107">You can assign the result of the `stackalloc` operator to a variable of one of the following types:</span></span>

- <span data-ttu-id="bbbc1-108">Начиная с C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> или <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bbbc1-108">Starting with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="bbbc1-109">Нет необходимости использовать [небезопасный](../keywords/unsafe.md) контекст при назначении выделенного в стеке блока памяти переменной <xref:System.Span%601> или <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="bbbc1-109">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="bbbc1-110">При работе с такими типами вы можете использовать выражение `stackalloc` в [условном](conditional-operator.md) выражении или выражении присваивания, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bbbc1-110">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AsExpression)]

  > [!NOTE]
  > <span data-ttu-id="bbbc1-111">Мы рекомендуем везде, где это возможно, использовать для работы с выделенной в стеке памятью типы <xref:System.Span%601> или <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="bbbc1-111">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="bbbc1-112">[Тип указателя](../../programming-guide/unsafe-code-pointers/pointer-types.md), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="bbbc1-112">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="bbbc1-113">Как демонстрирует пример выше, при работе с типами указателей необходимо использовать контекст `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="bbbc1-113">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

<span data-ttu-id="bbbc1-114">Содержимое только что выделенной памяти не определено.</span><span class="sxs-lookup"><span data-stu-id="bbbc1-114">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="bbbc1-115">Начиная с C# 7.3, вы можете использовать синтаксис инициализатора массива, чтобы определить содержимое для только что выделенной памяти.</span><span class="sxs-lookup"><span data-stu-id="bbbc1-115">Starting with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="bbbc1-116">В следующем примере показано несколько способов сделать это:</span><span class="sxs-lookup"><span data-stu-id="bbbc1-116">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](~/samples/csharp/language-reference/operators/StackallocOperator.cs#StackallocInit)]

## <a name="security"></a><span data-ttu-id="bbbc1-117">Безопасность</span><span class="sxs-lookup"><span data-stu-id="bbbc1-117">Security</span></span>

<span data-ttu-id="bbbc1-118">При использовании `stackalloc` в среде CLR автоматически включается контроль переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="bbbc1-118">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="bbbc1-119">Если буфер переполнен, процесс незамедлительно прерывается — это позволяет минимизировать риск исполнения вредоносного кода.</span><span class="sxs-lookup"><span data-stu-id="bbbc1-119">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bbbc1-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="bbbc1-120">C# language specification</span></span>

<span data-ttu-id="bbbc1-121">Дополнительные сведения см. в разделе [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) (Выделение памяти в стеке) из [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="bbbc1-121">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bbbc1-122">См. также</span><span class="sxs-lookup"><span data-stu-id="bbbc1-122">See also</span></span>

- [<span data-ttu-id="bbbc1-123">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="bbbc1-123">C# reference</span></span>](../index.md)
- [<span data-ttu-id="bbbc1-124">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="bbbc1-124">C# operators</span></span>](index.md)
- [<span data-ttu-id="bbbc1-125">Операторы, связанные с указателем</span><span class="sxs-lookup"><span data-stu-id="bbbc1-125">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="bbbc1-126">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="bbbc1-126">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="bbbc1-127">Типы, связанные с памятью и диапазонами</span><span class="sxs-lookup"><span data-stu-id="bbbc1-127">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
