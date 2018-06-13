---
title: Оператор lock (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 2ce870e8caa67d780ce603a6f1dbcc7cd303b842
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274223"
---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="98261-102">Оператор lock (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="98261-102">lock Statement (C# Reference)</span></span>
<span data-ttu-id="98261-103">При помощи ключевого слова `lock` блок выражений можно пометить как важный фрагмент. Получив блокировку взаимного исключения для указанного объекта, выражения выполняются, а затем снимается блокировка.</span><span class="sxs-lookup"><span data-stu-id="98261-103">The `lock` keyword marks a statement block as a critical section by obtaining the mutual-exclusion lock for a given object, executing a statement, and then releasing the lock.</span></span> <span data-ttu-id="98261-104">Следующий пример включает оператор `lock`.</span><span class="sxs-lookup"><span data-stu-id="98261-104">The following example includes a `lock` statement.</span></span>  
  
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
  
 <span data-ttu-id="98261-105">Дополнительные сведения см. в разделе [Синхронизация потоков](../../programming-guide/concepts/threading/thread-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="98261-105">For more information, see [Thread Synchronization](../../programming-guide/concepts/threading/thread-synchronization.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98261-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="98261-106">Remarks</span></span>  
 <span data-ttu-id="98261-107">Ключевое слово `lock` не позволит одному потоку войти в важный раздел кода в тот момент, когда в нем находится другой поток.</span><span class="sxs-lookup"><span data-stu-id="98261-107">The `lock` keyword ensures that one thread does not enter a critical section of code while another thread is in the critical section.</span></span> <span data-ttu-id="98261-108">При попытке входа другого потока в заблокированный код потребуется дождаться снятия блокировки объекта.</span><span class="sxs-lookup"><span data-stu-id="98261-108">If another thread tries to enter a locked code, it will wait, block, until the object is released.</span></span>  
  
 <span data-ttu-id="98261-109">Работа с потоками описана в разделе [Работа с потоками](../../programming-guide/concepts/threading/index.md).</span><span class="sxs-lookup"><span data-stu-id="98261-109">The section [Threading](../../programming-guide/concepts/threading/index.md) discusses threading.</span></span>  
  
 <span data-ttu-id="98261-110">Ключевое слово `lock` вызывает <xref:System.Threading.Monitor.Enter%2A> в начале блока и <xref:System.Threading.Monitor.Exit%2A> в конце блока.</span><span class="sxs-lookup"><span data-stu-id="98261-110">The `lock` keyword calls <xref:System.Threading.Monitor.Enter%2A> at the start of the block and <xref:System.Threading.Monitor.Exit%2A> at the end of the block.</span></span> <span data-ttu-id="98261-111">Если <xref:System.Threading.Thread.Interrupt%2A> прерывает работу потока, который ожидает ввода оператора `lock`, возникает <xref:System.Threading.ThreadInterruptedException>.</span><span class="sxs-lookup"><span data-stu-id="98261-111">A <xref:System.Threading.ThreadInterruptedException> is thrown if <xref:System.Threading.Thread.Interrupt%2A> interrupts a thread that is waiting to enter a `lock` statement.</span></span>  
  
 <span data-ttu-id="98261-112">Как правило, рекомендуется избегать блокировки типа `public` или экземпляров, которыми код не управляет.</span><span class="sxs-lookup"><span data-stu-id="98261-112">In general, avoid locking on a `public` type, or instances beyond your code's control.</span></span> <span data-ttu-id="98261-113">Это правило не соблюдается в распространенных конструкциях `lock (this)`, `lock (typeof (MyType))` и `lock ("myLock")`.</span><span class="sxs-lookup"><span data-stu-id="98261-113">The common constructs `lock (this)`, `lock (typeof (MyType))`, and `lock ("myLock")` violate this guideline:</span></span>  
  
-   <span data-ttu-id="98261-114">`lock (this)` может привести к проблеме, если к экземпляру допускается открытый доступ.</span><span class="sxs-lookup"><span data-stu-id="98261-114">`lock (this)` is a problem if the instance can be accessed publicly.</span></span>  
  
-   <span data-ttu-id="98261-115">`lock (typeof (MyType))` может привести к проблеме, если к `MyType` допускается открытый доступ.</span><span class="sxs-lookup"><span data-stu-id="98261-115">`lock (typeof (MyType))` is a problem if `MyType` is publicly accessible.</span></span>  
  
-   <span data-ttu-id="98261-116">`lock("myLock")` может привести к проблеме, поскольку любой код в процессе, использующий ту же строку, будет совместно использовать ту же блокировку.</span><span class="sxs-lookup"><span data-stu-id="98261-116">`lock("myLock")` is a problem because any other code in the process using the same string, will share the same lock.</span></span>  
  
 <span data-ttu-id="98261-117">Для блокировки рекомендуется использовать объект `private`. Если нужно защитить данные, являющиеся общими для всех экземпляров, рекомендуется использовать переменную объекта `private static`.</span><span class="sxs-lookup"><span data-stu-id="98261-117">Best practice is to define a `private` object to lock on, or a `private static` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="98261-118">Нельзя использовать ключевое слово [await](../../../csharp/language-reference/keywords/await.md) в теле оператора `lock`.</span><span class="sxs-lookup"><span data-stu-id="98261-118">You can't use the [await](../../../csharp/language-reference/keywords/await.md) keyword in the body of a `lock` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98261-119">Пример</span><span class="sxs-lookup"><span data-stu-id="98261-119">Example</span></span>  
 <span data-ttu-id="98261-120">В следующем примере показано простое использование потоков без блокировки в C#.</span><span class="sxs-lookup"><span data-stu-id="98261-120">The following sample shows a simple use of threads without locking in C#.</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="98261-121">Пример</span><span class="sxs-lookup"><span data-stu-id="98261-121">Example</span></span>  
 <span data-ttu-id="98261-122">В следующем примере используются потоки и ключевое слово`lock`.</span><span class="sxs-lookup"><span data-stu-id="98261-122">The following sample uses threads and `lock`.</span></span> <span data-ttu-id="98261-123">Так как присутствует оператор `lock`, блокировка оператора является важным разделом и `balance` никогда не будет отрицательным числом.</span><span class="sxs-lookup"><span data-stu-id="98261-123">As long as the `lock` statement is present, the statement block is a critical section and `balance` will never become a negative number.</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="98261-124">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="98261-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="98261-125">См. также</span><span class="sxs-lookup"><span data-stu-id="98261-125">See Also</span></span>  
 <xref:System.Reflection.MethodImplAttributes>  
 <xref:System.Threading.Mutex>  
 [<span data-ttu-id="98261-126">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="98261-126">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="98261-127">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="98261-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="98261-128">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="98261-128">Threading</span></span>](../../programming-guide/concepts/threading/index.md)  
 [<span data-ttu-id="98261-129">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="98261-129">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="98261-130">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="98261-130">Statement Keywords</span></span>](../../../csharp/language-reference/keywords/statement-keywords.md)  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="98261-131">Блокируемые операции</span><span class="sxs-lookup"><span data-stu-id="98261-131">Interlocked Operations</span></span>](../../../standard/threading/interlocked-operations.md)  
 [<span data-ttu-id="98261-132">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="98261-132">AutoResetEvent</span></span>](../../../standard/threading/autoresetevent.md)  
 [<span data-ttu-id="98261-133">Синхронизация потоков</span><span class="sxs-lookup"><span data-stu-id="98261-133">Thread Synchronization</span></span>](../../programming-guide/concepts/threading/thread-synchronization.md)
