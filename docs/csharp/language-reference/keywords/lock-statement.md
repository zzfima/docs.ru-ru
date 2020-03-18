---
title: Инструкция lock. Справочник по C#
description: Синхронизация доступа потоков к общему ресурсу с помощью оператора блокировки C#
ms.date: 10/01/2018
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 467881dd36c97b6b18b7f31d4e4af25152b0d012
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713390"
---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="20905-103">Инструкция lock. (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="20905-103">lock statement (C# reference)</span></span>

<span data-ttu-id="20905-104">Оператор `lock` получает взаимоисключающую блокировку заданного объекта перед выполнением определенных операторов, а затем снимает блокировку.</span><span class="sxs-lookup"><span data-stu-id="20905-104">The `lock` statement acquires the mutual-exclusion lock for a given object, executes a statement block, and then releases the lock.</span></span> <span data-ttu-id="20905-105">Во время блокировки поток, удерживающий блокировку, может снова поставить и снять блокировку.</span><span class="sxs-lookup"><span data-stu-id="20905-105">While a lock is held, the thread that holds the lock can again acquire and release the lock.</span></span> <span data-ttu-id="20905-106">Любой другой поток не может получить блокировку и ожидает ее снятия.</span><span class="sxs-lookup"><span data-stu-id="20905-106">Any other thread is blocked from acquiring the lock and waits until the lock is released.</span></span>

<span data-ttu-id="20905-107">Оператор `lock` имеет форму</span><span class="sxs-lookup"><span data-stu-id="20905-107">The `lock` statement is of the form</span></span>

```csharp
lock (x)
{
    // Your code...
}
```

<span data-ttu-id="20905-108">Здесь `x` — это выражение [ссылочного типа](reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="20905-108">where `x` is an expression of a [reference type](reference-types.md).</span></span> <span data-ttu-id="20905-109">Оно является точным эквивалентом</span><span class="sxs-lookup"><span data-stu-id="20905-109">It's precisely equivalent to</span></span>

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

<span data-ttu-id="20905-110">Так как в коде используется блок [try... finally](try-finally.md), блокировка освобождается, даже если возникает исключение в теле оператора `lock`.</span><span class="sxs-lookup"><span data-stu-id="20905-110">Since the code uses a [try...finally](try-finally.md) block, the lock is released even if an exception is thrown within the body of a `lock` statement.</span></span>

<span data-ttu-id="20905-111">Нельзя использовать [оператор await](../operators/await.md) в теле оператора `lock`.</span><span class="sxs-lookup"><span data-stu-id="20905-111">You can't use the [await operator](../operators/await.md) in the body of a `lock` statement.</span></span>

## <a name="remarks"></a><span data-ttu-id="20905-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="20905-112">Remarks</span></span>

<span data-ttu-id="20905-113">При синхронизации доступа потоков к общему ресурсу блокируйте выделенный экземпляр объекта (например, `private readonly object balanceLock = new object();`) или другой экземпляр, который, скорее всего, не будет использоваться как объект блокировки другими частями кода.</span><span class="sxs-lookup"><span data-stu-id="20905-113">When you synchronize thread access to a shared resource, lock on a dedicated object instance (for example, `private readonly object balanceLock = new object();`) or another instance that is unlikely to be used as a lock object by unrelated parts of the code.</span></span> <span data-ttu-id="20905-114">Не используйте один и тот же экземпляр объекта блокировки для разных общих ресурсов: это может привести к взаимоблокировке или состязанию при блокировке.</span><span class="sxs-lookup"><span data-stu-id="20905-114">Avoid using the same lock object instance for different shared resources, as it might result in deadlock or lock contention.</span></span> <span data-ttu-id="20905-115">В особенности избегайте использования следующих объектов в качестве объектов блокировки:</span><span class="sxs-lookup"><span data-stu-id="20905-115">In particular, avoid using the following as lock objects:</span></span>

- <span data-ttu-id="20905-116">`this`, так как он может использоваться вызывающими объектами как блокировка;</span><span class="sxs-lookup"><span data-stu-id="20905-116">`this`, as it might be used by the callers as a lock.</span></span>
- <span data-ttu-id="20905-117">экземпляров <xref:System.Type>, так как их может получать оператор [typeof](../operators/type-testing-and-cast.md#typeof-operator) или отражение;</span><span class="sxs-lookup"><span data-stu-id="20905-117"><xref:System.Type> instances, as those might be obtained by the [typeof](../operators/type-testing-and-cast.md#typeof-operator) operator or reflection.</span></span>
- <span data-ttu-id="20905-118">строковых экземпляров, включая строковые литералы, так как они могут быть [интернированы](/dotnet/api/system.string.intern#remarks).</span><span class="sxs-lookup"><span data-stu-id="20905-118">string instances, including string literals, as those might be [interned](/dotnet/api/system.string.intern#remarks).</span></span>

## <a name="example"></a><span data-ttu-id="20905-119">Пример</span><span class="sxs-lookup"><span data-stu-id="20905-119">Example</span></span>

<span data-ttu-id="20905-120">В следующем примере определяется класс `Account`, который синхронизирует доступ к закрытому полю `balance` путем блокировки выделенного экземпляра `balanceLock`.</span><span class="sxs-lookup"><span data-stu-id="20905-120">The following example defines an `Account` class that synchronizes access to its private `balance` field by locking on a dedicated `balanceLock` instance.</span></span> <span data-ttu-id="20905-121">Использование того же экземпляра для блокировки гарантирует, что поле `balance` не смогут одновременно обновить два потока, пытающиеся вызвать методы `Debit` или `Credit` одновременно.</span><span class="sxs-lookup"><span data-stu-id="20905-121">Using the same instance for locking ensures that the `balance` field cannot be updated simultaneously by two threads attempting to call the `Debit` or `Credit` methods simultaneously.</span></span>

[!code-csharp[lock-statement-example](~/samples/snippets/csharp/keywords/LockStatementExample.cs)]

## <a name="c-language-specification"></a><span data-ttu-id="20905-122">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="20905-122">C# language specification</span></span>

<span data-ttu-id="20905-123">Дополнительные сведения см. в разделе об [инструкции lock](~/_csharplang/spec/statements.md#the-lock-statement) в документации [Предварительная спецификация C# 6.0](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="20905-123">For more information, see [The lock statement](~/_csharplang/spec/statements.md#the-lock-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="20905-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="20905-124">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.SpinLock?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [<span data-ttu-id="20905-125">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="20905-125">C# reference</span></span>](../index.md)
- [<span data-ttu-id="20905-126">Ключевые слова C#</span><span class="sxs-lookup"><span data-stu-id="20905-126">C# keywords</span></span>](index.md)
- [<span data-ttu-id="20905-127">Обзор примитивов синхронизации</span><span class="sxs-lookup"><span data-stu-id="20905-127">Overview of synchronization primitives</span></span>](../../../standard/threading/overview-of-synchronization-primitives.md)
