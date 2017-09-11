---
title: "Оператор lock (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- lock_CSharpKeyword
- lock
dev_langs:
- CSharp
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 00dcbb9feec11587265bf61667d91c2c1598065b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="99263-102">Оператор lock (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="99263-102">lock Statement (C# Reference)</span></span>
<span data-ttu-id="99263-103">При помощи ключевого слова `lock` блок выражений можно пометить как важный фрагмент. Получив блокировку взаимного исключения для указанного объекта, выражения выполняются, а затем снимается блокировка.</span><span class="sxs-lookup"><span data-stu-id="99263-103">The `lock` keyword marks a statement block as a critical section by obtaining the mutual-exclusion lock for a given object, executing a statement, and then releasing the lock.</span></span> <span data-ttu-id="99263-104">Следующий пример включает оператор `lock`.</span><span class="sxs-lookup"><span data-stu-id="99263-104">The following example includes a `lock` statement.</span></span>  
  
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
  
 <span data-ttu-id="99263-105">Дополнительные сведения см. в разделе [Синхронизация потоков](http://msdn.microsoft.com/library/413e1f28-a2c5-4eec-8338-aa43e7982ff4).</span><span class="sxs-lookup"><span data-stu-id="99263-105">For more information, see [Thread Synchronization](http://msdn.microsoft.com/library/413e1f28-a2c5-4eec-8338-aa43e7982ff4).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99263-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="99263-106">Remarks</span></span>  
 <span data-ttu-id="99263-107">Ключевое слово `lock` не позволит одному потоку войти в важный раздел кода в тот момент, когда в нем находится другой поток.</span><span class="sxs-lookup"><span data-stu-id="99263-107">The `lock` keyword ensures that one thread does not enter a critical section of code while another thread is in the critical section.</span></span> <span data-ttu-id="99263-108">При попытке входа другого потока в заблокированный код потребуется дождаться снятия блокировки объекта.</span><span class="sxs-lookup"><span data-stu-id="99263-108">If another thread tries to enter a locked code, it will wait, block, until the object is released.</span></span>  
  
 <span data-ttu-id="99263-109">Работа с потоками описана в разделе [Работа с потоками](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span><span class="sxs-lookup"><span data-stu-id="99263-109">The section [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c) discusses threading.</span></span>  
  
 <span data-ttu-id="99263-110">Ключевое слово `lock` вызывает <xref:System.Threading.Monitor.Enter%2A> в начале блока и <xref:System.Threading.Monitor.Exit%2A> в конце блока.</span><span class="sxs-lookup"><span data-stu-id="99263-110">The `lock` keyword calls <xref:System.Threading.Monitor.Enter%2A> at the start of the block and <xref:System.Threading.Monitor.Exit%2A> at the end of the block.</span></span> <span data-ttu-id="99263-111">Если <xref:System.Threading.Thread.Interrupt%2A> прерывает работу потока, который ожидает ввода оператора `lock`, возникает <xref:System.Threading.ThreadInterruptedException>.</span><span class="sxs-lookup"><span data-stu-id="99263-111">A <xref:System.Threading.ThreadInterruptedException> is thrown if <xref:System.Threading.Thread.Interrupt%2A> interrupts a thread that is waiting to enter a `lock` statement.</span></span>  
  
 <span data-ttu-id="99263-112">Как правило, рекомендуется избегать блокировки типа `public` или экземпляров, которыми код не управляет.</span><span class="sxs-lookup"><span data-stu-id="99263-112">In general, avoid locking on a `public` type, or instances beyond your code's control.</span></span> <span data-ttu-id="99263-113">Это правило не соблюдается в распространенных конструкциях `lock (this)`, `lock (typeof (MyType))` и `lock ("myLock")`.</span><span class="sxs-lookup"><span data-stu-id="99263-113">The common constructs `lock (this)`, `lock (typeof (MyType))`, and `lock ("myLock")` violate this guideline:</span></span>  
  
-   <span data-ttu-id="99263-114">`lock (this)` может привести к проблеме, если к экземпляру допускается открытый доступ.</span><span class="sxs-lookup"><span data-stu-id="99263-114">`lock (this)` is a problem if the instance can be accessed publicly.</span></span>  
  
-   <span data-ttu-id="99263-115">`lock (typeof (MyType))` может привести к проблеме, если к `MyType` допускается открытый доступ.</span><span class="sxs-lookup"><span data-stu-id="99263-115">`lock (typeof (MyType))` is a problem if `MyType` is publicly accessible.</span></span>  
  
-   <span data-ttu-id="99263-116">`lock("myLock")` может привести к проблеме, поскольку любой код в процессе, использующий ту же строку, будет совместно использовать ту же блокировку.</span><span class="sxs-lookup"><span data-stu-id="99263-116">`lock("myLock")` is a problem because any other code in the process using the same string, will share the same lock.</span></span>  
  
 <span data-ttu-id="99263-117">Для блокировки рекомендуется использовать объект `private`. Если нужно защитить данные, являющиеся общими для всех экземпляров, рекомендуется использовать переменную объекта `private static`.</span><span class="sxs-lookup"><span data-stu-id="99263-117">Best practice is to define a `private` object to lock on, or a `private static` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="99263-118">Нельзя использовать ключевое слово [await](../../../csharp/language-reference/keywords/await.md) в теле оператора `lock`.</span><span class="sxs-lookup"><span data-stu-id="99263-118">You can't use the [await](../../../csharp/language-reference/keywords/await.md) keyword in the body of a `lock` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99263-119">Пример</span><span class="sxs-lookup"><span data-stu-id="99263-119">Example</span></span>  
 <span data-ttu-id="99263-120">В следующем примере показано простое использование потоков без блокировки в C#.</span><span class="sxs-lookup"><span data-stu-id="99263-120">The following sample shows a simple use of threads without locking in C#.</span></span>  
  
 <span data-ttu-id="99263-121">[!code-cs[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="99263-121">[!code-cs[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="99263-122">Пример</span><span class="sxs-lookup"><span data-stu-id="99263-122">Example</span></span>  
 <span data-ttu-id="99263-123">В следующем примере используются потоки и ключевое слово`lock`.</span><span class="sxs-lookup"><span data-stu-id="99263-123">The following sample uses threads and `lock`.</span></span> <span data-ttu-id="99263-124">Так как присутствует оператор `lock`, блокировка оператора является важным разделом и `balance` никогда не будет отрицательным числом.</span><span class="sxs-lookup"><span data-stu-id="99263-124">As long as the `lock` statement is present, the statement block is a critical section and `balance` will never become a negative number.</span></span>  
  
 <span data-ttu-id="99263-125">[!code-cs[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="99263-125">[!code-cs[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="99263-126">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="99263-126">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="99263-127">См. также</span><span class="sxs-lookup"><span data-stu-id="99263-127">See Also</span></span>  
 <span data-ttu-id="99263-128"><xref:System.Reflection.MethodImplAttributes></span><span class="sxs-lookup"><span data-stu-id="99263-128"><xref:System.Reflection.MethodImplAttributes></span></span>   
 <span data-ttu-id="99263-129"><xref:System.Threading.Mutex></span><span class="sxs-lookup"><span data-stu-id="99263-129"><xref:System.Threading.Mutex></span></span>   
 <span data-ttu-id="99263-130">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="99263-130">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="99263-131">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="99263-131">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="99263-132">[Работа с потоками](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c) </span><span class="sxs-lookup"><span data-stu-id="99263-132">[Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c) </span></span>  
 <span data-ttu-id="99263-133">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="99263-133">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="99263-134">[Ключевые слова операторов](../../../csharp/language-reference/keywords/statement-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="99263-134">[Statement Keywords](../../../csharp/language-reference/keywords/statement-keywords.md) </span></span>  
 <span data-ttu-id="99263-135">@System.Threading.Monitor</span><span class="sxs-lookup"><span data-stu-id="99263-135">@System.Threading.Monitor</span></span>   
 <span data-ttu-id="99263-136">[Блокируемые операции](../../../standard/threading/interlocked-operations.md) </span><span class="sxs-lookup"><span data-stu-id="99263-136">[Interlocked Operations](../../../standard/threading/interlocked-operations.md) </span></span>  
 <span data-ttu-id="99263-137">[AutoResetEvent](../../../standard/threading/autoresetevent.md) </span><span class="sxs-lookup"><span data-stu-id="99263-137">[AutoResetEvent](../../../standard/threading/autoresetevent.md) </span></span>  
 [<span data-ttu-id="99263-138">Синхронизация потоков</span><span class="sxs-lookup"><span data-stu-id="99263-138">Thread Synchronization</span></span>](http://msdn.microsoft.com/library/413e1f28-a2c5-4eec-8338-aa43e7982ff4)

