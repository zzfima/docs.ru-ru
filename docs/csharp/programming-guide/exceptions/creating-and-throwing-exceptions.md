---
title: "Создание и генерация исключений (Руководство по программированию C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- catching exceptions [C#]
- throwing exceptions [C#]
- exceptions [C#], creating
- exceptions [C#], throwing
ms.assetid: 6bbba495-a115-4c6d-90cc-1f4d7b5f39e2
caps.latest.revision: 28
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
ms.openlocfilehash: 5f49b0911aa94480988987f209bc73d187451620
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="creating-and-throwing-exceptions-c-programming-guide"></a><span data-ttu-id="31a6d-102">Создание и генерация исключений (Руководство по программированию C#)</span><span class="sxs-lookup"><span data-stu-id="31a6d-102">Creating and Throwing Exceptions (C# Programming Guide)</span></span>
<span data-ttu-id="31a6d-103">Исключения позволяют обозначить, что во время выполнения программы произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="31a6d-103">Exceptions are used to indicate that an error has occurred while running the program.</span></span> <span data-ttu-id="31a6d-104">Объекты исключений, описывающие ошибку, создаются и затем *вызываются* с помощью ключевого слова [throw](../../../csharp/language-reference/keywords/throw.md).</span><span class="sxs-lookup"><span data-stu-id="31a6d-104">Exception objects that describe an error are created and then *thrown* with the [throw](../../../csharp/language-reference/keywords/throw.md) keyword.</span></span> <span data-ttu-id="31a6d-105">Далее среда выполнения ищет наиболее совместимый обработчик исключений.</span><span class="sxs-lookup"><span data-stu-id="31a6d-105">The runtime then searches for the most compatible exception handler.</span></span>  
  
 <span data-ttu-id="31a6d-106">Программисты должны вызывать исключения при выполнении одного или нескольких из перечисленных ниже условий.</span><span class="sxs-lookup"><span data-stu-id="31a6d-106">Programmers should throw exceptions when one or more of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="31a6d-107">Метод не способен выполнить свои функции.</span><span class="sxs-lookup"><span data-stu-id="31a6d-107">The method cannot complete its defined functionality.</span></span>  
  
     <span data-ttu-id="31a6d-108">Например, если значение параметра метода является недопустимым:</span><span class="sxs-lookup"><span data-stu-id="31a6d-108">For example, if a parameter to a method has an invalid value:</span></span>  
  
     <span data-ttu-id="31a6d-109">[!code-cs[csProgGuideExceptions#12](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="31a6d-109">[!code-cs[csProgGuideExceptions#12](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_1.cs)]</span></span>  
  
-   <span data-ttu-id="31a6d-110">На основе состояния объекта выполнен неправильный вызов объекта.</span><span class="sxs-lookup"><span data-stu-id="31a6d-110">An inappropriate call to an object is made, based on the object state.</span></span>  
  
     <span data-ttu-id="31a6d-111">В качестве примера можно привести попытку записи в файл, доступный только для чтения.</span><span class="sxs-lookup"><span data-stu-id="31a6d-111">One example might be trying to write to a read-only file.</span></span> <span data-ttu-id="31a6d-112">В случаях, когда состояние объекта не допускает выполнения операции, вызывается экземпляр <xref:System.InvalidOperationException> или объекта на основе наследования этого класса.</span><span class="sxs-lookup"><span data-stu-id="31a6d-112">In cases where an object state does not allow an operation, throw an instance of <xref:System.InvalidOperationException> or an object based on a derivation of this class.</span></span> <span data-ttu-id="31a6d-113">Ниже приведен пример метода, который вызывает объект <xref:System.InvalidOperationException>:</span><span class="sxs-lookup"><span data-stu-id="31a6d-113">This is an example of a method that throws an <xref:System.InvalidOperationException> object:</span></span>  
  
     <span data-ttu-id="31a6d-114">[!code-cs[csProgGuideExceptions#13](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="31a6d-114">[!code-cs[csProgGuideExceptions#13](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_2.cs)]</span></span>  
  
-   <span data-ttu-id="31a6d-115">Когда аргумент метода вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="31a6d-115">When an argument to a method causes an exception.</span></span>  
  
     <span data-ttu-id="31a6d-116">В этом случае должно быть перехвачено исходное исключение и создан экземпляр <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="31a6d-116">In this case, the original exception should be caught and an <xref:System.ArgumentException> instance should be created.</span></span> <span data-ttu-id="31a6d-117">Исходное исключение должно передаваться конструктору <xref:System.ArgumentException> в качестве параметра <xref:System.Exception.InnerException%2A>:</span><span class="sxs-lookup"><span data-stu-id="31a6d-117">The original exception should be passed to the constructor of the <xref:System.ArgumentException> as the <xref:System.Exception.InnerException%2A> parameter:</span></span>  
  
     <span data-ttu-id="31a6d-118">[!code-cs[csProgGuideExceptions#14](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="31a6d-118">[!code-cs[csProgGuideExceptions#14](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_3.cs)]</span></span>  
  
 <span data-ttu-id="31a6d-119">Исключения содержат свойство с именем <xref:System.Exception.StackTrace%2A>.</span><span class="sxs-lookup"><span data-stu-id="31a6d-119">Exceptions contain a property named <xref:System.Exception.StackTrace%2A>.</span></span> <span data-ttu-id="31a6d-120">Строка содержит имена методов в текущем стеке вызовов вместе с именем файла и номером строки, в которой было вызвано исключение для каждого метода.</span><span class="sxs-lookup"><span data-stu-id="31a6d-120">This string contains the name of the methods on the current call stack, together with the file name and line number where the exception was thrown for each method.</span></span> <span data-ttu-id="31a6d-121">Объект <xref:System.Exception.StackTrace%2A> создается автоматически средой CLR из точки оператора `throw`, так что исключения должны вызываться из той точки, где должна начинаться трассировка стека.</span><span class="sxs-lookup"><span data-stu-id="31a6d-121">A <xref:System.Exception.StackTrace%2A> object is created automatically by the common language runtime (CLR) from the point of the `throw` statement, so that exceptions must be thrown from the point where the stack trace should begin.</span></span>  
  
 <span data-ttu-id="31a6d-122">Все исключения содержат свойство с именем <xref:System.Exception.Message%2A>.</span><span class="sxs-lookup"><span data-stu-id="31a6d-122">All exceptions contain a property named <xref:System.Exception.Message%2A>.</span></span> <span data-ttu-id="31a6d-123">Эта строка должна содержать сообщение с объяснением причины исключения.</span><span class="sxs-lookup"><span data-stu-id="31a6d-123">This string should be set to explain the reason for the exception.</span></span> <span data-ttu-id="31a6d-124">Обратите внимание, что важные с точки зрения безопасности сведения не следует помещать в текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="31a6d-124">Note that information that is sensitive to security should not be put in the message text.</span></span> <span data-ttu-id="31a6d-125">Помимо <xref:System.Exception.Message%2A>, <xref:System.ArgumentException> содержит свойство с именем <xref:System.ArgumentException.ParamName%2A>, которому должно присваиваться имя аргумента, ставшего причиной возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="31a6d-125">In addition to <xref:System.Exception.Message%2A>, <xref:System.ArgumentException> contains a property named <xref:System.ArgumentException.ParamName%2A> that should be set to the name of the argument that caused the exception to be thrown.</span></span> <span data-ttu-id="31a6d-126">Для метода задания свойства <xref:System.ArgumentException.ParamName%2A> должно получать значение `value`.</span><span class="sxs-lookup"><span data-stu-id="31a6d-126">In the case of a property setter, <xref:System.ArgumentException.ParamName%2A> should be set to `value`.</span></span>  
  
 <span data-ttu-id="31a6d-127">Члены открытых и защищенных методов должны вызывать исключения каждый раз, когда не удается выполнить назначенные им функции.</span><span class="sxs-lookup"><span data-stu-id="31a6d-127">Public and protected methods members should throw exceptions whenever they cannot complete their intended functions.</span></span> <span data-ttu-id="31a6d-128">Вызываемый класс исключения должен быть самым конкретным доступным исключением, удовлетворяющим условиям ошибки.</span><span class="sxs-lookup"><span data-stu-id="31a6d-128">The exception class that is thrown should be the most specific exception available that fits the error conditions.</span></span> <span data-ttu-id="31a6d-129">Эти исключения должны документироваться в составе функций класса, а производные классы или обновления исходного класса должны сохранять то же поведение для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="31a6d-129">These exceptions should be documented as part of the class functionality, and derived classes or updates to the original class should retain the same behavior for backward compatibility.</span></span>  
  
## <a name="things-to-avoid-when-throwing-exceptions"></a><span data-ttu-id="31a6d-130">Чего следует избегать при вызове исключений</span><span class="sxs-lookup"><span data-stu-id="31a6d-130">Things to Avoid When Throwing Exceptions</span></span>  
 <span data-ttu-id="31a6d-131">Ниже приводятся рекомендации по тому, чего следует избегать при вызове исключений.</span><span class="sxs-lookup"><span data-stu-id="31a6d-131">The following list identifies practices to avoid when throwing exceptions:</span></span>  
  
-   <span data-ttu-id="31a6d-132">Исключения не рекомендуется использовать для изменения потока программы в рамках обычного выполнения.</span><span class="sxs-lookup"><span data-stu-id="31a6d-132">Exceptions should not be used to change the flow of a program as part of ordinary execution.</span></span> <span data-ttu-id="31a6d-133">Исключения следует использовать только для сообщения о состояниях ошибки и их обработки.</span><span class="sxs-lookup"><span data-stu-id="31a6d-133">Exceptions should only be used to report and handle error conditions.</span></span>  
  
-   <span data-ttu-id="31a6d-134">Исключения должны генерироваться, а не возвращаться в качестве возвращаемого значения или параметра.</span><span class="sxs-lookup"><span data-stu-id="31a6d-134">Exceptions should not be returned as a return value or parameter instead of being thrown.</span></span>  
  
-   <span data-ttu-id="31a6d-135">Не следует вызывать <xref:System.Exception?displayProperty=fullName>, <xref:System.SystemException?displayProperty=fullName>, <xref:System.NullReferenceException?displayProperty=fullName> или <xref:System.IndexOutOfRangeException?displayProperty=fullName> из собственного исходного кода намеренно.</span><span class="sxs-lookup"><span data-stu-id="31a6d-135">Do not throw <xref:System.Exception?displayProperty=fullName>, <xref:System.SystemException?displayProperty=fullName>, <xref:System.NullReferenceException?displayProperty=fullName>, or <xref:System.IndexOutOfRangeException?displayProperty=fullName> intentionally from your own source code.</span></span>  
  
-   <span data-ttu-id="31a6d-136">Не рекомендуется создавать исключения, которые могут вызываться в режиме отладки, а не в режиме выпуска.</span><span class="sxs-lookup"><span data-stu-id="31a6d-136">Do not create exceptions that can be thrown in debug mode but not release mode.</span></span> <span data-ttu-id="31a6d-137">Чтобы определить ошибки времени выполнения на этапе разработки, используйте Debug Assert.</span><span class="sxs-lookup"><span data-stu-id="31a6d-137">To identify run-time errors during the development phase, use Debug Assert instead.</span></span>  
  
## <a name="defining-exception-classes"></a><span data-ttu-id="31a6d-138">Определение классов исключений</span><span class="sxs-lookup"><span data-stu-id="31a6d-138">Defining Exception Classes</span></span>  
 <span data-ttu-id="31a6d-139">Программы могут вызывать предопределенный класс исключений в пространстве имен <xref:System> (кроме указанных ранее случаев) или создавать собственные классы исключений путем наследования от <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="31a6d-139">Programs can throw a predefined exception class in the <xref:System> namespace (except where previously noted), or create their own exception classes by deriving from <xref:System.Exception>.</span></span> <span data-ttu-id="31a6d-140">Производные классы должны определять по крайней мере четыре конструктора: один конструктор по умолчанию, один конструктор, задающий свойство сообщения, и еще один, задающий свойства <xref:System.Exception.Message%2A> и <xref:System.Exception.InnerException%2A>.</span><span class="sxs-lookup"><span data-stu-id="31a6d-140">The derived classes should define at least four constructors: one default constructor, one that sets the message property, and one that sets both the <xref:System.Exception.Message%2A> and <xref:System.Exception.InnerException%2A> properties.</span></span> <span data-ttu-id="31a6d-141">Четвертый конструктор служит для сериализации исключения.</span><span class="sxs-lookup"><span data-stu-id="31a6d-141">The fourth constructor is used to serialize the exception.</span></span> <span data-ttu-id="31a6d-142">Новые классы исключений должны быть сериализуемыми.</span><span class="sxs-lookup"><span data-stu-id="31a6d-142">New exception classes should be serializable.</span></span> <span data-ttu-id="31a6d-143">Пример:</span><span class="sxs-lookup"><span data-stu-id="31a6d-143">For example:</span></span>  
  
 <span data-ttu-id="31a6d-144">[!code-cs[csProgGuideExceptions#15](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="31a6d-144">[!code-cs[csProgGuideExceptions#15](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_4.cs)]</span></span>  
  
 <span data-ttu-id="31a6d-145">Новые свойства следует добавлять к классу исключений только в том случае, если данные в них могут помочь в разрешении исключения.</span><span class="sxs-lookup"><span data-stu-id="31a6d-145">New properties should only be added to the exception class when the data they provide is useful to resolving the exception.</span></span> <span data-ttu-id="31a6d-146">При добавлении новых свойств в производный класс исключений метод `ToString()` необходимо переопределить так, чтобы он возвращал добавленные сведения.</span><span class="sxs-lookup"><span data-stu-id="31a6d-146">If new properties are added to the derived exception class, `ToString()` should be overridden to return the added information.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="31a6d-147">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="31a6d-147">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="31a6d-148">См. также</span><span class="sxs-lookup"><span data-stu-id="31a6d-148">See Also</span></span>  
 <span data-ttu-id="31a6d-149">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="31a6d-149">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="31a6d-150">[Исключения и обработка исключений](../../../csharp/programming-guide/exceptions/index.md) </span><span class="sxs-lookup"><span data-stu-id="31a6d-150">[Exceptions and Exception Handling](../../../csharp/programming-guide/exceptions/index.md) </span></span>  
 <span data-ttu-id="31a6d-151">[Иерархия исключений](http://msdn.microsoft.com/library/f7d68675-be06-40fb-a555-05f0c5a6f66b) </span><span class="sxs-lookup"><span data-stu-id="31a6d-151">[Exception Hierarchy](http://msdn.microsoft.com/library/f7d68675-be06-40fb-a555-05f0c5a6f66b) </span></span>  
 [<span data-ttu-id="31a6d-152">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="31a6d-152">Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/exception-handling.md)

