---
title: throw (Справочник по C#)
ms.date: 03/02/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- throw
- throw_CSharpKeyword
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
caps.latest.revision: 22
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 088a8e70c5aaaae6f833f12cad1052c30fbb6bfa
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="throw-c-reference"></a><span data-ttu-id="6f467-102">throw (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="6f467-102">throw (C# Reference)</span></span>
<span data-ttu-id="6f467-103">Сообщает о возникновении исключения во время выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="6f467-103">Signals the occurrence of an exception during program execution.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f467-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="6f467-104">Remarks</span></span>

<span data-ttu-id="6f467-105">Синтаксис `throw` выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6f467-105">The syntax of `throw` is:</span></span>

```csharp
throw [e]
```
<span data-ttu-id="6f467-106">где `e` — это экземпляр класса, производного от <xref:System.Exception?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6f467-106">where `e` is an instance of a class derived from <xref:System.Exception?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6f467-107">В следующем примере используется оператор `throw` для создания <xref:System.IndexOutOfRangeException>, если аргумент, переданный в метод с именем `GetNumber`, не соответствует допустимому индексу внутреннего массива.</span><span class="sxs-lookup"><span data-stu-id="6f467-107">The following example uses the `throw` statement to throw an <xref:System.IndexOutOfRangeException> if the argument passed to a method named `GetNumber` does not correspond to a valid index of an internal array.</span></span>

[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]  

<span data-ttu-id="6f467-108">Затем вызывающие объекты метода используют блок `try-catch` или `try-catch-finally` для обработки исключения.</span><span class="sxs-lookup"><span data-stu-id="6f467-108">Method callers then use a `try-catch` or `try-catch-finally` block to handle the thrown exception.</span></span> <span data-ttu-id="6f467-109">В следующем примере показана обработка исключения, созданного методом `GetNumber`.</span><span class="sxs-lookup"><span data-stu-id="6f467-109">The following example handles the exception thrown by the `GetNumber` method.</span></span>

[!code-csharp[csrefKeyword#2](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]  

## <a name="re-throwing-an-exception"></a><span data-ttu-id="6f467-110">Повторное создание исключения</span><span class="sxs-lookup"><span data-stu-id="6f467-110">Re-throwing an exception</span></span>

<span data-ttu-id="6f467-111">`throw` можно также использовать в блоке `catch` для повторного создания исключения, обрабатываемого в блоке `catch`.</span><span class="sxs-lookup"><span data-stu-id="6f467-111">`throw` can also be used in a `catch` block to re-throw an exception handled in a `catch` block.</span></span>  <span data-ttu-id="6f467-112">В этом случае оператор `throw` не принимает операнд исключения.</span><span class="sxs-lookup"><span data-stu-id="6f467-112">In this case, `throw` does not take an exception operand.</span></span> <span data-ttu-id="6f467-113">Это наиболее полезно, когда метод передает аргумент от вызывающего объекта в другой метод библиотеки, а метод библиотеки создает исключение, которое должно быть передано вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="6f467-113">It is most useful when a method passes on an argument from a caller to some other library method, and the library method throws an exception that must be passed on to the caller.</span></span> <span data-ttu-id="6f467-114">Например, в следующем примере повторно создается исключение <xref:System.NullReferenceException>, возникающее при попытке получить первый символ неинициализированной строки.</span><span class="sxs-lookup"><span data-stu-id="6f467-114">For example, the following example re-throws an <xref:System.NullReferenceException> that is thrown when attempting to retrieve the first character of an uninitialized string.</span></span> 

[!code-csharp[csrefKeyword#3](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]  

> [!IMPORTANT]
> <span data-ttu-id="6f467-115">Можно также использовать синтаксис `throw e` в блоке `catch`, чтобы создать исключение, которое будет передано вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="6f467-115">You can also use the `throw e` syntax in a `catch` block to instantiate a new exception that you pass on to the caller.</span></span> <span data-ttu-id="6f467-116">В этом случае трассировка стека исходного исключения, которое доступно из свойства <xref:System.Exception.StackTrace>, не сохраняется.</span><span class="sxs-lookup"><span data-stu-id="6f467-116">In this case, the stack trace of the original exception, which is available from the <xref:System.Exception.StackTrace> property, is not preserved.</span></span>
 
## <a name="the-throw-expression"></a><span data-ttu-id="6f467-117">Выражение `throw`</span><span class="sxs-lookup"><span data-stu-id="6f467-117">The `throw` expression</span></span>

<span data-ttu-id="6f467-118">Начиная с C# 7.0 `throw` можно использовать в качестве выражения, а также как оператор.</span><span class="sxs-lookup"><span data-stu-id="6f467-118">Starting with C# 7.0, `throw` can be used as an expression as well as a statement.</span></span> <span data-ttu-id="6f467-119">Это позволяет вызывать исключения в контекстах, которые ранее не поддерживались.</span><span class="sxs-lookup"><span data-stu-id="6f467-119">This allows an exception to be thrown in contexts that were previously unsupported.</span></span> <span data-ttu-id="6f467-120">Сюда входит следующее.</span><span class="sxs-lookup"><span data-stu-id="6f467-120">These include:</span></span>

- <span data-ttu-id="6f467-121">[Условный оператор](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="6f467-121">[the conditional operator](../operators/conditional-operator.md).</span></span> <span data-ttu-id="6f467-122">В следующем примере используется исключение `throw` для создания <xref:System.ArgumentException>, если методу передается массив пустых строк.</span><span class="sxs-lookup"><span data-stu-id="6f467-122">The following example uses a `throw` expression to throw an <xref:System.ArgumentException> if a method is passed an empty string array.</span></span> <span data-ttu-id="6f467-123">До выхода C# 7.0 эта логика должна была отображаться в операторе `if`/`else`.</span><span class="sxs-lookup"><span data-stu-id="6f467-123">Before C# 7.0, this logic would need to appear in an `if`/`else` statement.</span></span>

   [!code-csharp[csrefKeyword#4](../../../../samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]  
  
- <span data-ttu-id="6f467-124">[Оператор объединения с NULL](../operators/null-conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="6f467-124">[the null-coalescing operator](../operators/null-conditional-operator.md).</span></span> <span data-ttu-id="6f467-125">В следующем примере выражение `throw` используется с оператором, принимающим значение NULL, для создания исключения, если строка, назначенная свойству `Name` является `null`.</span><span class="sxs-lookup"><span data-stu-id="6f467-125">In the following example, a `throw` expression is used with a null-coalescing operator to throw an exception if the string assigned to a `Name` property is `null`.</span></span>
 
   [!code-csharp[csrefKeyword#5](../../../../samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]  
 
- <span data-ttu-id="6f467-126">Метод или [лямбда](../../lambda-expressions.md), воплощающие выражение.</span><span class="sxs-lookup"><span data-stu-id="6f467-126">an expression-bodied [lambda](../../lambda-expressions.md) or method.</span></span> <span data-ttu-id="6f467-127">В следующем примере показан метод, воплощающий выражение, который создает <xref:System.InvalidCastException>, так как преобразование в значение <xref:System.DateTime> не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="6f467-127">The following example illustrates an expression-bodied method that throws an <xref:System.InvalidCastException> because a conversion to a <xref:System.DateTime> value is not supported.</span></span>
 
   [!code-csharp[csrefKeyword#6](../../../../samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]  
 
  
## <a name="c-language-specification"></a><span data-ttu-id="6f467-128">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="6f467-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6f467-129">См. также</span><span class="sxs-lookup"><span data-stu-id="6f467-129">See Also</span></span>  
 [<span data-ttu-id="6f467-130">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="6f467-130">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6f467-131">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6f467-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6f467-132">try-catch</span><span class="sxs-lookup"><span data-stu-id="6f467-132">try-catch</span></span>](../../../csharp/language-reference/keywords/try-catch.md)  
 [<span data-ttu-id="6f467-133">Операторы try, catch и throw в C++</span><span class="sxs-lookup"><span data-stu-id="6f467-133">The try, catch, and throw Statements in C++</span></span>](../../../csharp/language-reference/keywords/try-catch.md)  
 [<span data-ttu-id="6f467-134">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="6f467-134">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="6f467-135">Операторы обработки исключений</span><span class="sxs-lookup"><span data-stu-id="6f467-135">Exception Handling Statements</span></span>](../../../csharp/language-reference/keywords/exception-handling-statements.md)  
 [<span data-ttu-id="6f467-136">Практическое руководство. Явное создание исключений</span><span class="sxs-lookup"><span data-stu-id="6f467-136">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
