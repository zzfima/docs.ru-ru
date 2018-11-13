---
title: 'Исключения: выражение try...with (F#)'
description: Узнайте, как с помощью выражения F# «try... with» для обработки исключений.
ms.date: 05/16/2016
ms.openlocfilehash: 588960c0f8ccedb431c37d0f1314bf1a293b638c
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "44042170"
---
# <a name="exceptions-the-trywith-expression"></a><span data-ttu-id="1ab9d-103">Исключения: выражение try...with</span><span class="sxs-lookup"><span data-stu-id="1ab9d-103">Exceptions: The try...with Expression</span></span>

<span data-ttu-id="1ab9d-104">В этом разделе описывается `try...with` выражение, выражение, которое используется для обработки исключений в языке F#.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-104">This topic describes the `try...with` expression, the expression that is used for exception handling in the F# language.</span></span>

## <a name="syntax"></a><span data-ttu-id="1ab9d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ab9d-105">Syntax</span></span>

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a><span data-ttu-id="1ab9d-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="1ab9d-106">Remarks</span></span>

<span data-ttu-id="1ab9d-107">`try...with` Выражение используется для обработки исключений в языке F#.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-107">The `try...with` expression is used to handle exceptions in F#.</span></span> <span data-ttu-id="1ab9d-108">Это похоже на `try...catch` инструкции на языке C#.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-108">It is similar to the `try...catch` statement in C#.</span></span> <span data-ttu-id="1ab9d-109">Приведенный выше синтаксис кода в *expression1* может явиться источником исключения.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-109">In the preceding syntax, the code in *expression1* might generate an exception.</span></span> <span data-ttu-id="1ab9d-110">`try...with` Выражение возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-110">The `try...with` expression returns a value.</span></span> <span data-ttu-id="1ab9d-111">Если исключение не создается, то все выражение возвращает значение *expression1*.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-111">If no exception is thrown, the whole expression returns the value of *expression1*.</span></span> <span data-ttu-id="1ab9d-112">Если создается исключение, каждый *шаблон* сравнивается в свою очередь, за исключением, а также для первый совпадающий шаблон, соответствующий *выражение*, которая называется *обработчик исключений*, для выполнения этой ветви, а общее выражение возвращает значение выражения в этом обработчике исключений.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-112">If an exception is thrown, each *pattern* is compared in turn with the exception, and for the first matching pattern, the corresponding *expression*, known as the *exception handler*, for that branch is executed, and the overall expression returns the value of the expression in that exception handler.</span></span> <span data-ttu-id="1ab9d-113">Если шаблон не совпадает, исключение передается вверх по стеку вызовов, пока не будет найден соответствующий обработчик.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-113">If no pattern matches, the exception propagates up the call stack until a matching handler is found.</span></span> <span data-ttu-id="1ab9d-114">Типы значений, возвращаемых каждым из выражений в обработчиках исключений должен соответствовать типу, возвращаемому из выражения в `try` блока.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-114">The types of the values returned from each expression in the exception handlers must match the type returned from the expression in the `try` block.</span></span>

<span data-ttu-id="1ab9d-115">Как правило тот факт, что произошла ошибка также означает, что отсутствует допустимое значение, могут быть возвращены из выражений в каждый обработчик исключений.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-115">Frequently, the fact that an error occurred also means that there is no valid value that can be returned from the expressions in each exception handler.</span></span> <span data-ttu-id="1ab9d-116">Часто является тип выражения быть типом параметра.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-116">A frequent pattern is to have the type of the expression be an option type.</span></span> <span data-ttu-id="1ab9d-117">В следующем примере кода показан этот шаблон.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-117">The following code example illustrates this pattern.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

<span data-ttu-id="1ab9d-118">Исключения могут вызываться исключения .NET, или они могут быть исключения F#.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-118">Exceptions can be .NET exceptions, or they can be F# exceptions.</span></span> <span data-ttu-id="1ab9d-119">Можно задать исключения F# с помощью `exception` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-119">You can define F# exceptions by using the `exception` keyword.</span></span>

<span data-ttu-id="1ab9d-120">Другие шаблоны можно использовать для фильтрации по типу исключения и другие условия; в следующей таблице приведены параметры.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-120">You can use a variety of patterns to filter on the exception type and other conditions; the options are summarized in the following table.</span></span>

