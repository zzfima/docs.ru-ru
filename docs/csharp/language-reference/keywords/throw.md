---
title: "throw (Справочник по C#)"
ms.date: 2015-03-02
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- throw
- throw_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
caps.latest.revision: 22
author: rpetrusha
ms.author: ronpet
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
ms.openlocfilehash: 955f6d87614e0b452ace162e79e34aec9decad54
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="throw-c-reference"></a><span data-ttu-id="f5672-102">throw (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f5672-102">throw (C# Reference)</span></span>
<span data-ttu-id="f5672-103">Сообщает о возникновении исключения во время выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="f5672-103">Signals the occurrence of an exception during program execution.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5672-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="f5672-104">Remarks</span></span>

<span data-ttu-id="f5672-105">Синтаксис `throw` выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f5672-105">The syntax of `throw` is:</span></span>

```csharp
throw [e]
```
<span data-ttu-id="f5672-106">где `e` — это экземпляр класса, производного от <xref:System.Exception?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="f5672-106">where `e` is an instance of a class derived from <xref:System.Exception?displayProperty=fullName>.</span></span> <span data-ttu-id="f5672-107">В следующем примере используется оператор `throw` для создания @System.IndexOutOfRangeException, если аргумент, переданный в метод с именем `GetNumber`, не соответствует допустимому индексу внутреннего массива.</span><span class="sxs-lookup"><span data-stu-id="f5672-107">The following example uses the `throw` statement to throw an @System.IndexOutOfRangeException if the argument passed to a method named `GetNumber` does not correspond to a valid index of an internal array.</span></span>

<span data-ttu-id="f5672-108">[!code-cs[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="f5672-108">[!code-cs[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]</span></span>  

<span data-ttu-id="f5672-109">Затем вызывающие объекты метода используют блок `try-catch` или `try-catch-finally` для обработки исключения.</span><span class="sxs-lookup"><span data-stu-id="f5672-109">Method callers then use a `try-catch` or `try-catch-finally` block to handle the thrown exception.</span></span> <span data-ttu-id="f5672-110">В следующем примере показана обработка исключения, созданного методом `GetNumber`.</span><span class="sxs-lookup"><span data-stu-id="f5672-110">The following example handles the exception thrown by the `GetNumber` method.</span></span>

<span data-ttu-id="f5672-111">[!code-cs[csrefKeyword#2](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="f5672-111">[!code-cs[csrefKeyword#2](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]</span></span>  

## <a name="re-throwing-an-exception"></a><span data-ttu-id="f5672-112">Повторное создание исключения</span><span class="sxs-lookup"><span data-stu-id="f5672-112">Re-throwing an exception</span></span>

<span data-ttu-id="f5672-113">`throw` можно также использовать в блоке `catch` для повторного создания исключения, обрабатываемого в блоке `catch`.</span><span class="sxs-lookup"><span data-stu-id="f5672-113">`throw` can also be used in a `catch` block to re-throw an exception handled in a `catch` block.</span></span>  <span data-ttu-id="f5672-114">В этом случае оператор `throw` не принимает операнд исключения.</span><span class="sxs-lookup"><span data-stu-id="f5672-114">In this case, `throw` does not take an exception operand.</span></span> <span data-ttu-id="f5672-115">Это наиболее полезно, когда метод передает аргумент от вызывающего объекта в другой метод библиотеки, а метод библиотеки создает исключение, которое должно быть передано вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="f5672-115">It is most useful when a method passes on an argument from a caller to some other library method, and the library method throws an exception that must be passed on to the caller.</span></span> <span data-ttu-id="f5672-116">Например, в следующем примере повторно создается исключение @System.NullReferenceException, возникающее при попытке получить первый символ неинициализированной строки.</span><span class="sxs-lookup"><span data-stu-id="f5672-116">For example, the following example re-throws an @System.NullReferenceException that is thrown when attempting to retrieve the first character of an uninitialized string.</span></span> 

<span data-ttu-id="f5672-117">[!code-cs[csrefKeyword#3](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]</span><span class="sxs-lookup"><span data-stu-id="f5672-117">[!code-cs[csrefKeyword#3](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="f5672-118">Можно также использовать синтаксис `throw e` в блоке `catch`, чтобы создать исключение, которое будет передано вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="f5672-118">You can also use the `throw e` syntax in a `catch` block to instantiate a new exception that you pass on to the caller.</span></span> <span data-ttu-id="f5672-119">В этом случае трассировка стека исходного исключения, которое доступно из свойства @System.Exception.Stacktrace, не сохраняется.</span><span class="sxs-lookup"><span data-stu-id="f5672-119">In this case, the stack trace of the original exception, which is available from the @System.Exception.Stacktrace property, is not preserved.</span></span>
 
## <a name="the-throw-expression"></a><span data-ttu-id="f5672-120">Выражение `throw`</span><span class="sxs-lookup"><span data-stu-id="f5672-120">The `throw` expression</span></span>

<span data-ttu-id="f5672-121">Начиная с C# 7 `throw` можно использовать в качестве выражения, а также как оператор.</span><span class="sxs-lookup"><span data-stu-id="f5672-121">Starting with C# 7, `throw` can be used as an expression as well as a statement.</span></span> <span data-ttu-id="f5672-122">Это позволяет вызывать исключения в контекстах, которые ранее не поддерживались.</span><span class="sxs-lookup"><span data-stu-id="f5672-122">This allows an exception to be thrown in contexts that were previously unsupported.</span></span> <span data-ttu-id="f5672-123">Сюда входит следующее.</span><span class="sxs-lookup"><span data-stu-id="f5672-123">These include:</span></span>

- <span data-ttu-id="f5672-124">[Условный оператор](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="f5672-124">[the conditional operator](../operators/conditional-operator.md).</span></span> <span data-ttu-id="f5672-125">В следующем примере используется исключение `throw` для создания @System.ArgumentException, если методу передается массив пустых строк.</span><span class="sxs-lookup"><span data-stu-id="f5672-125">The following example uses a `throw` expression to throw an @System.ArgumentException if a method is passed an empty string array.</span></span> <span data-ttu-id="f5672-126">До выхода C# 7 эта логика должна была отображаться в инструкции `if`/`else`.</span><span class="sxs-lookup"><span data-stu-id="f5672-126">Before C# 7, this logic would need to appear in an `if`/`else` statement.</span></span>

   <span data-ttu-id="f5672-127">[!code-cs[csrefKeyword#4](../../../../samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="f5672-127">[!code-cs[csrefKeyword#4](../../../../samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]</span></span>  
  
- <span data-ttu-id="f5672-128">[Оператор объединения с NULL](../operators/null-conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="f5672-128">[the null-coalescing operator](../operators/null-conditional-operator.md).</span></span> <span data-ttu-id="f5672-129">В следующем примере выражение `throw` используется с оператором, принимающим значение NULL, для создания исключения, если строка, назначенная свойству `Name` является `null`.</span><span class="sxs-lookup"><span data-stu-id="f5672-129">In the following example, a `throw` expression is used with a null-coalescing operator to throw an exception if the string assigned to a `Name` property is `null`.</span></span>
 
   <span data-ttu-id="f5672-130">[!code-cs[csrefKeyword#5](../../../../samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="f5672-130">[!code-cs[csrefKeyword#5](../../../../samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]</span></span>  
 
- <span data-ttu-id="f5672-131">Метод или [лямбда](../../lambda-expressions.md), воплощающие выражение.</span><span class="sxs-lookup"><span data-stu-id="f5672-131">an expression-bodied [lambda](../../lambda-expressions.md) or method.</span></span> <span data-ttu-id="f5672-132">В следующем примере показан метод, воплощающий выражение, который создает @System.InvalidCastException, так как преобразование в значение @System.DateTime не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f5672-132">The following example illustrates an expression-bodied method that throws an @System.InvalidCastException because a conversion to a @System.DateTime value is not supported.</span></span>
 
   <span data-ttu-id="f5672-133">[!code-cs[csrefKeyword#6](../../../../samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="f5672-133">[!code-cs[csrefKeyword#6](../../../../samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]</span></span>  
 
  
## <a name="c-language-specification"></a><span data-ttu-id="f5672-134">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f5672-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f5672-135">См. также</span><span class="sxs-lookup"><span data-stu-id="f5672-135">See Also</span></span>  
 <span data-ttu-id="f5672-136">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f5672-136">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f5672-137">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f5672-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f5672-138">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="f5672-138">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 <span data-ttu-id="f5672-139">[Операторы try, catch и throw в C++](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="f5672-139">[The try, catch, and throw Statements in C++](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 <span data-ttu-id="f5672-140">[Ключевые слова C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="f5672-140">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="f5672-141">[Операторы обработки исключений](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span><span class="sxs-lookup"><span data-stu-id="f5672-141">[Exception Handling Statements](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span></span>  
 [<span data-ttu-id="f5672-142">Практическое руководство. Явное создание исключений</span><span class="sxs-lookup"><span data-stu-id="f5672-142">How to: Explicitly Throw Exceptions</span></span>](https://msdn.microsoft.com/library/xhcbs8fz)

