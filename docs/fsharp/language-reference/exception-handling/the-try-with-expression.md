---
title: 'Исключения: выражение try...with (F#)'
description: 'Сведения об использовании выражения F # «try... with» для обработки исключений.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 06e40b79fc1958918dc0615ce9d1004e0a6e74a5
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="exceptions-the-trywith-expression"></a><span data-ttu-id="f4d90-103">Исключения: выражение try...with</span><span class="sxs-lookup"><span data-stu-id="f4d90-103">Exceptions: The try...with Expression</span></span>

<span data-ttu-id="f4d90-104">В этом разделе описывается `try...with` выражение, выражение, которое используется для обработки исключений в языке F #.</span><span class="sxs-lookup"><span data-stu-id="f4d90-104">This topic describes the `try...with` expression, the expression that is used for exception handling in the F# language.</span></span>


## <a name="syntax"></a><span data-ttu-id="f4d90-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4d90-105">Syntax</span></span>

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a><span data-ttu-id="f4d90-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="f4d90-106">Remarks</span></span>
<span data-ttu-id="f4d90-107">`try...with` Выражение используется для обработки исключений в языке F #.</span><span class="sxs-lookup"><span data-stu-id="f4d90-107">The `try...with` expression is used to handle exceptions in F#.</span></span> <span data-ttu-id="f4d90-108">Это похоже на `try...catch` инструкции на языке C#.</span><span class="sxs-lookup"><span data-stu-id="f4d90-108">It is similar to the `try...catch` statement in C#.</span></span> <span data-ttu-id="f4d90-109">Приведенный выше синтаксис кода в *expression1* может вызвать исключение.</span><span class="sxs-lookup"><span data-stu-id="f4d90-109">In the preceding syntax, the code in *expression1* might generate an exception.</span></span> <span data-ttu-id="f4d90-110">`try...with` Выражение возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="f4d90-110">The `try...with` expression returns a value.</span></span> <span data-ttu-id="f4d90-111">Если исключение не возникает, то все выражение возвращает значение *expression1*.</span><span class="sxs-lookup"><span data-stu-id="f4d90-111">If no exception is thrown, the whole expression returns the value of *expression1*.</span></span> <span data-ttu-id="f4d90-112">Если создается исключение, каждый *шаблон* сравнивается в свою очередь, за исключением того и для первого соответствующий шаблон, соответствующий *выражение*, называемой *обработчик исключений*, для выполнения этой ветви, а общее выражение возвращает значение выражения в этот обработчик исключений.</span><span class="sxs-lookup"><span data-stu-id="f4d90-112">If an exception is thrown, each *pattern* is compared in turn with the exception, and for the first matching pattern, the corresponding *expression*, known as the *exception handler*, for that branch is executed, and the overall expression returns the value of the expression in that exception handler.</span></span> <span data-ttu-id="f4d90-113">При отсутствии соответствующего шаблона, исключение распространяется вверх по стеку вызовов, пока не будет найден соответствующий обработчик.</span><span class="sxs-lookup"><span data-stu-id="f4d90-113">If no pattern matches, the exception propagates up the call stack until a matching handler is found.</span></span> <span data-ttu-id="f4d90-114">Типы значений, возвращаемых каждым из выражений в обработчиках исключений должен соответствовать типу, возвращаемых из выражений в `try` блока.</span><span class="sxs-lookup"><span data-stu-id="f4d90-114">The types of the values returned from each expression in the exception handlers must match the type returned from the expression in the `try` block.</span></span>

<span data-ttu-id="f4d90-115">Как правило тот факт, что произошла ошибка также означает, что отсутствие допустимого значения, которые могут быть возвращены из выражений в каждого обработчика исключений.</span><span class="sxs-lookup"><span data-stu-id="f4d90-115">Frequently, the fact that an error occurred also means that there is no valid value that can be returned from the expressions in each exception handler.</span></span> <span data-ttu-id="f4d90-116">Часто используется шаблон является тип выражения является типом option.</span><span class="sxs-lookup"><span data-stu-id="f4d90-116">A frequent pattern is to have the type of the expression be an option type.</span></span> <span data-ttu-id="f4d90-117">В следующем примере кода показан этот шаблон.</span><span class="sxs-lookup"><span data-stu-id="f4d90-117">The following code example illustrates this pattern.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

<span data-ttu-id="f4d90-118">Исключения могут вызываться исключения .NET, или они могут быть исключения F #.</span><span class="sxs-lookup"><span data-stu-id="f4d90-118">Exceptions can be .NET exceptions, or they can be F# exceptions.</span></span> <span data-ttu-id="f4d90-119">Исключения F # можно определить с помощью `exception` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="f4d90-119">You can define F# exceptions by using the `exception` keyword.</span></span>

<span data-ttu-id="f4d90-120">Различные шаблоны можно использовать для фильтрации по типу исключения и другие условия; Возможные варианты приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f4d90-120">You can use a variety of patterns to filter on the exception type and other conditions; the options are summarized in the following table.</span></span>


