---
title: "Управление ресурсами: ключевое слово use (F#)"
description: "Дополнительные сведения о F # ключевое слово «use» и «использование» функции, который может управлять инициализацией и освобождением ресурсов."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 00c3040e-859f-4dad-a7b5-7b8d44dc232c
ms.openlocfilehash: d4e8626f07f1c77e52e8fabd5ccc07dbf1fa8ddd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="resource-management-the-use-keyword"></a><span data-ttu-id="6e6ad-104">Управление ресурсами: ключевое слово use</span><span class="sxs-lookup"><span data-stu-id="6e6ad-104">Resource Management: The use Keyword</span></span>

<span data-ttu-id="6e6ad-105">В этом разделе описывается ключевое слово `use` и `using` функции, которые позволяют управлять инициализацией и освобождением ресурсов.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-105">This topic describes the keyword `use` and the `using` function, which can control the initialization and release of resources.</span></span>

## <a name="resources"></a><span data-ttu-id="6e6ad-106">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="6e6ad-106">Resources</span></span>
<span data-ttu-id="6e6ad-107">Термин *ресурсов* используется более чем одним способом.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-107">The term *resource* is used in more than one way.</span></span> <span data-ttu-id="6e6ad-108">Да, ресурсы могут быть данные, которые приложение использует, такие как строки, графики и т. д, но в этом контексте *ресурсов* содержатся ссылки на ресурсы операционной системы или программного обеспечения, такие как контексты графических устройств, дескрипторы файлов, сети и базы данных, подключения, параллельных объектов, таких как дескрипторы ожидания и т. д.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-108">Yes, resources can be data that an application uses, such as strings, graphics, and the like, but in this context, *resources* refers to software or operating system resources, such as graphics device contexts, file handles, network and database connections, concurrency objects such as wait handles, and so on.</span></span> <span data-ttu-id="6e6ad-109">Использование этих ресурсов приложениями подразумевает получение ресурса от операционной системы или другого поставщика ресурсов, за которым следует более поздней версии ресурса в пул, чтобы его можно предоставить другому приложению.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-109">The use of these resources by applications involves the acquisition of the resource from the operating system or other resource provider, followed by the later release of the resource to the pool so that it can be provided to another application.</span></span> <span data-ttu-id="6e6ad-110">Проблемы возникают, если приложения не выводят ресурсы обратно в пуле.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-110">Problems occur when applications do not release resources back to the common pool.</span></span>

## <a name="managing-resources"></a><span data-ttu-id="6e6ad-111">Управление ресурсами</span><span class="sxs-lookup"><span data-stu-id="6e6ad-111">Managing Resources</span></span>
<span data-ttu-id="6e6ad-112">Для эффективного и ответственного управления ресурсами в приложении необходимо освобождать ресурсы, своевременно и предсказуемым образом.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-112">To efficiently and responsibly manage resources in an application, you must release resources promptly and in a predictable manner.</span></span> <span data-ttu-id="6e6ad-113">.NET Framework помогает сделать это, предоставляя `System.IDisposable` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-113">The .NET Framework helps you do this by providing the `System.IDisposable` interface.</span></span> <span data-ttu-id="6e6ad-114">Тип, реализующий `System.IDisposable` имеет `System.IDisposable.Dispose` метод, который правильно освобождает ресурсы.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-114">A type that implements `System.IDisposable` has the `System.IDisposable.Dispose` method, which correctly frees resources.</span></span> <span data-ttu-id="6e6ad-115">Грамотно сконструированные приложения обеспечивают `System.IDisposable.Dispose` немедленно вызывается, когда любой объект, который содержит ограниченным ресурсом больше не нужен.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-115">Well-written applications guarantee that `System.IDisposable.Dispose` is called promptly when any object that holds a limited resource is no longer needed.</span></span> <span data-ttu-id="6e6ad-116">К счастью большинство языков .NET предоставляют поддержки, чтобы облегчить эту задачу, а F # не является исключением.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-116">Fortunately, most .NET languages provide support to make this easier, and F# is no exception.</span></span> <span data-ttu-id="6e6ad-117">Существует две полезные языковые конструкции, которые поддерживают шаблон dispose: `use` привязки и `using` функции.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-117">There are two useful language constructs that support the dispose pattern: the `use` binding and the `using` function.</span></span>

## <a name="use-binding"></a><span data-ttu-id="6e6ad-118">Использование привязки</span><span class="sxs-lookup"><span data-stu-id="6e6ad-118">use Binding</span></span>
<span data-ttu-id="6e6ad-119">`use` Ключевое слово имеет форму напоминает `let` привязки:</span><span class="sxs-lookup"><span data-stu-id="6e6ad-119">The `use` keyword has a form that resembles that of the `let` binding:</span></span>

<span data-ttu-id="6e6ad-120">Используйте *значение* = *выражение*</span><span class="sxs-lookup"><span data-stu-id="6e6ad-120">use *value* = *expression*</span></span>

