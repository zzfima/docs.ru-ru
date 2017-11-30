---
title: "Блокируемые операции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Interlocked class, about Interlocked class
- threading [.NET Framework], Interlocked class
ms.assetid: cbda7114-c752-4f3e-ada1-b1e8dd262f2b
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 122058b7e826e27fe6c60c5b07610f7c63e64f78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="interlocked-operations"></a><span data-ttu-id="aa493-102">Блокируемые операции</span><span class="sxs-lookup"><span data-stu-id="aa493-102">Interlocked Operations</span></span>
<span data-ttu-id="aa493-103"><xref:System.Threading.Interlocked> Класс предоставляет методы для синхронизации доступа к переменной, которая совместно используется несколькими потоками.</span><span class="sxs-lookup"><span data-stu-id="aa493-103">The <xref:System.Threading.Interlocked> class provides methods that synchronize access to a variable that is shared by multiple threads.</span></span> <span data-ttu-id="aa493-104">Потоки различных процессов могут использовать этот механизм, если переменная находится в общей памяти.</span><span class="sxs-lookup"><span data-stu-id="aa493-104">The threads of different processes can use this mechanism if the variable is in shared memory.</span></span> <span data-ttu-id="aa493-105">Блокируемые операции являются атомарными, т. е. вся операция представляет собой единицу, которая не может быть прервана другой блокируемой операцией с той же переменной.</span><span class="sxs-lookup"><span data-stu-id="aa493-105">Interlocked operations are atomic — that is, the entire operation is a unit that cannot be interrupted by another interlocked operation on the same variable.</span></span> <span data-ttu-id="aa493-106">Это имеет значение в операционных системах с преимущественной многопоточностью, когда поток может быть приостановлен после загрузки значения из адреса памяти, но прежде, чем его можно будет изменить или сохранить.</span><span class="sxs-lookup"><span data-stu-id="aa493-106">This is important in operating systems with preemptive multithreading, where a thread can be suspended after loading a value from a memory address, but before having the chance to alter it and store it.</span></span>  
  
 <span data-ttu-id="aa493-107"><xref:System.Threading.Interlocked> Класс предоставляет следующие операции:</span><span class="sxs-lookup"><span data-stu-id="aa493-107">The <xref:System.Threading.Interlocked> class provides the following operations:</span></span>  
  
-   <span data-ttu-id="aa493-108">В .NET Framework версии 2.0 <xref:System.Threading.Interlocked.Add%2A> метод добавляет целочисленное значение для переменной и возвращает новое значение переменной.</span><span class="sxs-lookup"><span data-stu-id="aa493-108">In the .NET Framework version 2.0, the <xref:System.Threading.Interlocked.Add%2A> method adds an integer value to a variable and returns the new value of the variable.</span></span>  
  
-   <span data-ttu-id="aa493-109">В .NET Framework версии 2.0 <xref:System.Threading.Interlocked.Read%2A> метод считывает 64-разрядное целое значение в виде атомарной операции.</span><span class="sxs-lookup"><span data-stu-id="aa493-109">In the .NET Framework version 2.0, the <xref:System.Threading.Interlocked.Read%2A> method reads a 64-bit integer value as an atomic operation.</span></span> <span data-ttu-id="aa493-110">Это пригодится в 32-разрядных операционных системах, где считывание 64-разрядного целого числа обычно не является атомарной операцией.</span><span class="sxs-lookup"><span data-stu-id="aa493-110">This is useful on 32-bit operating systems, where reading a 64-bit integer is not ordinarily an atomic operation.</span></span>  
  
-   <span data-ttu-id="aa493-111"><xref:System.Threading.Interlocked.Increment%2A> И <xref:System.Threading.Interlocked.Decrement%2A> методы увеличивают или уменьшают переменную и возвращают результирующее значение.</span><span class="sxs-lookup"><span data-stu-id="aa493-111">The <xref:System.Threading.Interlocked.Increment%2A> and <xref:System.Threading.Interlocked.Decrement%2A> methods increment or decrement a variable and return the resulting value.</span></span>  
  