|<span data-ttu-id="f4d90-121">Шаблон</span><span class="sxs-lookup"><span data-stu-id="f4d90-121">Pattern</span></span>|<span data-ttu-id="f4d90-122">Описание</span><span class="sxs-lookup"><span data-stu-id="f4d90-122">Description</span></span>|
|-------|-----------|
|<span data-ttu-id="f4d90-123">:?</span><span class="sxs-lookup"><span data-stu-id="f4d90-123">:?</span></span> <span data-ttu-id="f4d90-124">*Тип исключения*</span><span class="sxs-lookup"><span data-stu-id="f4d90-124">*exception-type*</span></span>|<span data-ttu-id="f4d90-125">Соответствует указанному типу исключения .NET.</span><span class="sxs-lookup"><span data-stu-id="f4d90-125">Matches the specified .NET exception type.</span></span>|
|<span data-ttu-id="f4d90-126">:?</span><span class="sxs-lookup"><span data-stu-id="f4d90-126">:?</span></span> <span data-ttu-id="f4d90-127">*Тип исключения* как *идентификатор*</span><span class="sxs-lookup"><span data-stu-id="f4d90-127">*exception-type* as *identifier*</span></span>|<span data-ttu-id="f4d90-128">Соответствует указанному типу исключения .NET, но присваивает исключению именованное значение.</span><span class="sxs-lookup"><span data-stu-id="f4d90-128">Matches the specified .NET exception type, but gives the exception a named value.</span></span>|
|<span data-ttu-id="f4d90-129">*имя исключения*(*аргументы*)</span><span class="sxs-lookup"><span data-stu-id="f4d90-129">*exception-name*(*arguments*)</span></span>|<span data-ttu-id="f4d90-130">Соответствует типу исключения F # и привязывает аргументы.</span><span class="sxs-lookup"><span data-stu-id="f4d90-130">Matches an F# exception type and binds the arguments.</span></span>|
|<span data-ttu-id="f4d90-131">*identifier*</span><span class="sxs-lookup"><span data-stu-id="f4d90-131">*identifier*</span></span>|<span data-ttu-id="f4d90-132">Соответствует любому исключению и привязывает имя объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="f4d90-132">Matches any exception and binds the name to the exception object.</span></span> <span data-ttu-id="f4d90-133">Эквивалентно **:? System.Exception как *** идентификатор*</span><span class="sxs-lookup"><span data-stu-id="f4d90-133">Equivalent to **:? System.Exception as***identifier*</span></span>|
|<span data-ttu-id="f4d90-134">*Идентификатор* при *условие*</span><span class="sxs-lookup"><span data-stu-id="f4d90-134">*identifier* when *condition*</span></span>|<span data-ttu-id="f4d90-135">Соответствует любому исключению, если условие истинно.</span><span class="sxs-lookup"><span data-stu-id="f4d90-135">Matches any exception if the condition is true.</span></span>|

## <a name="examples"></a><span data-ttu-id="f4d90-136">Примеры</span><span class="sxs-lookup"><span data-stu-id="f4d90-136">Examples</span></span>
<span data-ttu-id="f4d90-137">В следующих примерах кода показано использование различных шаблонов обработчиков исключений.</span><span class="sxs-lookup"><span data-stu-id="f4d90-137">The following code examples illustrate the use of the various exception handler patterns.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]
    
>[!NOTE] 
<span data-ttu-id="f4d90-138">`try...with` Конструкция отдельное выражение из `try...finally` выражение.</span><span class="sxs-lookup"><span data-stu-id="f4d90-138">The `try...with` construct is a separate expression from the `try...finally` expression.</span></span> <span data-ttu-id="f4d90-139">Таким образом Если код требует выполнения обоих `with` блока и `finally` блока, будет необходимо вложить двух выражений.</span><span class="sxs-lookup"><span data-stu-id="f4d90-139">Therefore, if your code requires both a `with` block and a `finally` block, you will have to nest the two expressions.</span></span>

>[!NOTE] 
<span data-ttu-id="f4d90-140">Можно использовать `try...with` в асинхронных рабочих процессах и других вычислительных выражениях, в котором используется настроенная версия из `try...with` используется выражение.</span><span class="sxs-lookup"><span data-stu-id="f4d90-140">You can use `try...with` in asynchronous workflows and other computation expressions, in which case a customized version of the `try...with` expression is used.</span></span> <span data-ttu-id="f4d90-141">Дополнительные сведения см. в разделе [асинхронные рабочие потоки](../asynchronous-workflows.md), и [вычислительных выражениях](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f4d90-141">For more information, see [Asynchronous Workflows](../asynchronous-workflows.md), and [Computation Expressions](../computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="f4d90-142">См. также</span><span class="sxs-lookup"><span data-stu-id="f4d90-142">See Also</span></span>
[<span data-ttu-id="f4d90-143">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="f4d90-143">Exception Handling</span></span>](index.md)

[<span data-ttu-id="f4d90-144">Типы исключения</span><span class="sxs-lookup"><span data-stu-id="f4d90-144">Exception Types</span></span>](exception-types.md)

[<span data-ttu-id="f4d90-145">Исключения: выражение `try...finally`</span><span class="sxs-lookup"><span data-stu-id="f4d90-145">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