<span data-ttu-id="6e6ad-121">Он предоставляет те же функциональные возможности, как `let` привязки, но добавляет вызов `Dispose` для значения, если значение выходит за пределы области.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-121">It provides the same functionality as a `let` binding but adds a call to `Dispose` on the value when the value goes out of scope.</span></span> <span data-ttu-id="6e6ad-122">Обратите внимание, что компилятор вставляет проверку значения на null, поэтому, если значение равно `null`, вызов `Dispose` не выполняется.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-122">Note that the compiler inserts a null check on the value, so that if the value is `null`, the call to `Dispose` is not attempted.</span></span>

<span data-ttu-id="6e6ad-123">В следующем примере показано, как автоматически закрывать файл с помощью `use` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-123">The following example shows how to close a file automatically by using the `use` keyword.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

>[!NOTE]
<span data-ttu-id="6e6ad-124">Можно использовать `use` в вычислительных выражениях в этом случае настроенную версию `use` используется выражение.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-124">You can use `use` in computation expressions, in which case a customized version of the `use` expression is used.</span></span> <span data-ttu-id="6e6ad-125">Дополнительные сведения см. в разделе [последовательности](sequences.md), [асинхронные рабочие потоки](asynchronous-workflows.md), и [вычислительных выражениях](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="6e6ad-125">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="using-function"></a><span data-ttu-id="6e6ad-126">с помощью функции</span><span class="sxs-lookup"><span data-stu-id="6e6ad-126">using Function</span></span>
<span data-ttu-id="6e6ad-127">`using` Функция имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="6e6ad-127">The `using` function has the following form:</span></span>

<span data-ttu-id="6e6ad-128">`using`(*expression1*) *функции или лямбда*</span><span class="sxs-lookup"><span data-stu-id="6e6ad-128">`using` (*expression1*) *function-or-lambda*</span></span>

<span data-ttu-id="6e6ad-129">В `using` выражение, *expression1* создает объект, который должен быть удален.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-129">In a `using` expression, *expression1* creates the object that must be disposed.</span></span> <span data-ttu-id="6e6ad-130">Результат *expression1* (объект, который необходимо освободить) становится аргумент *значение*в *функции или лямбда*, который является либо функцию, ожидающую один оставшийся аргумент типа, который соответствует значению, полученных при *expression1*, или лямбда-выражение, которое ожидает аргумент этого типа.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-130">The result of *expression1* (the object that must be disposed) becomes an argument, *value*, to *function-or-lambda*, which is either a function that expects a single remaining argument of a type that matches the value produced by *expression1*, or a lambda expression that expects an argument of that type.</span></span> <span data-ttu-id="6e6ad-131">В конце выполнения функции среда выполнения вызывает `Dispose` и освобождает ресурсы (пока значение `null`, в этом случае попытка вызова Dispose не предпринимается).</span><span class="sxs-lookup"><span data-stu-id="6e6ad-131">At the end of the execution of the function, the runtime calls `Dispose` and frees the resources (unless the value is `null`, in which case the call to Dispose is not attempted).</span></span>

<span data-ttu-id="6e6ad-132">В следующем примере демонстрируется `using` выражение с лямбда-выражением.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-132">The following example demonstrates the `using` expression with a lambda expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

<span data-ttu-id="6e6ad-133">В следующем примере показано `using` выражение с функцией.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-133">The next example shows the `using` expression with a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

<span data-ttu-id="6e6ad-134">Обратите внимание, что функция может быть функцией, которая уже применены некоторые аргументы.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-134">Note that the function could be a function that has some arguments applied already.</span></span> <span data-ttu-id="6e6ad-135">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-135">The following code example demonstrates this.</span></span> <span data-ttu-id="6e6ad-136">Он создает файл, содержащий строку `XYZ`.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-136">It creates a file that contains the string `XYZ`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

<span data-ttu-id="6e6ad-137">`using` Функции и `use` привязки — практически эквивалентные способы решения и то же.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-137">The `using` function and the `use` binding are nearly equivalent ways to accomplish the same thing.</span></span> <span data-ttu-id="6e6ad-138">`using` Ключевое слово предоставляет больший контроль над тем, когда `Dispose` вызывается.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-138">The `using` keyword provides more control over when `Dispose` is called.</span></span> <span data-ttu-id="6e6ad-139">При использовании `using`, `Dispose` вызывается в конце функции или лямбда-выражения; при использовании `use` ключевое слово, `Dispose` вызывается в конце содержащего его блока кода.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-139">When you use `using`, `Dispose` is called at the end of the function or lambda expression; when you use the `use` keyword, `Dispose` is called at the end of the containing code block.</span></span> <span data-ttu-id="6e6ad-140">В общем случае лучше использовать `use` вместо `using` функции.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-140">In general, you should prefer to use `use` instead of the `using` function.</span></span>


## <a name="see-also"></a><span data-ttu-id="6e6ad-141">См. также</span><span class="sxs-lookup"><span data-stu-id="6e6ad-141">See Also</span></span>
[<span data-ttu-id="6e6ad-142">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="6e6ad-142">F# Language Reference</span></span>](index.md)
