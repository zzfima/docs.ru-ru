---
title: Практическое руководство. Объявление, создание экземпляра и использование делегата (руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], declaring and instantiating
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
ms.openlocfilehash: 6c53d7572074db44976494e5eed596bf95aaf456
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858864"
---
# <a name="how-to-declare-instantiate-and-use-a-delegate-c-programming-guide"></a><span data-ttu-id="a7ccf-102">Практическое руководство. Объявление, создание экземпляра и использование делегата (руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="a7ccf-102">How to: Declare, Instantiate, and Use a Delegate (C# Programming Guide)</span></span>
<span data-ttu-id="a7ccf-103">В C# 1.0 и более поздних версий делегаты можно объявлять так, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-103">In C# 1.0 and later, delegates can be declared as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#13](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_1.cs)]  
  
 [!code-csharp[csProgGuideDelegates#14](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_2.cs)]  
  
 <span data-ttu-id="a7ccf-104">В C# 2.0 предоставлен более простой способ для записи предыдущего объявления, который показан в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-104">C# 2.0 provides a simpler way to write the previous declaration, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#32](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_3.cs)]  
  
 <span data-ttu-id="a7ccf-105">В C# 2.0 и более поздних версиях можно использовать анонимный метод для объявления и инициализации [делегата](../../../csharp/language-reference/keywords/delegate.md), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-105">In C# 2.0 and later, it is also possible to use an anonymous method to declare and initialize a [delegate](../../../csharp/language-reference/keywords/delegate.md), as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#15](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_4.cs)]  
  
 <span data-ttu-id="a7ccf-106">В C# 3.0 и более поздних версиях можно объявлять делегаты и создавать для них экземпляры с помощью лямбда-выражения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-106">In C# 3.0 and later, delegates can also be declared and instantiated by using a lambda expression, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#31](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_5.cs)]  
  
 <span data-ttu-id="a7ccf-107">Дополнительные сведения см. в разделе [Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a7ccf-107">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="a7ccf-108">Следующий пример демонстрирует объявление, создание экземпляра и использование делегата.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-108">The following example illustrates declaring, instantiating, and using a delegate.</span></span> <span data-ttu-id="a7ccf-109">Класс `BookDB` инкапсулирует базу данных книжного магазина, в которой хранится информация о книгах.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-109">The `BookDB` class encapsulates a bookstore database that maintains a database of books.</span></span> <span data-ttu-id="a7ccf-110">Он предоставляет метод `ProcessPaperbackBooks`, который находит в базе данных все книги в мягкой обложке и вызывает делегат для каждой из них.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-110">It exposes a method, `ProcessPaperbackBooks`, which finds all paperback books in the database and calls a delegate for each one.</span></span> <span data-ttu-id="a7ccf-111">Используется тип `delegate` с именем `ProcessBookDelegate`.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-111">The `delegate` type that is used is named `ProcessBookDelegate`.</span></span> <span data-ttu-id="a7ccf-112">Класс `Test` использует этот класс для печати заголовков и средней цены книг в мягкой обложке.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-112">The `Test` class uses this class to print the titles and average price of the paperback books.</span></span>  
  
 <span data-ttu-id="a7ccf-113">Использование делегата помогает правильно разделить функции между базой данных книжного магазина и кодом клиента.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-113">The use of delegates promotes good separation of functionality between the bookstore database and the client code.</span></span> <span data-ttu-id="a7ccf-114">Код клиента не имеет сведений о том, как хранятся книги и как код книжного магазина находит книги в мягкой обложке.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-114">The client code has no knowledge of how the books are stored or how the bookstore code finds paperback books.</span></span> <span data-ttu-id="a7ccf-115">Код книжного магазина не имеет сведений о том, какая обработка выполняется для найденных книг в мягкой обложке.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-115">The bookstore code has no knowledge of what processing is performed on the paperback books after it finds them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7ccf-116">Пример</span><span class="sxs-lookup"><span data-stu-id="a7ccf-116">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#12](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_6.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="a7ccf-117">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="a7ccf-117">Robust Programming</span></span>  
  
-   <span data-ttu-id="a7ccf-118">Объявление делегата.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-118">Declaring a delegate.</span></span>  
  
     <span data-ttu-id="a7ccf-119">Следующая инструкция объявляет новый тип делегата.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-119">The following statement declares a new delegate type.</span></span>  
  
     [!code-csharp[csProgGuideDelegates#16](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_7.cs)]  
  
     <span data-ttu-id="a7ccf-120">Каждый тип делегата описывает количество аргументов и их типы, а также тип возвращаемого значения для всех методов, которые он может инкапсулировать.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-120">Each delegate type describes the number and types of the arguments, and the type of the return value of methods that it can encapsulate.</span></span> <span data-ttu-id="a7ccf-121">Каждый раз, когда требуется новый набор типов аргументов или новый тип возвращаемого значения, нужно объявить новый тип делегата.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-121">Whenever a new set of argument types or return value type is needed, a new delegate type must be declared.</span></span>  
  
-   <span data-ttu-id="a7ccf-122">Создания экземпляра делегата.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-122">Instantiating a delegate.</span></span>  
  
     <span data-ttu-id="a7ccf-123">После объявления типа делегата нужно создать объект этого делегата и связать его с определенным методом.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-123">After a delegate type has been declared, a delegate object must be created and associated with a particular method.</span></span> <span data-ttu-id="a7ccf-124">Продолжая предыдущий пример, вы можете передать метод `PrintTitle` в метод `ProcessPaperbackBooks`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a7ccf-124">In the previous example, you do this by passing the `PrintTitle` method to the `ProcessPaperbackBooks` method as in the following example:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#17](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_8.cs)]  
  
     <span data-ttu-id="a7ccf-125">Будет создан новый объект делегата, связанный со [статическим](../../../csharp/language-reference/keywords/static.md) методом `Test.PrintTitle`.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-125">This creates a new delegate object associated with the [static](../../../csharp/language-reference/keywords/static.md) method `Test.PrintTitle`.</span></span> <span data-ttu-id="a7ccf-126">Аналогичным образом, в следующем примере передается нестатический метод `AddBookToTotal` для объекта `totaller`:</span><span class="sxs-lookup"><span data-stu-id="a7ccf-126">Similarly, the non-static method `AddBookToTotal` on the object `totaller` is passed as in the following example:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#18](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_9.cs)]  
  
     <span data-ttu-id="a7ccf-127">В обоих случаях новый объект делегата передается в метод `ProcessPaperbackBooks`.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-127">In both cases a new delegate object is passed to the `ProcessPaperbackBooks` method.</span></span>  
  
     <span data-ttu-id="a7ccf-128">После создания делегата невозможно изменить метод, с которым он связан. Объекты делегатов являются неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-128">After a delegate is created, the method it is associated with never changes; delegate objects are immutable.</span></span>  
  
-   <span data-ttu-id="a7ccf-129">Использование делегатов</span><span class="sxs-lookup"><span data-stu-id="a7ccf-129">Calling a delegate.</span></span>  
  
     <span data-ttu-id="a7ccf-130">Обычно после создания объекта делегата он передается в другой код, который будет использовать этот делегат.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-130">After a delegate object is created, the delegate object is typically passed to other code that will call the delegate.</span></span> <span data-ttu-id="a7ccf-131">Для вызова объекта делегата используется имя этого объекта, за которым следуют параметризованные аргументы, которые нужно передать делегату.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-131">A delegate object is called by using the name of the delegate object, followed by the parenthesized arguments to be passed to the delegate.</span></span> <span data-ttu-id="a7ccf-132">Ниже показан пример использования делегата.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-132">Following is an example of a delegate call:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#19](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_10.cs)]  
  
     <span data-ttu-id="a7ccf-133">Делегат можно вызвать синхронно, как показано в этом примере, или асинхронно при помощи методов `BeginInvoke` и `EndInvoke`.</span><span class="sxs-lookup"><span data-stu-id="a7ccf-133">A delegate can be either called synchronously, as in this example, or asynchronously by using `BeginInvoke` and `EndInvoke` methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7ccf-134">См. также</span><span class="sxs-lookup"><span data-stu-id="a7ccf-134">See Also</span></span>

- [<span data-ttu-id="a7ccf-135">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a7ccf-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a7ccf-136">События</span><span class="sxs-lookup"><span data-stu-id="a7ccf-136">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
- [<span data-ttu-id="a7ccf-137">Делегаты</span><span class="sxs-lookup"><span data-stu-id="a7ccf-137">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
