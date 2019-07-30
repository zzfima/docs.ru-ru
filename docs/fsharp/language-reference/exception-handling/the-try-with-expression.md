---
title: Исключения. Выражение try…with
description: Узнайте, F# как использовать оператор "try... With ' выражение для обработки исключений.
ms.date: 05/16/2016
ms.openlocfilehash: e4d615086a93e26b76cca460e797659ca13792b5
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630246"
---
# <a name="exceptions-the-trywith-expression"></a><span data-ttu-id="a4e72-103">Исключения. Выражение try…with</span><span class="sxs-lookup"><span data-stu-id="a4e72-103">Exceptions: The try...with Expression</span></span>

<span data-ttu-id="a4e72-104">В этом разделе описывается `try...with` выражение, которое используется для обработки исключений в F# языке.</span><span class="sxs-lookup"><span data-stu-id="a4e72-104">This topic describes the `try...with` expression, the expression that is used for exception handling in the F# language.</span></span>

## <a name="syntax"></a><span data-ttu-id="a4e72-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a4e72-105">Syntax</span></span>

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a><span data-ttu-id="a4e72-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="a4e72-106">Remarks</span></span>

<span data-ttu-id="a4e72-107">Выражение используется для управления исключениями в F# `try...with`</span><span class="sxs-lookup"><span data-stu-id="a4e72-107">The `try...with` expression is used to handle exceptions in F#.</span></span> <span data-ttu-id="a4e72-108">Он аналогичен `try...catch` оператору в C#.</span><span class="sxs-lookup"><span data-stu-id="a4e72-108">It is similar to the `try...catch` statement in C#.</span></span> <span data-ttu-id="a4e72-109">В приведенном выше синтаксисе код в *expression1* может вызвать исключение.</span><span class="sxs-lookup"><span data-stu-id="a4e72-109">In the preceding syntax, the code in *expression1* might generate an exception.</span></span> <span data-ttu-id="a4e72-110">`try...with` Выражение возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="a4e72-110">The `try...with` expression returns a value.</span></span> <span data-ttu-id="a4e72-111">Если исключение не создается, выражение целиком возвращает значение *expression1*.</span><span class="sxs-lookup"><span data-stu-id="a4e72-111">If no exception is thrown, the whole expression returns the value of *expression1*.</span></span> <span data-ttu-id="a4e72-112">При возникновении исключения каждый *шаблон* сравнивается, в свою очередь, с исключением, а для первого совпадающего шаблона соответствующее *выражение*, известное как *обработчик исключений*для этой ветви, выполняется, а общее выражение Возвращает значение выражения в этом обработчике исключений.</span><span class="sxs-lookup"><span data-stu-id="a4e72-112">If an exception is thrown, each *pattern* is compared in turn with the exception, and for the first matching pattern, the corresponding *expression*, known as the *exception handler*, for that branch is executed, and the overall expression returns the value of the expression in that exception handler.</span></span> <span data-ttu-id="a4e72-113">Если шаблон не соответствует, исключение распространяет стек вызовов до тех пор, пока не будет найден соответствующий обработчик.</span><span class="sxs-lookup"><span data-stu-id="a4e72-113">If no pattern matches, the exception propagates up the call stack until a matching handler is found.</span></span> <span data-ttu-id="a4e72-114">Типы значений, возвращаемых каждым выражением в обработчиках исключений, должны соответствовать типу, возвращаемому из выражения в `try` блоке.</span><span class="sxs-lookup"><span data-stu-id="a4e72-114">The types of the values returned from each expression in the exception handlers must match the type returned from the expression in the `try` block.</span></span>

<span data-ttu-id="a4e72-115">Как правило, возникновение ошибки также означает, что нет допустимого значения, которое может быть возвращено из выражений в каждом обработчике исключений.</span><span class="sxs-lookup"><span data-stu-id="a4e72-115">Frequently, the fact that an error occurred also means that there is no valid value that can be returned from the expressions in each exception handler.</span></span> <span data-ttu-id="a4e72-116">Часто шаблоном является то, что тип выражения должен быть типом параметра.</span><span class="sxs-lookup"><span data-stu-id="a4e72-116">A frequent pattern is to have the type of the expression be an option type.</span></span> <span data-ttu-id="a4e72-117">Этот шаблон показан в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="a4e72-117">The following code example illustrates this pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

<span data-ttu-id="a4e72-118">Исключения могут быть исключениями .NET, или они могут F# быть исключениями.</span><span class="sxs-lookup"><span data-stu-id="a4e72-118">Exceptions can be .NET exceptions, or they can be F# exceptions.</span></span> <span data-ttu-id="a4e72-119">Исключения можно определить F# с помощью `exception` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="a4e72-119">You can define F# exceptions by using the `exception` keyword.</span></span>

<span data-ttu-id="a4e72-120">Для фильтрации по типу исключения и другим условиям можно использовать разнообразные шаблоны. параметры приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a4e72-120">You can use a variety of patterns to filter on the exception type and other conditions; the options are summarized in the following table.</span></span>

