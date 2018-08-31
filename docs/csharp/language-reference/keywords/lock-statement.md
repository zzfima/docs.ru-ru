---
title: Оператор lock (справочник по C#)
description: 'Ключевое слово lock используется при работе с потоками '
ms.date: 07/20/2015
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 6ed46837482642dfd7e1a96cd120fc18023c5e9f
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42931197"
---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="0206a-103">Оператор lock (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0206a-103">lock statement (C# Reference)</span></span>

<span data-ttu-id="0206a-104">При помощи ключевого слова `lock` блок выражений можно пометить как важный фрагмент. Получив блокировку взаимного исключения для указанного объекта, выражения выполняются, а затем снимается блокировка.</span><span class="sxs-lookup"><span data-stu-id="0206a-104">The `lock` keyword marks a statement block as a critical section by obtaining the mutual-exclusion lock for a given object, executing a statement, and then releasing the lock.</span></span> <span data-ttu-id="0206a-105">Следующий пример включает оператор `lock`.</span><span class="sxs-lookup"><span data-stu-id="0206a-105">The following example includes a `lock` statement.</span></span>

```csharp
class Account
{
    decimal balance;
    private Object thisLock = new Object();

    public void Withdraw(decimal amount)
    {
        lock (thisLock)
        {
            if (amount > balance)
            {
                throw new Exception("Insufficient funds");
            }
            balance -= amount;
        }
    }
}
```

<span data-ttu-id="0206a-106">Дополнительные сведения см. в разделе [Синхронизация потоков](../../programming-guide/concepts/threading/thread-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="0206a-106">For more information, see [Thread Synchronization](../../programming-guide/concepts/threading/thread-synchronization.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="0206a-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="0206a-107">Remarks</span></span>

<span data-ttu-id="0206a-108">Ключевое слово `lock` не позволит одному потоку войти в важный раздел кода в тот момент, когда в нем находится другой поток.</span><span class="sxs-lookup"><span data-stu-id="0206a-108">The `lock` keyword ensures that one thread does not enter a critical section of code while another thread is in the critical section.</span></span> <span data-ttu-id="0206a-109">При попытке входа другого потока в заблокированный код потребуется дождаться снятия блокировки объекта.</span><span class="sxs-lookup"><span data-stu-id="0206a-109">If another thread tries to enter a locked code, it will wait, block, until the object is released.</span></span>

<span data-ttu-id="0206a-110">Работа с потоками описана в разделе [Работа с потоками](../../programming-guide/concepts/threading/index.md).</span><span class="sxs-lookup"><span data-stu-id="0206a-110">The section [Threading](../../programming-guide/concepts/threading/index.md) discusses threading.</span></span>

<span data-ttu-id="0206a-111">Ключевое слово `lock` вызывает <xref:System.Threading.Monitor.Enter%2A> в начале блока и <xref:System.Threading.Monitor.Exit%2A> в конце блока.</span><span class="sxs-lookup"><span data-stu-id="0206a-111">The `lock` keyword calls <xref:System.Threading.Monitor.Enter%2A> at the start of the block and <xref:System.Threading.Monitor.Exit%2A> at the end of the block.</span></span> <span data-ttu-id="0206a-112">Если <xref:System.Threading.Thread.Interrupt%2A> прерывает работу потока, который ожидает ввода оператора `lock`, возникает <xref:System.Threading.ThreadInterruptedException>.</span><span class="sxs-lookup"><span data-stu-id="0206a-112">A <xref:System.Threading.ThreadInterruptedException> is thrown if <xref:System.Threading.Thread.Interrupt%2A> interrupts a thread that is waiting to enter a `lock` statement.</span></span>

<span data-ttu-id="0206a-113">Как правило, рекомендуется избегать блокировки типа `public` или экземпляров, которыми код не управляет.</span><span class="sxs-lookup"><span data-stu-id="0206a-113">In general, avoid locking on a `public` type, or instances beyond your code's control.</span></span> <span data-ttu-id="0206a-114">Это правило не соблюдается в распространенных конструкциях `lock (this)`, `lock (typeof (MyType))` и `lock ("myLock")`.</span><span class="sxs-lookup"><span data-stu-id="0206a-114">The common constructs `lock (this)`, `lock (typeof (MyType))`, and `lock ("myLock")` violate this guideline:</span></span>

- <span data-ttu-id="0206a-115">`lock (this)` может привести к проблеме, если к экземпляру допускается открытый доступ.</span><span class="sxs-lookup"><span data-stu-id="0206a-115">`lock (this)` is a problem if the instance can be accessed publicly.</span></span>

- <span data-ttu-id="0206a-116">`lock (typeof (MyType))` может привести к проблеме, если к `MyType` допускается открытый доступ.</span><span class="sxs-lookup"><span data-stu-id="0206a-116">`lock (typeof (MyType))` is a problem if `MyType` is publicly accessible.</span></span>

- <span data-ttu-id="0206a-117">`lock("myLock")` может привести к проблеме, поскольку любой код в процессе, использующий ту же строку, будет совместно использовать ту же блокировку.</span><span class="sxs-lookup"><span data-stu-id="0206a-117">`lock("myLock")` is a problem because any other code in the process using the same string, will share the same lock.</span></span>

<span data-ttu-id="0206a-118">Для блокировки рекомендуется использовать объект `private`. Если нужно защитить данные, являющиеся общими для всех экземпляров, рекомендуется использовать переменную объекта `private static`.</span><span class="sxs-lookup"><span data-stu-id="0206a-118">Best practice is to define a `private` object to lock on, or a `private static` object variable to protect data common to all instances.</span></span>

<span data-ttu-id="0206a-119">Нельзя использовать ключевое слово [await](await.md) в теле оператора `lock`.</span><span class="sxs-lookup"><span data-stu-id="0206a-119">You can't use the [await](await.md) keyword in the body of a `lock` statement.</span></span>

## <a name="example---threads-without-locking"></a><span data-ttu-id="0206a-120">Пример — потоки без блокировки</span><span class="sxs-lookup"><span data-stu-id="0206a-120">Example - Threads without locking</span></span>

<span data-ttu-id="0206a-121">В следующем примере показано простое использование потоков без блокировки в C#:</span><span class="sxs-lookup"><span data-stu-id="0206a-121">The following sample shows a simple use of threads without locking in C#:</span></span>

[!code-csharp[csrefKeywordsFixedLock#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsFixedLock/CS/csrefKeywordsFixedLock.cs#5)]

## <a name="example---threads-using-locking"></a><span data-ttu-id="0206a-122">Пример — потоки с блокировкой</span><span class="sxs-lookup"><span data-stu-id="0206a-122">Example - Threads using locking</span></span>

<span data-ttu-id="0206a-123">В следующем примере используются потоки и ключевое слово`lock`.</span><span class="sxs-lookup"><span data-stu-id="0206a-123">The following sample uses threads and `lock`.</span></span> <span data-ttu-id="0206a-124">Так как присутствует оператор `lock`, блокировка оператора является важным разделом и `balance` никогда не будет отрицательным числом:</span><span class="sxs-lookup"><span data-stu-id="0206a-124">As long as the `lock` statement is present, the statement block is a critical section and `balance` will never become a negative number:</span></span>

[!code-csharp[csrefKeywordsFixedLock#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsFixedLock/CS/csrefKeywordsFixedLock.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="0206a-125">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0206a-125">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="0206a-126">См. также</span><span class="sxs-lookup"><span data-stu-id="0206a-126">See also</span></span>

- <xref:System.Reflection.MethodImplAttributes>
- <xref:System.Threading.Mutex>
- <xref:System.Threading.Monitor>
- [<span data-ttu-id="0206a-127">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0206a-127">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="0206a-128">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0206a-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0206a-129">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="0206a-129">Threading</span></span>](../../programming-guide/concepts/threading/index.md)
- [<span data-ttu-id="0206a-130">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="0206a-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="0206a-131">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="0206a-131">Statement Keywords</span></span>](statement-keywords.md)
- [<span data-ttu-id="0206a-132">Блокируемые операции</span><span class="sxs-lookup"><span data-stu-id="0206a-132">Interlocked Operations</span></span>](../../../standard/threading/interlocked-operations.md)
- [<span data-ttu-id="0206a-133">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="0206a-133">AutoResetEvent</span></span>](../../../standard/threading/autoresetevent.md)
- [<span data-ttu-id="0206a-134">Синхронизация потоков</span><span class="sxs-lookup"><span data-stu-id="0206a-134">Thread Synchronization</span></span>](../../programming-guide/concepts/threading/thread-synchronization.md)