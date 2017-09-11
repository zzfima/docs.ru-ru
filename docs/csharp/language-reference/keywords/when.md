---
title: "when (справочник по C#)"
ms.date: 2017-03-07
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- when_CSharpKeyword
- when
dev_langs:
- CSharp
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
caps.latest.revision: 30
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
ms.sourcegitcommit: 9ad2eff6eb527f00ce23f463e811aa748def62d0
ms.openlocfilehash: c391c6de51d41577d61278f43d58fade5b7c139f
ms.contentlocale: ru-ru
ms.lasthandoff: 08/11/2017

---
 # <a name="when-c-reference"></a><span data-ttu-id="fbef7-102">when (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="fbef7-102">when (C# Reference)</span></span>

<span data-ttu-id="fbef7-103">Для того чтобы указать условие фильтра в двух контекстах, можно использовать контекстно-зависимое ключевое слово `when`.</span><span class="sxs-lookup"><span data-stu-id="fbef7-103">You can use the `when` contextual keyword to specify a filter condition in two contexts:</span></span>

- <span data-ttu-id="fbef7-104">В операторе `catch` блока [try/catch](try-catch.md) или [try/catch/finally](try-catch-finally.md).</span><span class="sxs-lookup"><span data-stu-id="fbef7-104">In the `catch` statement of a [try/catch](try-catch.md) or [try/catch/finally](try-catch-finally.md) block.</span></span>
- <span data-ttu-id="fbef7-105">В метке `case` оператора [switch](switch.md).</span><span class="sxs-lookup"><span data-stu-id="fbef7-105">In the `case` label of a [switch](switch.md) statement.</span></span>

## <a name="when-in-a-catch-statement"></a><span data-ttu-id="fbef7-106">`when` в операторе `catch`</span><span class="sxs-lookup"><span data-stu-id="fbef7-106">`when` in a `catch` statement</span></span>

<span data-ttu-id="fbef7-107">Начиная с C# версии 6, `When` можно использовать в операторе `catch`, чтобы задать условие, которое должно быть истинным для выполнения обработчика определенного исключения.</span><span class="sxs-lookup"><span data-stu-id="fbef7-107">Starting with C# 6, `When` can be used in a `catch` statement to specify a condition that must be true for the handler for a specific exception to execute.</span></span> <span data-ttu-id="fbef7-108">Он имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="fbef7-108">Its syntax is:</span></span>

```csharp
catch ExceptionType [e] when (expr)
```
<span data-ttu-id="fbef7-109">здесь *expr* представляет собой выражение, которое оценивает значение типа Boolean.</span><span class="sxs-lookup"><span data-stu-id="fbef7-109">where *expr* is an expression that evaluates to a Boolean value.</span></span> <span data-ttu-id="fbef7-110">Если он возвращает `true`, обработчик исключений выполняется, а если `false`, то нет.</span><span class="sxs-lookup"><span data-stu-id="fbef7-110">If it returns `true`, the exception handler executes; if `false`, it does not.</span></span> 

<span data-ttu-id="fbef7-111">В следующем примере используется ключевое слово `when`, которое позволяет условно выполнять обработчики для @System.Net.HttpRequestException в зависимости от того, какой текст содержит сообщение об исключении.</span><span class="sxs-lookup"><span data-stu-id="fbef7-111">The following example uses the `when` keyword to conditionally execute handlers for an @System.Net.HttpRequestException depending on the text of the exception message.</span></span>

 <span data-ttu-id="fbef7-112">[!code-cs[when-with-catch](../../../../samples/snippets/csharp/language-reference/keywords/when/catch.cs)]</span><span class="sxs-lookup"><span data-stu-id="fbef7-112">[!code-cs[when-with-catch](../../../../samples/snippets/csharp/language-reference/keywords/when/catch.cs)]</span></span>  
  
## <a name="when-in-a-switch-statement"></a><span data-ttu-id="fbef7-113">`when` в операторе `switch`</span><span class="sxs-lookup"><span data-stu-id="fbef7-113">`when` in a `switch` statement</span></span>

<span data-ttu-id="fbef7-114">Начиная с версии 7, метки `case` больше не должны быть взаимоисключающими, а порядок отображения меток `case` в операторе `switch` может определять, какие блоки switch должны быть выполнены.</span><span class="sxs-lookup"><span data-stu-id="fbef7-114">Starting with 7, `case` labels no longer need be mutually exclusive, and the order in which `case` labels appear in a `switch` statement can determine which switch block executes.</span></span> <span data-ttu-id="fbef7-115">Ключевое слово `when` позволяет задать условие фильтра, при котором соответствующая метка case будет иметь значение true, только если условие фильтра также имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="fbef7-115">The `when` keyword can be used to specify a filter condition that causes its associated case label to be true only if the filter condition is also true.</span></span> <span data-ttu-id="fbef7-116">Он имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="fbef7-116">Its syntax is:</span></span>

```csharp
case (expr) when (when-condition):
```
<span data-ttu-id="fbef7-117">здесь *expr* является постоянным шаблоном или типом шаблона, который сравнивается с соответствующим выражением, а *условие when* представляет собой любое логическое выражение.</span><span class="sxs-lookup"><span data-stu-id="fbef7-117">where *expr* is a constant pattern or type pattern that is compared to the match expression, and *when-condition* is any Boolean expression.</span></span> 

<span data-ttu-id="fbef7-118">В следующем примере ключевое слово `when` используется для проверки объектов `Shape`, которые имеют нулевую область, а также для проверки различных объектов `Shape` с областью больше нуля.</span><span class="sxs-lookup"><span data-stu-id="fbef7-118">The following example uses the `when` keyword to test for `Shape` objects that have an area of zero, as well as to test for a variety of `Shape` objects that have an area greater than zero.</span></span> 

 <span data-ttu-id="fbef7-119">[!code-cs[when-with-case#1](../../../../samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="fbef7-119">[!code-cs[when-with-case#1](../../../../samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="fbef7-120">См. также</span><span class="sxs-lookup"><span data-stu-id="fbef7-120">See also</span></span> 
  [<span data-ttu-id="fbef7-121">Оператор switch</span><span class="sxs-lookup"><span data-stu-id="fbef7-121">switch statement</span></span>](switch.md)  
  [<span data-ttu-id="fbef7-122">Оператор try-catch</span><span class="sxs-lookup"><span data-stu-id="fbef7-122">try/catch statement</span></span>](try-catch.md)  
  [<span data-ttu-id="fbef7-123">Оператор try/catch/finally</span><span class="sxs-lookup"><span data-stu-id="fbef7-123">try/catch/finally statement</span></span>](try-catch-finally.md) 


