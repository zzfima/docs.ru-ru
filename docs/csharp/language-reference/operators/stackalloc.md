---
title: Справочник по C#. Оператор stackalloc
ms.custom: seodec18
ms.date: 09/20/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: 82fc1649bac66c0e934db13c50390b977432c34c
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036145"
---
# <a name="stackalloc-operator-c-reference"></a><span data-ttu-id="35c10-102">Оператор stackalloc (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="35c10-102">stackalloc operator (C# reference)</span></span>

<span data-ttu-id="35c10-103">Оператор `stackalloc` выделяет блок памяти в стеке.</span><span class="sxs-lookup"><span data-stu-id="35c10-103">The `stackalloc` operator allocates a block of memory on the stack.</span></span> <span data-ttu-id="35c10-104">Выделенный в стеке блок памяти, который создает этот метод, автоматически удаляется по завершении выполнения метода.</span><span class="sxs-lookup"><span data-stu-id="35c10-104">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="35c10-105">Вы не можете явным образом освободить память, выделенную оператором `stackalloc`.</span><span class="sxs-lookup"><span data-stu-id="35c10-105">You cannot explicitly free memory allocated with the `stackalloc` operator.</span></span> <span data-ttu-id="35c10-106">Выделенный в стеке блок памяти не подвергается [сборке мусора](../../../standard/garbage-collection/index.md), поэтому его не нужно закреплять с помощью [инструкции `fixed`](../keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="35c10-106">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with a [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="35c10-107">В выражении `stackalloc T[E]` элемент `T` должен быть [неуправляемым типом](../builtin-types/unmanaged-types.md), а элемент `E` — выражением типа `int`.</span><span class="sxs-lookup"><span data-stu-id="35c10-107">In expression `stackalloc T[E]`, `T` must be an [unmanaged type](../builtin-types/unmanaged-types.md) and `E` must be an expression of type `int`.</span></span>

<span data-ttu-id="35c10-108">Результат выполнения оператора `stackalloc` вы можете присвоить переменной любого из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="35c10-108">You can assign the result of the `stackalloc` operator to a variable of one of the following types:</span></span>

- <span data-ttu-id="35c10-109">Начиная с версии C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> или <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="35c10-109">Beginning with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="35c10-110">Нет необходимости использовать [небезопасный](../keywords/unsafe.md) контекст при назначении выделенного в стеке блока памяти переменной <xref:System.Span%601> или <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="35c10-110">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="35c10-111">При работе с такими типами вы можете использовать выражение `stackalloc` в [условном](conditional-operator.md) выражении или выражении присваивания, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="35c10-111">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AsExpression)]

  <span data-ttu-id="35c10-112">Начиная с версии C# 8.0, можно использовать выражение `stackalloc` внутри других выражений, если разрешена переменная <xref:System.Span%601> или <xref:System.ReadOnlySpan%601>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="35c10-112">Beginning with C# 8.0, you can use a `stackalloc` expression inside other expressions whenever a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable is allowed, as the following example shows:</span></span>

  [!code-csharp[stackalloc in nested expressions](~/samples/csharp/language-reference/operators/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > <span data-ttu-id="35c10-113">Мы рекомендуем везде, где это возможно, использовать для работы с выделенной в стеке памятью типы <xref:System.Span%601> или <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="35c10-113">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="35c10-114">[Тип указателя](../../programming-guide/unsafe-code-pointers/pointer-types.md), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="35c10-114">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="35c10-115">Как демонстрирует пример выше, при работе с типами указателей необходимо использовать контекст `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="35c10-115">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

  <span data-ttu-id="35c10-116">В случае типов указателей можно использовать выражение `stackalloc` только в объявлении локальной переменной для инициализации переменной.</span><span class="sxs-lookup"><span data-stu-id="35c10-116">In the case of pointer types, you can use a `stackalloc` expression only in a local variable declaration to initialize the variable.</span></span>

<span data-ttu-id="35c10-117">Содержимое только что выделенной памяти не определено.</span><span class="sxs-lookup"><span data-stu-id="35c10-117">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="35c10-118">Начиная с версии C# 7.3, вы можете использовать синтаксис инициализатора массива, чтобы определить содержимое для только что выделенной памяти.</span><span class="sxs-lookup"><span data-stu-id="35c10-118">Beginning with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="35c10-119">В следующем примере показано несколько способов сделать это:</span><span class="sxs-lookup"><span data-stu-id="35c10-119">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](~/samples/csharp/language-reference/operators/StackallocOperator.cs#StackallocInit)]

## <a name="security"></a><span data-ttu-id="35c10-120">Безопасность</span><span class="sxs-lookup"><span data-stu-id="35c10-120">Security</span></span>

<span data-ttu-id="35c10-121">При использовании `stackalloc` в среде CLR автоматически включается контроль переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="35c10-121">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="35c10-122">Если буфер переполнен, процесс незамедлительно прерывается — это позволяет минимизировать риск исполнения вредоносного кода.</span><span class="sxs-lookup"><span data-stu-id="35c10-122">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="35c10-123">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="35c10-123">C# language specification</span></span>

<span data-ttu-id="35c10-124">Дополнительные сведения см. в разделе [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) (Выделение памяти в стеке) из [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="35c10-124">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="35c10-125">См. также</span><span class="sxs-lookup"><span data-stu-id="35c10-125">See also</span></span>

- [<span data-ttu-id="35c10-126">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="35c10-126">C# reference</span></span>](../index.md)
- [<span data-ttu-id="35c10-127">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="35c10-127">C# operators</span></span>](index.md)
- [<span data-ttu-id="35c10-128">Операторы, связанные с указателем</span><span class="sxs-lookup"><span data-stu-id="35c10-128">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="35c10-129">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="35c10-129">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="35c10-130">Типы, связанные с памятью и диапазонами</span><span class="sxs-lookup"><span data-stu-id="35c10-130">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
