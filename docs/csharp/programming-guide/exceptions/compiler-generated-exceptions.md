---
title: "Исключения, создаваемые компилятором (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d1417e42f588978d5fc1beca4ad55463502ee219
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a><span data-ttu-id="58b16-102">Исключения, создаваемые компилятором (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="58b16-102">Compiler-Generated Exceptions (C# Programming Guide)</span></span>
<span data-ttu-id="58b16-103">Некоторые исключения создаются средой .NET Framework CLR (CLR) автоматически, когда происходит сбой основной операции.</span><span class="sxs-lookup"><span data-stu-id="58b16-103">Some exceptions are thrown automatically by the .NET Framework's common language runtime (CLR) when basic operations fail.</span></span> <span data-ttu-id="58b16-104">В следующей таблице перечислены эти исключения и условия возникновения ошибок.</span><span class="sxs-lookup"><span data-stu-id="58b16-104">These exceptions and their error conditions are listed in the following table.</span></span>  
  
|<span data-ttu-id="58b16-105">Исключение</span><span class="sxs-lookup"><span data-stu-id="58b16-105">Exception</span></span>|<span data-ttu-id="58b16-106">Описание</span><span class="sxs-lookup"><span data-stu-id="58b16-106">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ArithmeticException>|<span data-ttu-id="58b16-107">Базовый класс для исключений, которые возникают при выполнении арифметических операций, таких как <xref:System.DivideByZeroException> и <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="58b16-107">A base class for exceptions that occur during arithmetic operations, such as <xref:System.DivideByZeroException> and <xref:System.OverflowException>.</span></span>|  
|<xref:System.ArrayTypeMismatchException>|<span data-ttu-id="58b16-108">Возникает, если массив не может сохранить данный элемент, поскольку фактический тип элемента несовместим с фактическим типом массива.</span><span class="sxs-lookup"><span data-stu-id="58b16-108">Thrown when an array cannot store a given element because the actual type of the element is incompatible with the actual type of the array.</span></span>|  
|<xref:System.DivideByZeroException>|<span data-ttu-id="58b16-109">Возникает при попытке деления целого значения на ноль.</span><span class="sxs-lookup"><span data-stu-id="58b16-109">Thrown when an attempt is made to divide an integral value by zero.</span></span>|  
|<xref:System.IndexOutOfRangeException>|<span data-ttu-id="58b16-110">Возникает при попытке индексирования массива, если индекс меньше нуля или выходит за границы массива.</span><span class="sxs-lookup"><span data-stu-id="58b16-110">Thrown when an attempt is made to index an array when the index is less than zero or outside the bounds of the array.</span></span>|  
|<xref:System.InvalidCastException>|<span data-ttu-id="58b16-111">Возникает, если явное преобразование из базового типа в интерфейс или в производный тип завершается ошибкой во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="58b16-111">Thrown when an explicit conversion from a base type to an interface or to a derived type fails at runtime.</span></span>|  
|<xref:System.NullReferenceException>|<span data-ttu-id="58b16-112">Возникает при попытке сослаться на объект, имеющий значение [null](../../../csharp/language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="58b16-112">Thrown when you attempt to reference an object whose value is [null](../../../csharp/language-reference/keywords/null.md).</span></span>|  
|<xref:System.OutOfMemoryException>|<span data-ttu-id="58b16-113">Возникает, если попытка распределения памяти с помощью оператора [new](../../../csharp/language-reference/keywords/new-operator.md) завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="58b16-113">Thrown when an attempt to allocate memory using the [new](../../../csharp/language-reference/keywords/new-operator.md) operator fails.</span></span> <span data-ttu-id="58b16-114">Это означает, что ресурсы памяти, доступные для среды CLR, исчерпаны.</span><span class="sxs-lookup"><span data-stu-id="58b16-114">This indicates that the memory available to the common language runtime has been exhausted.</span></span>|  
|<xref:System.OverflowException>|<span data-ttu-id="58b16-115">Возникает при переполнении арифметической операции в контексте `checked`.</span><span class="sxs-lookup"><span data-stu-id="58b16-115">Thrown when an arithmetic operation in a `checked` context overflows.</span></span>|  
|<xref:System.StackOverflowException>|<span data-ttu-id="58b16-116">Возникает, когда чрезмерное количество ожидающих вызовов метода истощает стек выполнения; обычно это указывает на крайне глубокую или бесконечную рекурсию.</span><span class="sxs-lookup"><span data-stu-id="58b16-116">Thrown when the execution stack is exhausted by having too many pending method calls; usually indicates a very deep or infinite recursion.</span></span>|  
|<xref:System.TypeInitializationException>|<span data-ttu-id="58b16-117">Возникает, когда статический конструктор создает исключение, а совместимого предложения `catch` для его захвата нет.</span><span class="sxs-lookup"><span data-stu-id="58b16-117">Thrown when a static constructor throws an exception and no compatible `catch` clause exists to catch it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="58b16-118">См. также</span><span class="sxs-lookup"><span data-stu-id="58b16-118">See Also</span></span>  
 [<span data-ttu-id="58b16-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="58b16-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="58b16-120">Исключения и обработка исключений</span><span class="sxs-lookup"><span data-stu-id="58b16-120">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)  
 [<span data-ttu-id="58b16-121">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="58b16-121">Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/exception-handling.md)  
 [<span data-ttu-id="58b16-122">try-catch</span><span class="sxs-lookup"><span data-stu-id="58b16-122">try-catch</span></span>](../../../csharp/language-reference/keywords/try-catch.md)  
 [<span data-ttu-id="58b16-123">try-finally</span><span class="sxs-lookup"><span data-stu-id="58b16-123">try-finally</span></span>](../../../csharp/language-reference/keywords/try-finally.md)  
 [<span data-ttu-id="58b16-124">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="58b16-124">try-catch-finally</span></span>](../../../csharp/language-reference/keywords/try-catch-finally.md)