|<span data-ttu-id="1ab9d-121">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1ab9d-121">Pattern</span></span>|<span data-ttu-id="1ab9d-122">Описание</span><span class="sxs-lookup"><span data-stu-id="1ab9d-122">Description</span></span>|
|-------|-----------|
|<span data-ttu-id="1ab9d-123">:?</span><span class="sxs-lookup"><span data-stu-id="1ab9d-123">:?</span></span> <span data-ttu-id="1ab9d-124">*Тип исключения*</span><span class="sxs-lookup"><span data-stu-id="1ab9d-124">*exception-type*</span></span>|<span data-ttu-id="1ab9d-125">Совпадает с указанным типом исключения .NET.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-125">Matches the specified .NET exception type.</span></span>|
|<span data-ttu-id="1ab9d-126">:?</span><span class="sxs-lookup"><span data-stu-id="1ab9d-126">:?</span></span> <span data-ttu-id="1ab9d-127">*Тип исключения* как *идентификатор*</span><span class="sxs-lookup"><span data-stu-id="1ab9d-127">*exception-type* as *identifier*</span></span>|<span data-ttu-id="1ab9d-128">Совпадает с указанным типом исключения .NET, но дает исключение именованное значение.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-128">Matches the specified .NET exception type, but gives the exception a named value.</span></span>|
|<span data-ttu-id="1ab9d-129">*имя исключения*(*аргументы*)</span><span class="sxs-lookup"><span data-stu-id="1ab9d-129">*exception-name*(*arguments*)</span></span>|<span data-ttu-id="1ab9d-130">Совпадает с типом исключения F# и привязывает аргументы.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-130">Matches an F# exception type and binds the arguments.</span></span>|
|<span data-ttu-id="1ab9d-131">*identifier*</span><span class="sxs-lookup"><span data-stu-id="1ab9d-131">*identifier*</span></span>|<span data-ttu-id="1ab9d-132">Соответствует любому исключению и привязывает имя объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-132">Matches any exception and binds the name to the exception object.</span></span> <span data-ttu-id="1ab9d-133">Эквивалентно \**:? System.Exception как \*\*\* идентификатор*</span><span class="sxs-lookup"><span data-stu-id="1ab9d-133">Equivalent to \**:? System.Exception as\*\*\*identifier*</span></span>|
|<span data-ttu-id="1ab9d-134">*Идентификатор* при *условие*</span><span class="sxs-lookup"><span data-stu-id="1ab9d-134">*identifier* when *condition*</span></span>|<span data-ttu-id="1ab9d-135">Соответствует любому исключению, если условие истинно.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-135">Matches any exception if the condition is true.</span></span>|

## <a name="examples"></a><span data-ttu-id="1ab9d-136">Примеры</span><span class="sxs-lookup"><span data-stu-id="1ab9d-136">Examples</span></span>

<span data-ttu-id="1ab9d-137">В следующих примерах кода показано использование различных шаблонов обработчиков исключений.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-137">The following code examples illustrate the use of the various exception handler patterns.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]

>[!NOTE]
<span data-ttu-id="1ab9d-138">`try...with` Конструкция — отдельное выражение из `try...finally` выражение.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-138">The `try...with` construct is a separate expression from the `try...finally` expression.</span></span> <span data-ttu-id="1ab9d-139">Таким образом Если код требует оба `with` блока и `finally` блока, необходимо будет вкладывать друг в друга двух выражений.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-139">Therefore, if your code requires both a `with` block and a `finally` block, you will have to nest the two expressions.</span></span>

>[!NOTE]
<span data-ttu-id="1ab9d-140">Можно использовать `try...with` в асинхронные рабочие потоки и другие вычисления выражения, в котором случае настроенную версию `try...with` используется выражение.</span><span class="sxs-lookup"><span data-stu-id="1ab9d-140">You can use `try...with` in asynchronous workflows and other computation expressions, in which case a customized version of the `try...with` expression is used.</span></span> <span data-ttu-id="1ab9d-141">Дополнительные сведения см. в разделе [асинхронные рабочие потоки](../asynchronous-workflows.md), и [выражения вычисления](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="1ab9d-141">For more information, see [Asynchronous Workflows](../asynchronous-workflows.md), and [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1ab9d-142">См. также</span><span class="sxs-lookup"><span data-stu-id="1ab9d-142">See also</span></span>

- [<span data-ttu-id="1ab9d-143">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="1ab9d-143">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="1ab9d-144">Типы исключения</span><span class="sxs-lookup"><span data-stu-id="1ab9d-144">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="1ab9d-145">Исключения: выражение `try...finally`</span><span class="sxs-lookup"><span data-stu-id="1ab9d-145">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
