---
title: Оператор lock (справочник по C#)
description: Использование выражения блокировки C# для синхронизации доступа потоков к общему ресурсу
ms.date: 08/28/2018
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 2b6fbfb2f81d7745c4effb9ea0087f34cc872a6c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858360"
---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="a42e8-103">Оператор lock (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a42e8-103">lock statement (C# Reference)</span></span>

<span data-ttu-id="a42e8-104">Оператор `lock` создает взаимоисключающую блокировку заданного объекта перед выполнением определенных операторов, а затем снимает блокировку.</span><span class="sxs-lookup"><span data-stu-id="a42e8-104">The `lock` statement obtains the mutual-exclusion lock for a given object, executes a statement block, and then releases the lock.</span></span> <span data-ttu-id="a42e8-105">Во время блокировки поток, удерживающий блокировку, может снова получить и снять блокировку.</span><span class="sxs-lookup"><span data-stu-id="a42e8-105">While a lock is held, the thread that holds the lock can again obtain and release the lock.</span></span> <span data-ttu-id="a42e8-106">Любой другой поток не может получить блокировку и ожидает ее снятия.</span><span class="sxs-lookup"><span data-stu-id="a42e8-106">Any other thread is blocked from obtaining the lock and waits until the lock is released.</span></span>

<span data-ttu-id="a42e8-107">Оператор `lock` имеет форму</span><span class="sxs-lookup"><span data-stu-id="a42e8-107">The `lock` statement is of the form</span></span>

```csharp
lock (x)
{
    // Your code...
}
```

<span data-ttu-id="a42e8-108">Здесь `x` — это выражение [ссылочного типа](reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="a42e8-108">where `x` is an expression of a [reference type](reference-types.md).</span></span> <span data-ttu-id="a42e8-109">Оно является точным эквивалентом</span><span class="sxs-lookup"><span data-stu-id="a42e8-109">It's precisely equivalent to</span></span>

```csharp
object __lockObj = x;
bool __lockWasTaken = false;
try
{
    System.Threading.Monitor.Enter(__lockObj, ref __lockWasTaken);
    // Your code...
}
finally
{
    if (__lockWasTaken) System.Threading.Monitor.Exit(__lockObj);
}
```

<span data-ttu-id="a42e8-110">Так как в коде используется блок [try... finally](try-finally.md), блокировка освобождается, даже если возникает исключение в теле оператора `lock`.</span><span class="sxs-lookup"><span data-stu-id="a42e8-110">Since the code uses a [try...finally](try-finally.md) block, the lock is released even if an exception is thrown within the body of a `lock` statement.</span></span>

<span data-ttu-id="a42e8-111">Нельзя использовать ключевое слово [await](await.md) в теле оператора `lock`.</span><span class="sxs-lookup"><span data-stu-id="a42e8-111">You can't use the [await](await.md) keyword in the body of a `lock` statement.</span></span>

## <a name="remarks"></a><span data-ttu-id="a42e8-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="a42e8-112">Remarks</span></span>

<span data-ttu-id="a42e8-113">При синхронизации доступа потоков к общему ресурсу блокируйте выделенный экземпляр объекта (например, `private readonly object balanceLock = new object();`) или другой экземпляр, который, скорее всего, не будет использоваться как объект блокировки другими частями кода.</span><span class="sxs-lookup"><span data-stu-id="a42e8-113">When you synchronize thread access to shared resource, lock on a dedicated object instance (for example, `private readonly object balanceLock = new object();`) or another instance that is unlikely to be used as a lock object by unrelated parts of the code.</span></span> <span data-ttu-id="a42e8-114">Не используйте один и тот же экземпляр объекта блокировки для разных общих ресурсов: это может привести к взаимоблокировке или состязанию при блокировке.</span><span class="sxs-lookup"><span data-stu-id="a42e8-114">Avoid using the same lock object instance for different shared resources, as it might result in deadlock or lock contention.</span></span> <span data-ttu-id="a42e8-115">В частности, старайтесь не использовать:</span><span class="sxs-lookup"><span data-stu-id="a42e8-115">In particular, avoid using</span></span>

- <span data-ttu-id="a42e8-116">`this` (может использоваться вызывающими объектами как блокировка);</span><span class="sxs-lookup"><span data-stu-id="a42e8-116">`this` (might be used by the callers as a lock),</span></span>
- <span data-ttu-id="a42e8-117">экземпляры <xref:System.Type> (может получатся оператором [typeof](typeof.md) или отражением);</span><span class="sxs-lookup"><span data-stu-id="a42e8-117"><xref:System.Type> instances (might be obtained by the [typeof](typeof.md) operator or reflection),</span></span>
- <span data-ttu-id="a42e8-118">строковые экземпляры, включая строковые литералы,</span><span class="sxs-lookup"><span data-stu-id="a42e8-118">string instances, including string literals,</span></span>

<span data-ttu-id="a42e8-119">как объекты блокировки.</span><span class="sxs-lookup"><span data-stu-id="a42e8-119">as lock objects.</span></span>

## <a name="example"></a><span data-ttu-id="a42e8-120">Пример</span><span class="sxs-lookup"><span data-stu-id="a42e8-120">Example</span></span>

<span data-ttu-id="a42e8-121">В следующем примере определяется класс `Account`, который синхронизирует доступ к закрытому полю `balance` путем блокировки выделенного экземпляра `balanceLock`.</span><span class="sxs-lookup"><span data-stu-id="a42e8-121">The following example defines an `Account` class that synchronizes access to its private `balance` field by locking on a dedicated `balanceLock` instance.</span></span> <span data-ttu-id="a42e8-122">Использование того же экземпляра для блокировки гарантирует, что поле `balance` не смогут одновременно обновить два потока, пытающиеся вызвать методы `Debit` или `Credit` одновременно.</span><span class="sxs-lookup"><span data-stu-id="a42e8-122">Using the same instance for locking ensures that the `balance` field cannot be updated simultaneously by two threads attempting to call the `Debit` or `Credit` methods simultaneously.</span></span>

[!code-csharp[lock-statement-example](~/samples/snippets/csharp/keywords/LockStatementExample.cs)]

## <a name="c-language-specification"></a><span data-ttu-id="a42e8-123">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a42e8-123">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a42e8-124">См. также</span><span class="sxs-lookup"><span data-stu-id="a42e8-124">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.SpinLock?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [<span data-ttu-id="a42e8-125">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a42e8-125">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a42e8-126">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="a42e8-126">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a42e8-127">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="a42e8-127">Statement Keywords</span></span>](statement-keywords.md)
- [<span data-ttu-id="a42e8-128">Блокируемые операции</span><span class="sxs-lookup"><span data-stu-id="a42e8-128">Interlocked operations</span></span>](../../../standard/threading/interlocked-operations.md)
- [<span data-ttu-id="a42e8-129">Обзор примитивов синхронизации</span><span class="sxs-lookup"><span data-stu-id="a42e8-129">Overview of synchronization primitives</span></span>](../../../standard/threading/overview-of-synchronization-primitives.md)