|<span data-ttu-id="a4e72-121">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4e72-121">Pattern</span></span>|<span data-ttu-id="a4e72-122">Описание</span><span class="sxs-lookup"><span data-stu-id="a4e72-122">Description</span></span>|
|-------|-----------|
|<span data-ttu-id="a4e72-123">:?</span><span class="sxs-lookup"><span data-stu-id="a4e72-123">:?</span></span> <span data-ttu-id="a4e72-124">*тип исключения*</span><span class="sxs-lookup"><span data-stu-id="a4e72-124">*exception-type*</span></span>|<span data-ttu-id="a4e72-125">Соответствует указанному типу исключения .NET.</span><span class="sxs-lookup"><span data-stu-id="a4e72-125">Matches the specified .NET exception type.</span></span>|
|<span data-ttu-id="a4e72-126">:?</span><span class="sxs-lookup"><span data-stu-id="a4e72-126">:?</span></span> <span data-ttu-id="a4e72-127">*тип Exception —* *идентификатор*</span><span class="sxs-lookup"><span data-stu-id="a4e72-127">*exception-type* as *identifier*</span></span>|<span data-ttu-id="a4e72-128">Соответствует указанному типу исключения .NET, но присваивает исключению именованное значение.</span><span class="sxs-lookup"><span data-stu-id="a4e72-128">Matches the specified .NET exception type, but gives the exception a named value.</span></span>|
|<span data-ttu-id="a4e72-129">*имя исключения* (*аргументы*)</span><span class="sxs-lookup"><span data-stu-id="a4e72-129">*exception-name*(*arguments*)</span></span>|<span data-ttu-id="a4e72-130">Соответствует типу F# исключения и привязывает аргументы.</span><span class="sxs-lookup"><span data-stu-id="a4e72-130">Matches an F# exception type and binds the arguments.</span></span>|
|<span data-ttu-id="a4e72-131">*identifier*</span><span class="sxs-lookup"><span data-stu-id="a4e72-131">*identifier*</span></span>|<span data-ttu-id="a4e72-132">Соответствует любому исключению и привязывает имя к объекту исключения.</span><span class="sxs-lookup"><span data-stu-id="a4e72-132">Matches any exception and binds the name to the exception object.</span></span> <span data-ttu-id="a4e72-133">Эквивалентно **:? System. Exception в**качестве_идентификатора_</span><span class="sxs-lookup"><span data-stu-id="a4e72-133">Equivalent to **:? System.Exception as**_identifier_</span></span>|
|<span data-ttu-id="a4e72-134">*идентификатор* при *условии*</span><span class="sxs-lookup"><span data-stu-id="a4e72-134">*identifier* when *condition*</span></span>|<span data-ttu-id="a4e72-135">Соответствует любому исключению, если условие истинно.</span><span class="sxs-lookup"><span data-stu-id="a4e72-135">Matches any exception if the condition is true.</span></span>|

## <a name="examples"></a><span data-ttu-id="a4e72-136">Примеры</span><span class="sxs-lookup"><span data-stu-id="a4e72-136">Examples</span></span>

<span data-ttu-id="a4e72-137">В следующих примерах кода показано использование различных шаблонов обработчиков исключений.</span><span class="sxs-lookup"><span data-stu-id="a4e72-137">The following code examples illustrate the use of the various exception handler patterns.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]

> [!NOTE]
> <span data-ttu-id="a4e72-138">Конструкция представляет собой отдельное выражение `try...finally` из выражения. `try...with`</span><span class="sxs-lookup"><span data-stu-id="a4e72-138">The `try...with` construct is a separate expression from the `try...finally` expression.</span></span> <span data-ttu-id="a4e72-139">Поэтому, если в коде требуется `with` блок `finally` и блок, необходимо вложить два выражения.</span><span class="sxs-lookup"><span data-stu-id="a4e72-139">Therefore, if your code requires both a `with` block and a `finally` block, you will have to nest the two expressions.</span></span>

> [!NOTE]
> <span data-ttu-id="a4e72-140">Можно использовать `try...with` в асинхронных рабочих процессах и других вычислительных выражениях. в этом случае используется `try...with` настроенная версия выражения.</span><span class="sxs-lookup"><span data-stu-id="a4e72-140">You can use `try...with` in asynchronous workflows and other computation expressions, in which case a customized version of the `try...with` expression is used.</span></span> <span data-ttu-id="a4e72-141">Дополнительные сведения см. в разделе [асинхронные рабочие процессы](../asynchronous-workflows.md)и [вычислительные выражения](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a4e72-141">For more information, see [Asynchronous Workflows](../asynchronous-workflows.md), and [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a4e72-142">См. также</span><span class="sxs-lookup"><span data-stu-id="a4e72-142">See also</span></span>

- [<span data-ttu-id="a4e72-143">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="a4e72-143">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="a4e72-144">Типы исключения</span><span class="sxs-lookup"><span data-stu-id="a4e72-144">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="a4e72-145">Исключения. `try...finally` Выражение</span><span class="sxs-lookup"><span data-stu-id="a4e72-145">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
