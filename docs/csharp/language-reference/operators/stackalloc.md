---
title: выражение stackalloc справочнике по C#
ms.date: 03/13/2020
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc expression [C#]
ms.openlocfilehash: 2e99ce8b1e44dfa040c1acac799a3a55b375bd91
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546605"
---
# <a name="stackalloc-expression-c-reference"></a><span data-ttu-id="35922-102">выражение stackalloc (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="35922-102">stackalloc expression (C# reference)</span></span>

<span data-ttu-id="35922-103">Выражение `stackalloc` выделяет блок памяти в стеке.</span><span class="sxs-lookup"><span data-stu-id="35922-103">A `stackalloc` expression allocates a block of memory on the stack.</span></span> <span data-ttu-id="35922-104">Выделенный в стеке блок памяти, который создает этот метод, автоматически удаляется по завершении выполнения метода.</span><span class="sxs-lookup"><span data-stu-id="35922-104">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="35922-105">Вы не можете явным образом освободить память, выделенную `stackalloc`.</span><span class="sxs-lookup"><span data-stu-id="35922-105">You cannot explicitly free the memory allocated with `stackalloc`.</span></span> <span data-ttu-id="35922-106">Выделенный в стеке блок памяти не подвергается [сборке мусора](../../../standard/garbage-collection/index.md), поэтому его не нужно закреплять с помощью [инструкции `fixed`](../keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="35922-106">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with a [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="35922-107">Результат выполнения выражения `stackalloc` можно присвоить переменной любого из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="35922-107">You can assign the result of a `stackalloc` expression to a variable of one of the following types:</span></span>

- <span data-ttu-id="35922-108">Начиная с версии C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> или <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="35922-108">Beginning with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](snippets/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="35922-109">Нет необходимости использовать [небезопасный](../keywords/unsafe.md) контекст при назначении выделенного в стеке блока памяти переменной <xref:System.Span%601> или <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="35922-109">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="35922-110">При работе с такими типами вы можете использовать выражение `stackalloc` в [условном](conditional-operator.md) выражении или выражении присваивания, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="35922-110">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](snippets/StackallocOperator.cs#AsExpression)]

  <span data-ttu-id="35922-111">Начиная с версии C# 8.0, можно использовать выражение `stackalloc` внутри других выражений, если разрешена переменная <xref:System.Span%601> или <xref:System.ReadOnlySpan%601>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="35922-111">Beginning with C# 8.0, you can use a `stackalloc` expression inside other expressions whenever a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable is allowed, as the following example shows:</span></span>

  [!code-csharp[stackalloc in nested expressions](snippets/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > <span data-ttu-id="35922-112">Мы рекомендуем везде, где это возможно, использовать для работы с выделенной в стеке памятью типы <xref:System.Span%601> или <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="35922-112">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="35922-113">[Тип указателя](../../programming-guide/unsafe-code-pointers/pointer-types.md), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="35922-113">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](snippets/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="35922-114">Как демонстрирует пример выше, при работе с типами указателей необходимо использовать контекст `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="35922-114">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

  <span data-ttu-id="35922-115">В случае типов указателей можно использовать выражение `stackalloc` только в объявлении локальной переменной для инициализации переменной.</span><span class="sxs-lookup"><span data-stu-id="35922-115">In the case of pointer types, you can use a `stackalloc` expression only in a local variable declaration to initialize the variable.</span></span>

<span data-ttu-id="35922-116">Объем доступной памяти в стеке ограничен.</span><span class="sxs-lookup"><span data-stu-id="35922-116">The amount of memory available on the stack is limited.</span></span> <span data-ttu-id="35922-117">При выделении слишком большого объема памяти в стеке возникает исключение <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="35922-117">If you allocate too much memory on the stack, a <xref:System.StackOverflowException> is thrown.</span></span> <span data-ttu-id="35922-118">Чтобы избежать этого, следуйте приведенным ниже правилам.</span><span class="sxs-lookup"><span data-stu-id="35922-118">To avoid that, follow the rules below:</span></span>

- <span data-ttu-id="35922-119">Ограничьте объем памяти, выделенный `stackalloc`:</span><span class="sxs-lookup"><span data-stu-id="35922-119">Limit the amount of memory you allocate with `stackalloc`:</span></span>

  [!code-csharp[limit stackalloc](snippets/StackallocOperator.cs#LimitStackalloc)]

  <span data-ttu-id="35922-120">Поскольку объем доступной памяти на стеке зависит от среды, в которой выполняется код, при определении фактического предельного значения следует использовать консервативное значение.</span><span class="sxs-lookup"><span data-stu-id="35922-120">Because the amount of memory available on the stack depends on the environment in which the code is executed, be conservative when you define the actual limit value.</span></span>

- <span data-ttu-id="35922-121">Старайтесь не использовать `stackalloc` в циклах.</span><span class="sxs-lookup"><span data-stu-id="35922-121">Avoid using `stackalloc` inside loops.</span></span> <span data-ttu-id="35922-122">Выделяйте блок памяти за пределами цикла и используйте его повторно внутри цикла.</span><span class="sxs-lookup"><span data-stu-id="35922-122">Allocate the memory block outside a loop and reuse it inside the loop.</span></span>

<span data-ttu-id="35922-123">Содержимое только что выделенной памяти не определено.</span><span class="sxs-lookup"><span data-stu-id="35922-123">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="35922-124">Его следует инициализировать перед использованием.</span><span class="sxs-lookup"><span data-stu-id="35922-124">You should initialize it before the use.</span></span> <span data-ttu-id="35922-125">Например, вы можете использовать метод <xref:System.Span%601.Clear%2A?displayProperty=nameWithType>, который задает для всех элементов значение по умолчанию типа `T`.</span><span class="sxs-lookup"><span data-stu-id="35922-125">For example, you can use the <xref:System.Span%601.Clear%2A?displayProperty=nameWithType> method that sets all the items to the default value of type `T`.</span></span>

<span data-ttu-id="35922-126">Начиная с версии C# 7.3, вы можете использовать синтаксис инициализатора массива, чтобы определить содержимое для только что выделенной памяти.</span><span class="sxs-lookup"><span data-stu-id="35922-126">Beginning with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="35922-127">В следующем примере показано несколько способов сделать это:</span><span class="sxs-lookup"><span data-stu-id="35922-127">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](snippets/StackallocOperator.cs#StackallocInit)]

<span data-ttu-id="35922-128">В выражении `stackalloc T[E]` `T` должен иметь [неуправляемый тип](../builtin-types/unmanaged-types.md), а `E` — неотрицательное значение [int](../builtin-types/integral-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="35922-128">In expression `stackalloc T[E]`, `T` must be an [unmanaged type](../builtin-types/unmanaged-types.md) and `E` must evaluate to a non-negative [int](../builtin-types/integral-numeric-types.md) value.</span></span>

## <a name="security"></a><span data-ttu-id="35922-129">Безопасность</span><span class="sxs-lookup"><span data-stu-id="35922-129">Security</span></span>

<span data-ttu-id="35922-130">При использовании `stackalloc` в среде CLR автоматически включается контроль переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="35922-130">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="35922-131">Если буфер переполнен, процесс незамедлительно прерывается — это позволяет минимизировать риск исполнения вредоносного кода.</span><span class="sxs-lookup"><span data-stu-id="35922-131">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="35922-132">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="35922-132">C# language specification</span></span>

<span data-ttu-id="35922-133">См. сведения о [выделении памяти в стеке](~/_csharplang/spec/unsafe-code.md#stack-allocation) в [спецификации языка C#](~/_csharplang/spec/introduction.md) и [разрешении `stackalloc` во вложенных контекстах](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md) в примечании.</span><span class="sxs-lookup"><span data-stu-id="35922-133">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the [Permit `stackalloc` in nested contexts](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md) feature proposal note.</span></span>

## <a name="see-also"></a><span data-ttu-id="35922-134">См. также</span><span class="sxs-lookup"><span data-stu-id="35922-134">See also</span></span>

- [<span data-ttu-id="35922-135">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="35922-135">C# reference</span></span>](../index.md)
- [<span data-ttu-id="35922-136">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="35922-136">C# operators</span></span>](index.md)
- [<span data-ttu-id="35922-137">Операторы, связанные с указателем</span><span class="sxs-lookup"><span data-stu-id="35922-137">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="35922-138">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="35922-138">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="35922-139">Типы, связанные с памятью и диапазонами</span><span class="sxs-lookup"><span data-stu-id="35922-139">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="35922-140">Правила stackalloc</span><span class="sxs-lookup"><span data-stu-id="35922-140">Dos and Don'ts of stackalloc</span></span>](https://vcsjones.dev/2020/02/24/stackalloc/)
