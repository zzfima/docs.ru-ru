---
title: Методы завершения (руководство по программированию в C#)
ms.date: 05/10/2017
helpviewer_keywords:
- ~ [C#], in finalizers
- C# language, finalizers
- finalizers [C#]
ms.assetid: 1ae6e46d-a4b1-4a49-abe5-b97f53d9e049
ms.openlocfilehash: b98d5eac29f498672000a7b0354734c15fd7400c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526039"
---
# <a name="finalizers-c-programming-guide"></a><span data-ttu-id="064c1-102">Методы завершения (руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="064c1-102">Finalizers (C# Programming Guide)</span></span>
<span data-ttu-id="064c1-103">Методы завершения используются для уничтожения экземпляров классов.</span><span class="sxs-lookup"><span data-stu-id="064c1-103">Finalizers are used to destruct instances of classes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="064c1-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="064c1-104">Remarks</span></span>  
  
-   <span data-ttu-id="064c1-105">В структурах определение методов завершения невозможно.</span><span class="sxs-lookup"><span data-stu-id="064c1-105">Finalizers cannot be defined in structs.</span></span> <span data-ttu-id="064c1-106">Они применяются только в классах.</span><span class="sxs-lookup"><span data-stu-id="064c1-106">They are only used with classes.</span></span>  
  
-   <span data-ttu-id="064c1-107">Каждый класс может иметь только один метод завершения.</span><span class="sxs-lookup"><span data-stu-id="064c1-107">A class can only have one finalizer.</span></span>  
  
-   <span data-ttu-id="064c1-108">Методы завершения не могут быть унаследованы или перегружены.</span><span class="sxs-lookup"><span data-stu-id="064c1-108">Finalizers cannot be inherited or overloaded.</span></span>  
  
-   <span data-ttu-id="064c1-109">Методы завершения невозможно вызвать.</span><span class="sxs-lookup"><span data-stu-id="064c1-109">Finalizers cannot be called.</span></span> <span data-ttu-id="064c1-110">Они запускаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="064c1-110">They are invoked automatically.</span></span>  
  
-   <span data-ttu-id="064c1-111">Метод завершения не принимает модификаторов и не имеет параметров.</span><span class="sxs-lookup"><span data-stu-id="064c1-111">A finalizer does not take modifiers or have parameters.</span></span>  
  
 <span data-ttu-id="064c1-112">Например, ниже показано объявление метода завершения для класса `Car`.</span><span class="sxs-lookup"><span data-stu-id="064c1-112">For example, the following is a declaration of a finalizer for the `Car` class.</span></span>
  
 [!code-csharp[csProgGuideObjects#86](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_1.cs)]  

<span data-ttu-id="064c1-113">Метод завершения можно также реализовать как определение тела выражения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="064c1-113">A finalizer can also be implemented as an expression body definition, as the following example shows.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  
  
 <span data-ttu-id="064c1-114">Метод завершения неявно вызывает метод <xref:System.Object.Finalize%2A> для базового класса объекта.</span><span class="sxs-lookup"><span data-stu-id="064c1-114">The finalizer implicitly calls <xref:System.Object.Finalize%2A> on the base class of the object.</span></span> <span data-ttu-id="064c1-115">В связи с этим вызов метода завершения неявно преобразуется в следующий код:</span><span class="sxs-lookup"><span data-stu-id="064c1-115">Therefore, a call to a finalizer is implicitly translated to the following code:</span></span>  
  
```csharp  
protected override void Finalize()  
{  
    try  
    {  
        // Cleanup statements...  
    }  
    finally  
    {  
        base.Finalize();  
    }  
}  
```  
  
 <span data-ttu-id="064c1-116">Это означает, что метод `Finalize` вызывается рекурсивно для всех экземпляров цепочки наследования начиная с самого дальнего и заканчивая самым первым.</span><span class="sxs-lookup"><span data-stu-id="064c1-116">This means that the `Finalize` method is called recursively for all instances in the inheritance chain, from the most-derived to the least-derived.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="064c1-117">Не следует использовать пустые методы завершения.</span><span class="sxs-lookup"><span data-stu-id="064c1-117">Empty finalizers should not be used.</span></span> <span data-ttu-id="064c1-118">Если класс содержит метод завершения, то в очереди метода `Finalize` создается запись.</span><span class="sxs-lookup"><span data-stu-id="064c1-118">When a class contains a finalizer, an entry is created in the `Finalize` queue.</span></span> <span data-ttu-id="064c1-119">При вызове метода завершения вызывается сборщик мусора, выполняющий обработку очереди.</span><span class="sxs-lookup"><span data-stu-id="064c1-119">When the finalizer is called, the garbage collector is invoked to process the queue.</span></span> <span data-ttu-id="064c1-120">Если метод завершения пустой, это приводит только к ненужному снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="064c1-120">An empty finalizer just causes a needless loss of performance.</span></span>  
  
 <span data-ttu-id="064c1-121">Программист не может управлять моментом вызова метода завершения, потому что этот момент определяется сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="064c1-121">The programmer has no control over when the finalizer is called because this is determined by the garbage collector.</span></span> <span data-ttu-id="064c1-122">Сборщик мусора проверяет наличие объектов, которые больше не используются приложением.</span><span class="sxs-lookup"><span data-stu-id="064c1-122">The garbage collector checks for objects that are no longer being used by the application.</span></span> <span data-ttu-id="064c1-123">Если он считает, что какой-либо объект требует уничтожения, то вызывает метод завершения (при наличии) и освобождает память, используемую для хранения этого объекта.</span><span class="sxs-lookup"><span data-stu-id="064c1-123">If it considers an object eligible for finalization, it calls the finalizer (if any) and reclaims the memory used to store the object.</span></span> 
 
 <span data-ttu-id="064c1-124">В приложениях .NET Framework (но не в приложениях .NET Core) методы завершения также вызываются при выходе из программы.</span><span class="sxs-lookup"><span data-stu-id="064c1-124">In .NET Framework applications (but not in .NET Core applications), finalizers are also called when the program exits.</span></span> 
  
 <span data-ttu-id="064c1-125">Сборку мусора можно выполнить принудительно, вызвав метод <xref:System.GC.Collect%2A>, но в большинстве случаев этого следует избегать из-за возможных проблем с производительностью.</span><span class="sxs-lookup"><span data-stu-id="064c1-125">It is possible to force garbage collection by calling <xref:System.GC.Collect%2A>, but most of the time, this should be avoided because it may create performance issues.</span></span>  
  
## <a name="using-finalizers-to-release-resources"></a><span data-ttu-id="064c1-126">Использование методов завершения для освобождения ресурсов</span><span class="sxs-lookup"><span data-stu-id="064c1-126">Using Finalizers to Release Resources</span></span>  
 <span data-ttu-id="064c1-127">В целом язык C# не требует управления памятью в той степени, в какой это требуется в случае разработки кода на языке, не рассчитанном на среду выполнения со сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="064c1-127">In general, C# does not require as much memory management as is needed when you develop with a language that does not target a runtime with garbage collection.</span></span> <span data-ttu-id="064c1-128">Это связано с тем, что сборщик мусора платформы .NET Framework неявным образом управляет выделением и высвобождением памяти для объектов.</span><span class="sxs-lookup"><span data-stu-id="064c1-128">This is because the .NET Framework garbage collector implicitly manages the allocation and release of memory for your objects.</span></span> <span data-ttu-id="064c1-129">Однако при инкапсуляции приложением неуправляемых ресурсов, например окон, файлов и сетевых подключений, для высвобождения этих ресурсов следует использовать методы завершения.</span><span class="sxs-lookup"><span data-stu-id="064c1-129">However, when your application encapsulates unmanaged resources such as windows, files, and network connections, you should use finalizers to free those resources.</span></span> <span data-ttu-id="064c1-130">Если объект допускает завершение, то сборщик мусора выполняет метод `Finalize` этого объекта.</span><span class="sxs-lookup"><span data-stu-id="064c1-130">When the object is eligible for finalization, the garbage collector runs the `Finalize` method of the object.</span></span>  
  
## <a name="explicit-release-of-resources"></a><span data-ttu-id="064c1-131">Высвобождение ресурсов явным образом</span><span class="sxs-lookup"><span data-stu-id="064c1-131">Explicit Release of Resources</span></span>  
 <span data-ttu-id="064c1-132">В случае, когда приложением используется ценный внешний ресурс, также рекомендуется обеспечить способ высвобождения этого ресурса явным образом, прежде чем сборщик мусора освободит объект.</span><span class="sxs-lookup"><span data-stu-id="064c1-132">If your application is using an expensive external resource, we also recommend that you provide a way to explicitly release the resource before the garbage collector frees the object.</span></span> <span data-ttu-id="064c1-133">Для этого реализуется метод `Dispose` интерфейса <xref:System.IDisposable>, который выполняет необходимую для объекта очистку.</span><span class="sxs-lookup"><span data-stu-id="064c1-133">You do this by implementing a `Dispose` method from the <xref:System.IDisposable> interface that performs the necessary cleanup for the object.</span></span> <span data-ttu-id="064c1-134">Это может значительно повысить производительность приложения.</span><span class="sxs-lookup"><span data-stu-id="064c1-134">This can considerably improve the performance of the application.</span></span> <span data-ttu-id="064c1-135">Даже в случае использования такого явного управления ресурсами метод завершения становится резервным средством очистки ресурсов, если вызов метода `Dispose` выполнить не удастся.</span><span class="sxs-lookup"><span data-stu-id="064c1-135">Even with this explicit control over resources, the finalizer becomes a safeguard to clean up resources if the call to the `Dispose` method failed.</span></span>  
  
 <span data-ttu-id="064c1-136">Дополнительные сведения об очистке ресурсов см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="064c1-136">For more details about cleaning up resources, see the following topics:</span></span>  
  
-   [<span data-ttu-id="064c1-137">Очистка неуправляемых ресурсов</span><span class="sxs-lookup"><span data-stu-id="064c1-137">Cleaning Up Unmanaged Resources</span></span>](../../../standard/garbage-collection/unmanaged.md)  
  
-   [<span data-ttu-id="064c1-138">Реализация метода dispose</span><span class="sxs-lookup"><span data-stu-id="064c1-138">Implementing a Dispose Method</span></span>](../../../standard/garbage-collection/implementing-dispose.md)  
  
-   [<span data-ttu-id="064c1-139">Оператор using</span><span class="sxs-lookup"><span data-stu-id="064c1-139">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)  
  
## <a name="example"></a><span data-ttu-id="064c1-140">Пример</span><span class="sxs-lookup"><span data-stu-id="064c1-140">Example</span></span>  
 <span data-ttu-id="064c1-141">В приведенном ниже примере создаются три класса, образующих цепочку наследования.</span><span class="sxs-lookup"><span data-stu-id="064c1-141">The following example creates three classes that make a chain of inheritance.</span></span> <span data-ttu-id="064c1-142">Класс `First` является базовым, класс `Second` является производным от класса `First`, а класс `Third` является производным от класса `Second`.</span><span class="sxs-lookup"><span data-stu-id="064c1-142">The class `First` is the base class, `Second` is derived from `First`, and `Third` is derived from `Second`.</span></span> <span data-ttu-id="064c1-143">Все три класса имеют методы завершения.</span><span class="sxs-lookup"><span data-stu-id="064c1-143">All three have finalizers.</span></span> <span data-ttu-id="064c1-144">В методе `Main` создается экземпляр самого дальнего в цепочке наследования класса.</span><span class="sxs-lookup"><span data-stu-id="064c1-144">In `Main`, an instance of the most-derived class is created.</span></span> <span data-ttu-id="064c1-145">При выполнении программы обратите внимание на то, что методы завершения для всех трех классов вызываются автоматически в порядке от самого дальнего до первого в цепочке наследования.</span><span class="sxs-lookup"><span data-stu-id="064c1-145">When the program runs, notice that the finalizers for the three classes are called automatically, and in order, from the most-derived to the least-derived.</span></span>  
  
 [!code-csharp[csProgGuideObjects#85](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="064c1-146">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="064c1-146">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="064c1-147">См. также</span><span class="sxs-lookup"><span data-stu-id="064c1-147">See Also</span></span>

- <xref:System.IDisposable>  
- [<span data-ttu-id="064c1-148">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="064c1-148">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="064c1-149">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="064c1-149">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
- [<span data-ttu-id="064c1-150">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="064c1-150">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