-   <span data-ttu-id="aa493-112"><xref:System.Threading.Interlocked.Exchange%2A> Метод выполняет атомарный обмен значение в указанной переменной, возвращая текущее значение и заменив его новым значением.</span><span class="sxs-lookup"><span data-stu-id="aa493-112">The <xref:System.Threading.Interlocked.Exchange%2A> method performs an atomic exchange of the value in a specified variable, returning that value and replacing it with a new value.</span></span> <span data-ttu-id="aa493-113">На платформе .NET Framework версии 2.0 универсальную перегрузку этого метода можно использовать для обмена значений в переменной любого ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="aa493-113">In the .NET Framework version 2.0, a generic overload of this method can be used to perform this exchange on a variable of any reference type.</span></span> <span data-ttu-id="aa493-114">См. раздел <xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29>.</span><span class="sxs-lookup"><span data-stu-id="aa493-114">See <xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29>.</span></span>  
  
-   <span data-ttu-id="aa493-115"><xref:System.Threading.Interlocked.CompareExchange%2A> Метод также обменивает два значения, но производное от результата сравнения.</span><span class="sxs-lookup"><span data-stu-id="aa493-115">The <xref:System.Threading.Interlocked.CompareExchange%2A> method also exchanges two values, but contingent on the result of a comparison.</span></span> <span data-ttu-id="aa493-116">На платформе .NET Framework версии 2.0 универсальную перегрузку этого метода можно использовать для обмена значений в переменной любого ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="aa493-116">In the .NET Framework version 2.0, a generic overload of this method can be used to perform this exchange on a variable of any reference type.</span></span> <span data-ttu-id="aa493-117">См. раздел <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>.</span><span class="sxs-lookup"><span data-stu-id="aa493-117">See <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>.</span></span>  
  
 <span data-ttu-id="aa493-118">Современные процессоры методы <xref:System.Threading.Interlocked> часто классов можно реализовать с помощью одной инструкции.</span><span class="sxs-lookup"><span data-stu-id="aa493-118">On modern processors, the methods of the <xref:System.Threading.Interlocked> class can often be implemented by a single instruction.</span></span> <span data-ttu-id="aa493-119">В связи с этим они обеспечивают очень высокую производительность синхронизации и могут использоваться для сборки сложных механизмов синхронизации, таких как спин-блокировки.</span><span class="sxs-lookup"><span data-stu-id="aa493-119">Thus, they provide very high-performance synchronization and can be used to build higher-level synchronization mechanisms, like spin locks.</span></span>  
  
 <span data-ttu-id="aa493-120">Пример, использующий <xref:System.Threading.Monitor> и <xref:System.Threading.Interlocked> классы в сочетании, в разделе [мониторы](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).</span><span class="sxs-lookup"><span data-stu-id="aa493-120">For an example that uses the <xref:System.Threading.Monitor> and <xref:System.Threading.Interlocked> classes in combination, see [Monitors](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).</span></span>  
  
