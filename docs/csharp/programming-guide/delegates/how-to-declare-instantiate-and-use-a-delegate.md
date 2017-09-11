---
title: "Практическое руководство. Объявление, создание экземпляра и использование делегата (руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- delegates [C#], declaring and instantiating
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
caps.latest.revision: 21
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
ms.openlocfilehash: 5a16fe4c627989f701ba523769cd87839d074849
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-declare-instantiate-and-use-a-delegate-c-programming-guide"></a><span data-ttu-id="db6fe-102">Практическое руководство. Объявление, создание экземпляра и использование делегата (руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="db6fe-102">How to: Declare, Instantiate, and Use a Delegate (C# Programming Guide)</span></span>
<span data-ttu-id="db6fe-103">В C# 1.0 и более поздних версий делегаты можно объявлять так, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="db6fe-103">In C# 1.0 and later, delegates can be declared as shown in the following example.</span></span>  
  
 <span data-ttu-id="db6fe-104">[!code-cs[csProgGuideDelegates#13](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="db6fe-104">[!code-cs[csProgGuideDelegates#13](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_1.cs)]</span></span>  
  
 <span data-ttu-id="db6fe-105">[!code-cs[csProgGuideDelegates#14](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="db6fe-105">[!code-cs[csProgGuideDelegates#14](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_2.cs)]</span></span>  
  
 <span data-ttu-id="db6fe-106">В C# 2.0 предоставлен более простой способ для записи предыдущего объявления, который показан в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="db6fe-106">C# 2.0 provides a simpler way to write the previous declaration, as shown in the following example.</span></span>  
  
 <span data-ttu-id="db6fe-107">[!code-cs[csProgGuideDelegates#32](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="db6fe-107">[!code-cs[csProgGuideDelegates#32](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_3.cs)]</span></span>  
  
 <span data-ttu-id="db6fe-108">В C# 2.0 и более поздних версиях можно использовать анонимный метод для объявления и инициализации [делегата](../../../csharp/language-reference/keywords/delegate.md), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="db6fe-108">In C# 2.0 and later, it is also possible to use an anonymous method to declare and initialize a [delegate](../../../csharp/language-reference/keywords/delegate.md), as shown in the following example.</span></span>  
  
 <span data-ttu-id="db6fe-109">[!code-cs[csProgGuideDelegates#15](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="db6fe-109">[!code-cs[csProgGuideDelegates#15](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_4.cs)]</span></span>  
  
 <span data-ttu-id="db6fe-110">В C# 3.0 и более поздних версиях можно объявлять делегаты и создавать для них экземпляры с помощью лямбда-выражения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="db6fe-110">In C# 3.0 and later, delegates can also be declared and instantiated by using a lambda expression, as shown in the following example.</span></span>  
  
 <span data-ttu-id="db6fe-111">[!code-cs[csProgGuideDelegates#31](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="db6fe-111">[!code-cs[csProgGuideDelegates#31](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_5.cs)]</span></span>  
  
 <span data-ttu-id="db6fe-112">Дополнительные сведения см. в разделе [Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="db6fe-112">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="db6fe-113">Следующий пример демонстрирует объявление, создание экземпляра и использование делегата.</span><span class="sxs-lookup"><span data-stu-id="db6fe-113">The following example illustrates declaring, instantiating, and using a delegate.</span></span> <span data-ttu-id="db6fe-114">Класс `BookDB` инкапсулирует базу данных книжного магазина, в которой хранится информация о книгах.</span><span class="sxs-lookup"><span data-stu-id="db6fe-114">The `BookDB` class encapsulates a bookstore database that maintains a database of books.</span></span> <span data-ttu-id="db6fe-115">Он предоставляет метод `ProcessPaperbackBooks`, который находит в базе данных все книги в мягкой обложке и вызывает делегат для каждой из них.</span><span class="sxs-lookup"><span data-stu-id="db6fe-115">It exposes a method, `ProcessPaperbackBooks`, which finds all paperback books in the database and calls a delegate for each one.</span></span> <span data-ttu-id="db6fe-116">Используется тип `delegate` с именем `ProcessBookDelegate`.</span><span class="sxs-lookup"><span data-stu-id="db6fe-116">The `delegate` type that is used is named `ProcessBookDelegate`.</span></span> <span data-ttu-id="db6fe-117">Класс `Test` использует этот класс для печати заголовков и средней цены книг в мягкой обложке.</span><span class="sxs-lookup"><span data-stu-id="db6fe-117">The `Test` class uses this class to print the titles and average price of the paperback books.</span></span>  
  
 <span data-ttu-id="db6fe-118">Использование делегата помогает правильно разделить функции между базой данных книжного магазина и кодом клиента.</span><span class="sxs-lookup"><span data-stu-id="db6fe-118">The use of delegates promotes good separation of functionality between the bookstore database and the client code.</span></span> <span data-ttu-id="db6fe-119">Код клиента не имеет сведений о том, как хранятся книги и как код книжного магазина находит книги в мягкой обложке.</span><span class="sxs-lookup"><span data-stu-id="db6fe-119">The client code has no knowledge of how the books are stored or how the bookstore code finds paperback books.</span></span> <span data-ttu-id="db6fe-120">Код книжного магазина не имеет сведений о том, какая обработка выполняется для найденных книг в мягкой обложке.</span><span class="sxs-lookup"><span data-stu-id="db6fe-120">The bookstore code has no knowledge of what processing is performed on the paperback books after it finds them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db6fe-121">Пример</span><span class="sxs-lookup"><span data-stu-id="db6fe-121">Example</span></span>  
 <span data-ttu-id="db6fe-122">[!code-cs[csProgGuideDelegates#12](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="db6fe-122">[!code-cs[csProgGuideDelegates#12](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_6.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="db6fe-123">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="db6fe-123">Robust Programming</span></span>  
  
-   <span data-ttu-id="db6fe-124">Объявление делегата.</span><span class="sxs-lookup"><span data-stu-id="db6fe-124">Declaring a delegate.</span></span>  
  
     <span data-ttu-id="db6fe-125">Следующая инструкция объявляет новый тип делегата.</span><span class="sxs-lookup"><span data-stu-id="db6fe-125">The following statement declares a new delegate type.</span></span>  
  
     <span data-ttu-id="db6fe-126">[!code-cs[csProgGuideDelegates#16](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="db6fe-126">[!code-cs[csProgGuideDelegates#16](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_7.cs)]</span></span>  
  
     <span data-ttu-id="db6fe-127">Каждый тип делегата описывает количество аргументов и их типы, а также тип возвращаемого значения для всех методов, которые он может инкапсулировать.</span><span class="sxs-lookup"><span data-stu-id="db6fe-127">Each delegate type describes the number and types of the arguments, and the type of the return value of methods that it can encapsulate.</span></span> <span data-ttu-id="db6fe-128">Каждый раз, когда требуется новый набор типов аргументов или новый тип возвращаемого значения, нужно объявить новый тип делегата.</span><span class="sxs-lookup"><span data-stu-id="db6fe-128">Whenever a new set of argument types or return value type is needed, a new delegate type must be declared.</span></span>  
  
-   <span data-ttu-id="db6fe-129">Создания экземпляра делегата.</span><span class="sxs-lookup"><span data-stu-id="db6fe-129">Instantiating a delegate.</span></span>  
  
     <span data-ttu-id="db6fe-130">После объявления типа делегата нужно создать объект этого делегата и связать его с определенным методом.</span><span class="sxs-lookup"><span data-stu-id="db6fe-130">After a delegate type has been declared, a delegate object must be created and associated with a particular method.</span></span> <span data-ttu-id="db6fe-131">Продолжая предыдущий пример, вы можете передать метод `PrintTitle` в метод `ProcessPaperbackBooks`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="db6fe-131">In the previous example, you do this by passing the `PrintTitle` method to the `ProcessPaperbackBooks` method as in the following example:</span></span>  
  
     <span data-ttu-id="db6fe-132">[!code-cs[csProgGuideDelegates#17](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="db6fe-132">[!code-cs[csProgGuideDelegates#17](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_8.cs)]</span></span>  
  
     <span data-ttu-id="db6fe-133">Будет создан новый объект делегата, связанный со [статическим](../../../csharp/language-reference/keywords/static.md) методом `Test.PrintTitle`.</span><span class="sxs-lookup"><span data-stu-id="db6fe-133">This creates a new delegate object associated with the [static](../../../csharp/language-reference/keywords/static.md) method `Test.PrintTitle`.</span></span> <span data-ttu-id="db6fe-134">Аналогичным образом, в следующем примере передается нестатический метод `AddBookToTotal` для объекта `totaller`:</span><span class="sxs-lookup"><span data-stu-id="db6fe-134">Similarly, the non-static method `AddBookToTotal` on the object `totaller` is passed as in the following example:</span></span>  
  
     <span data-ttu-id="db6fe-135">[!code-cs[csProgGuideDelegates#18](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="db6fe-135">[!code-cs[csProgGuideDelegates#18](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_9.cs)]</span></span>  
  
     <span data-ttu-id="db6fe-136">В обоих случаях новый объект делегата передается в метод `ProcessPaperbackBooks`.</span><span class="sxs-lookup"><span data-stu-id="db6fe-136">In both cases a new delegate object is passed to the `ProcessPaperbackBooks` method.</span></span>  
  
     <span data-ttu-id="db6fe-137">После создания делегата невозможно изменить метод, с которым он связан. Объекты делегатов являются неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="db6fe-137">After a delegate is created, the method it is associated with never changes; delegate objects are immutable.</span></span>  
  
-   <span data-ttu-id="db6fe-138">Использование делегатов</span><span class="sxs-lookup"><span data-stu-id="db6fe-138">Calling a delegate.</span></span>  
  
     <span data-ttu-id="db6fe-139">Обычно после создания объекта делегата он передается в другой код, который будет использовать этот делегат.</span><span class="sxs-lookup"><span data-stu-id="db6fe-139">After a delegate object is created, the delegate object is typically passed to other code that will call the delegate.</span></span> <span data-ttu-id="db6fe-140">Для вызова объекта делегата используется имя этого объекта, за которым следуют параметризованные аргументы, которые нужно передать делегату.</span><span class="sxs-lookup"><span data-stu-id="db6fe-140">A delegate object is called by using the name of the delegate object, followed by the parenthesized arguments to be passed to the delegate.</span></span> <span data-ttu-id="db6fe-141">Ниже показан пример использования делегата.</span><span class="sxs-lookup"><span data-stu-id="db6fe-141">Following is an example of a delegate call:</span></span>  
  
     <span data-ttu-id="db6fe-142">[!code-cs[csProgGuideDelegates#19](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="db6fe-142">[!code-cs[csProgGuideDelegates#19](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_10.cs)]</span></span>  
  
     <span data-ttu-id="db6fe-143">Делегат можно вызвать синхронно, как показано в этом примере, или асинхронно при помощи методов `BeginInvoke` и `EndInvoke`.</span><span class="sxs-lookup"><span data-stu-id="db6fe-143">A delegate can be either called synchronously, as in this example, or asynchronously by using `BeginInvoke` and `EndInvoke` methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db6fe-144">См. также</span><span class="sxs-lookup"><span data-stu-id="db6fe-144">See Also</span></span>  
 <span data-ttu-id="db6fe-145">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="db6fe-145">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="db6fe-146">[События](../../../csharp/programming-guide/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="db6fe-146">[Events](../../../csharp/programming-guide/events/index.md) </span></span>  
 [<span data-ttu-id="db6fe-147">Делегаты</span><span class="sxs-lookup"><span data-stu-id="db6fe-147">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)

