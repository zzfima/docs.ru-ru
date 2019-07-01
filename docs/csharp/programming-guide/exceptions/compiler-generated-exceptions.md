---
title: Руководство по программированию на C#. Исключения, создаваемые компилятором
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
ms.openlocfilehash: 28e6ba0c20948aa769a1517c664db80b5beb6b68
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2019
ms.locfileid: "67398033"
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a><span data-ttu-id="ed9fa-102">Исключения, создаваемые компилятором (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="ed9fa-102">Compiler-Generated Exceptions (C# Programming Guide)</span></span>
<span data-ttu-id="ed9fa-103">Некоторые исключения создаются средой .NET Framework CLR (CLR) автоматически, когда происходит сбой основной операции.</span><span class="sxs-lookup"><span data-stu-id="ed9fa-103">Some exceptions are thrown automatically by the .NET Framework's common language runtime (CLR) when basic operations fail.</span></span> <span data-ttu-id="ed9fa-104">В следующей таблице перечислены эти исключения и условия возникновения ошибок.</span><span class="sxs-lookup"><span data-stu-id="ed9fa-104">These exceptions and their error conditions are listed in the following table.</span></span>  
  
|<span data-ttu-id="ed9fa-105">Исключение</span><span class="sxs-lookup"><span data-stu-id="ed9fa-105">Exception</span></span>|<span data-ttu-id="ed9fa-106">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="ed9fa-106">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ArithmeticException>|<span data-ttu-id="ed9fa-107">Базовый класс для исключений, которые возникают при выполнении арифметических операций, таких как <xref:System.DivideByZeroException> и <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="ed9fa-107">A base class for exceptions that occur during arithmetic operations, such as <xref:System.DivideByZeroException> and <xref:System.OverflowException>.</span></span>|  
|<xref:System.ArrayTypeMismatchException>|<span data-ttu-id="ed9fa-108">Возникает, если массив не может сохранить данный элемент, поскольку фактический тип элемента несовместим с фактическим типом массива.</span><span class="sxs-lookup"><span data-stu-id="ed9fa-108">Thrown when an array cannot store a given element because the actual type of the element is incompatible with the actual type of the array.</span></span>|  
|<xref:System.DivideByZeroException>|<span data-ttu-id="ed9fa-109">Возникает при попытке деления целого значения на ноль.</span><span class="sxs-lookup"><span data-stu-id="ed9fa-109">Thrown when an attempt is made to divide an integral value by zero.</span></span>|  
|<xref:System.IndexOutOfRangeException>|<span data-ttu-id="ed9fa-110">Возникает при попытке индексирования массива, если индекс меньше нуля или выходит за границы массива.</span><span class="sxs-lookup"><span data-stu-id="ed9fa-110">Thrown when an attempt is made to index an array when the index is less than zero or outside the bounds of the array.</span></span>|  
|<xref:System.InvalidCastException>|<span data-ttu-id="ed9fa-111">Возникает, если явное преобразование из базового типа в интерфейс или в производный тип завершается ошибкой во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="ed9fa-111">Thrown when an explicit conversion from a base type to an interface or to a derived type fails at runtime.</span></span>|  
|<xref:System.NullReferenceException>|<span data-ttu-id="ed9fa-112">Возникает при попытке сослаться на объект, имеющий значение [null](../../../csharp/language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="ed9fa-112">Thrown when you attempt to reference an object whose value is [null](../../../csharp/language-reference/keywords/null.md).</span></span>|  
|<xref:System.OutOfMemoryException>|<span data-ttu-id="ed9fa-113">Возникает, если попытка распределения памяти с помощью оператора [new](../../../csharp/language-reference/operators/new-operator.md) завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ed9fa-113">Thrown when an attempt to allocate memory using the [new](../../../csharp/language-reference/operators/new-operator.md) operator fails.</span></span> <span data-ttu-id="ed9fa-114">Это означает, что ресурсы памяти, доступные для среды CLR, исчерпаны.</span><span class="sxs-lookup"><span data-stu-id="ed9fa-114">This indicates that the memory available to the common language runtime has been exhausted.</span></span>|  
|<xref:System.OverflowException>|<span data-ttu-id="ed9fa-115">Возникает при переполнении арифметической операции в контексте `checked`.</span><span class="sxs-lookup"><span data-stu-id="ed9fa-115">Thrown when an arithmetic operation in a `checked` context overflows.</span></span>|  
|<xref:System.StackOverflowException>|<span data-ttu-id="ed9fa-116">Возникает, когда чрезмерное количество ожидающих вызовов метода истощает стек выполнения; обычно это указывает на крайне глубокую или бесконечную рекурсию.</span><span class="sxs-lookup"><span data-stu-id="ed9fa-116">Thrown when the execution stack is exhausted by having too many pending method calls; usually indicates a very deep or infinite recursion.</span></span>|  
|<xref:System.TypeInitializationException>|<span data-ttu-id="ed9fa-117">Возникает, когда статический конструктор создает исключение, а совместимого предложения `catch` для его захвата нет.</span><span class="sxs-lookup"><span data-stu-id="ed9fa-117">Thrown when a static constructor throws an exception and no compatible `catch` clause exists to catch it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ed9fa-118">См. также</span><span class="sxs-lookup"><span data-stu-id="ed9fa-118">See also</span></span>

- [<span data-ttu-id="ed9fa-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ed9fa-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="ed9fa-120">Исключения и обработка исключений</span><span class="sxs-lookup"><span data-stu-id="ed9fa-120">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)
- [<span data-ttu-id="ed9fa-121">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="ed9fa-121">Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/exception-handling.md)
- [<span data-ttu-id="ed9fa-122">try-catch</span><span class="sxs-lookup"><span data-stu-id="ed9fa-122">try-catch</span></span>](../../../csharp/language-reference/keywords/try-catch.md)
- [<span data-ttu-id="ed9fa-123">try-finally</span><span class="sxs-lookup"><span data-stu-id="ed9fa-123">try-finally</span></span>](../../../csharp/language-reference/keywords/try-finally.md)
- [<span data-ttu-id="ed9fa-124">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="ed9fa-124">try-catch-finally</span></span>](../../../csharp/language-reference/keywords/try-catch-finally.md)