## <a name="compareexchange-example"></a><span data-ttu-id="aa493-121">Пример метода CompareExchange</span><span class="sxs-lookup"><span data-stu-id="aa493-121">CompareExchange Example</span></span>  
 <span data-ttu-id="aa493-122"><xref:System.Threading.Interlocked.CompareExchange%2A> Метод может использоваться для защиты, которые сложнее, чем простое увеличение и уменьшение вычислений.</span><span class="sxs-lookup"><span data-stu-id="aa493-122">The <xref:System.Threading.Interlocked.CompareExchange%2A> method can be used to protect computations that are more complicated than simple increment and decrement.</span></span> <span data-ttu-id="aa493-123">В следующем примере показан безопасный для потока метод, который добавляется к промежуточному итогу, хранящемуся в виде числа с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="aa493-123">The following example demonstrates a thread-safe method that adds to a running total stored as a floating point number.</span></span> <span data-ttu-id="aa493-124">(Для целых чисел, <xref:System.Threading.Interlocked.Add%2A> метод является простым решением.) Полные примеры кода, в разделе перегрузки <xref:System.Threading.Interlocked.CompareExchange%2A> , принимающие аргументы с плавающей запятой одиночной точности и двойной точности (<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29> и <xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>).</span><span class="sxs-lookup"><span data-stu-id="aa493-124">(For integers, the <xref:System.Threading.Interlocked.Add%2A> method is a simpler solution.) For complete code examples, see the overloads of <xref:System.Threading.Interlocked.CompareExchange%2A> that take single-precision and double-precision floating-point arguments (<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29> and <xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>).</span></span>  
  
 [!code-cpp[Conceptual.Interlocked#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Interlocked#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source1.cs#1)]
 [!code-vb[Conceptual.Interlocked#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source1.vb#1)]  
  
## <a name="untyped-overloads-of-exchange-and-compareexchange"></a><span data-ttu-id="aa493-125">Нетипизированные перегрузки Exchange и CompareExchange</span><span class="sxs-lookup"><span data-stu-id="aa493-125">Untyped Overloads of Exchange and CompareExchange</span></span>  
 <span data-ttu-id="aa493-126"><xref:System.Threading.Interlocked.Exchange%2A> И <xref:System.Threading.Interlocked.CompareExchange%2A> методы имеют перегрузки, принимающие аргументы типа <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="aa493-126">The <xref:System.Threading.Interlocked.Exchange%2A> and <xref:System.Threading.Interlocked.CompareExchange%2A> methods have overloads that take arguments of type <xref:System.Object>.</span></span> <span data-ttu-id="aa493-127">Первый аргумент в каждой из этих версий — `ref Object` (`ByRef … As Object` в Visual Basic), и безопасность типов требует переменную, передаваемую в следующий аргумент, чтобы быть строго типизированы как <xref:System.Object>; нельзя просто привести первый аргумент к типу <xref:System.Object> При вызове этих методов.</span><span class="sxs-lookup"><span data-stu-id="aa493-127">The first argument of each of these overloads is `ref Object` (`ByRef … As Object` in Visual Basic), and type safety requires the variable passed to this argument to be typed strictly as <xref:System.Object>; you cannot simply cast the first argument to type <xref:System.Object> when calling these methods.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa493-128">В .NET Framework версии 2.0, используйте универсальный перегрузки <xref:System.Threading.Interlocked.Exchange%2A> и <xref:System.Threading.Interlocked.CompareExchange%2A> методы для обмена строго типизированные переменные.</span><span class="sxs-lookup"><span data-stu-id="aa493-128">In the .NET Framework version 2.0, use the generic overloads of the <xref:System.Threading.Interlocked.Exchange%2A> and <xref:System.Threading.Interlocked.CompareExchange%2A> methods to exchange strongly typed variables.</span></span>  
  
 <span data-ttu-id="aa493-129">В следующем примере кода показано свойство типа `ClassA`, которое может быть задано однократно, так как подходит для реализации на платформе .NET Framework версии 1.0 или 1.1.</span><span class="sxs-lookup"><span data-stu-id="aa493-129">The following code example shows a property of type `ClassA` that can be set only once, as it might be implemented in the .NET Framework version 1.0 or 1.1.</span></span>  
  
 [!code-cpp[Conceptual.Interlocked#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Interlocked#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source2.cs#2)]
 [!code-vb[Conceptual.Interlocked#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="aa493-130">См. также</span><span class="sxs-lookup"><span data-stu-id="aa493-130">See Also</span></span>  
 <xref:System.Threading.Interlocked>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="aa493-131">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="aa493-131">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="aa493-132">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="aa493-132">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
