---
title: Оператор Using (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
caps.latest.revision: 36
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ed9cc0d04c89eac1fe342a0924dd89bb1e258a11
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="2659d-102">Оператор Using (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2659d-102">Using Statement (Visual Basic)</span></span>
<span data-ttu-id="2659d-103">Объявляет начало `Using` блокировку и при необходимости получает системные ресурсы, которыми управляет блок.</span><span class="sxs-lookup"><span data-stu-id="2659d-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2659d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2659d-104">Syntax</span></span>  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a><span data-ttu-id="2659d-105">Части</span><span class="sxs-lookup"><span data-stu-id="2659d-105">Parts</span></span>  
  
|<span data-ttu-id="2659d-106">Термин</span><span class="sxs-lookup"><span data-stu-id="2659d-106">Term</span></span>|<span data-ttu-id="2659d-107">Определение</span><span class="sxs-lookup"><span data-stu-id="2659d-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="2659d-108">Требуется, если не указать `resourceexpression`.</span><span class="sxs-lookup"><span data-stu-id="2659d-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="2659d-109">Список из одного или нескольких системных ресурсов, это `Using` блокировать элементы управления, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="2659d-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="2659d-110">Требуется, если не указать `resourcelist`.</span><span class="sxs-lookup"><span data-stu-id="2659d-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="2659d-111">Ссылочная переменная или выражение, которое ссылается на системный ресурс, чтобы управлять этим `Using` блока.</span><span class="sxs-lookup"><span data-stu-id="2659d-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="2659d-112">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="2659d-112">Optional.</span></span> <span data-ttu-id="2659d-113">Блок инструкций, `Using` блок.</span><span class="sxs-lookup"><span data-stu-id="2659d-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="2659d-114">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="2659d-114">Required.</span></span> <span data-ttu-id="2659d-115">Завершает определение `Using` блоков и освобождает все ресурсы, которыми он управляет.</span><span class="sxs-lookup"><span data-stu-id="2659d-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  
  
 <span data-ttu-id="2659d-116">Каждый ресурс в `resourcelist` часть имеет следующий синтаксис и компоненты:</span><span class="sxs-lookup"><span data-stu-id="2659d-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 <span data-ttu-id="2659d-117">-или-</span><span class="sxs-lookup"><span data-stu-id="2659d-117">-or-</span></span>  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a><span data-ttu-id="2659d-118">resourcelist частей</span><span class="sxs-lookup"><span data-stu-id="2659d-118">resourcelist Parts</span></span>  
  
|<span data-ttu-id="2659d-119">Термин</span><span class="sxs-lookup"><span data-stu-id="2659d-119">Term</span></span>|<span data-ttu-id="2659d-120">Определение</span><span class="sxs-lookup"><span data-stu-id="2659d-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="2659d-121">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="2659d-121">Required.</span></span> <span data-ttu-id="2659d-122">Ссылочная переменная, которая ссылается на системный ресурс, `Using` блокировать элементы управления.</span><span class="sxs-lookup"><span data-stu-id="2659d-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="2659d-123">Обязателен, если `Using` инструкция получает ресурса.</span><span class="sxs-lookup"><span data-stu-id="2659d-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="2659d-124">Если ресурс уже получен, используйте альтернативный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="2659d-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="2659d-125">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="2659d-125">Required.</span></span> <span data-ttu-id="2659d-126">Класс ресурса.</span><span class="sxs-lookup"><span data-stu-id="2659d-126">The class of the resource.</span></span> <span data-ttu-id="2659d-127">Класс должен реализовывать <xref:System.IDisposable> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2659d-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="2659d-128">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="2659d-128">Optional.</span></span> <span data-ttu-id="2659d-129">Список аргументов, которые передаются в конструктор для создания экземпляра `resourcetype`.</span><span class="sxs-lookup"><span data-stu-id="2659d-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="2659d-130">В разделе [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="2659d-130">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="2659d-131">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="2659d-131">Required.</span></span> <span data-ttu-id="2659d-132">Переменная или выражение, которое ссылается на системный ресурс, отвечающий требованиям `resourcetype`.</span><span class="sxs-lookup"><span data-stu-id="2659d-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="2659d-133">Если используется альтернативный синтаксис, необходимо получить ресурс перед передачей управления `Using` инструкции.</span><span class="sxs-lookup"><span data-stu-id="2659d-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2659d-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="2659d-134">Remarks</span></span>  
 <span data-ttu-id="2659d-135">Иногда код требует неуправляемых ресурсов, такие как дескриптор файла, оболочка COM или SQL-соединение.</span><span class="sxs-lookup"><span data-stu-id="2659d-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="2659d-136">Объект `Using` блок гарантирует удаление одного или нескольких таких ресурсов после завершения вашего кода с ними.</span><span class="sxs-lookup"><span data-stu-id="2659d-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="2659d-137">Это делает их доступными для использования другим кодом.</span><span class="sxs-lookup"><span data-stu-id="2659d-137">This makes them available for other code to use.</span></span>  
  
 <span data-ttu-id="2659d-138">Управляемые ресурсы удаляются с .NET Framework сборщик мусора (GC) без дополнительного кодирования со стороны пользователя.</span><span class="sxs-lookup"><span data-stu-id="2659d-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="2659d-139">Нет необходимости `Using` блок для управляемых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="2659d-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="2659d-140">Тем не менее, можно по-прежнему использовать `Using` блок для принудительного освобождения управляемых ресурсов, а не ждет, пока сборщик мусора.</span><span class="sxs-lookup"><span data-stu-id="2659d-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="2659d-141">Объект `Using` блок состоит из трех частей: приобретение, использование и удаление.</span><span class="sxs-lookup"><span data-stu-id="2659d-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>  
  
-   <span data-ttu-id="2659d-142">*Приобретение* означает создание переменной и инициализация ее для ссылки на ресурс системы.</span><span class="sxs-lookup"><span data-stu-id="2659d-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="2659d-143">`Using` Оператор может получить один или несколько ресурсов, или можно получить ровно один ресурс перед вводом блока и указать его `Using` инструкции.</span><span class="sxs-lookup"><span data-stu-id="2659d-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="2659d-144">При указании `resourceexpression`, необходимо получить ресурс перед передачей управления `Using` инструкции.</span><span class="sxs-lookup"><span data-stu-id="2659d-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>  
  
-   <span data-ttu-id="2659d-145">*Использование* означает доступ к ресурсам и выполнение действий с ними.</span><span class="sxs-lookup"><span data-stu-id="2659d-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="2659d-146">Инструкции между `Using` и `End Using` представляют собой использование ресурсов.</span><span class="sxs-lookup"><span data-stu-id="2659d-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>  
  
-   <span data-ttu-id="2659d-147">*Реализация* означает вызов <xref:System.IDisposable.Dispose%2A> объекта в метод `resourcename`.</span><span class="sxs-lookup"><span data-stu-id="2659d-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="2659d-148">Это позволяет объекту удалить его ресурсы.</span><span class="sxs-lookup"><span data-stu-id="2659d-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="2659d-149">`End Using` Инструкции освобождает все ресурсы в группе `Using` блока управления.</span><span class="sxs-lookup"><span data-stu-id="2659d-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="2659d-150">Поведение</span><span class="sxs-lookup"><span data-stu-id="2659d-150">Behavior</span></span>  
 <span data-ttu-id="2659d-151">Объект `Using` блок ведет себя как `Try`... `Finally` построения, в котором `Try` блок использует ресурсы и `Finally` блок удаляет их.</span><span class="sxs-lookup"><span data-stu-id="2659d-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="2659d-152">По этой причине `Using` блок гарантирует освобождение ресурсов, независимо от того, как выйти из блока.</span><span class="sxs-lookup"><span data-stu-id="2659d-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="2659d-153">Это верно даже при наличии необработанного исключения, за исключением <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="2659d-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>  
  
 <span data-ttu-id="2659d-154">Области каждой переменной ресурсов, полученных `Using` инструкции ограничено `Using` блока.</span><span class="sxs-lookup"><span data-stu-id="2659d-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>  
  
 <span data-ttu-id="2659d-155">Если указать более одного системного ресурса в `Using` инструкции эффект совпадает, если вложенные `Using` блокирует один в другой.</span><span class="sxs-lookup"><span data-stu-id="2659d-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>  
  
 <span data-ttu-id="2659d-156">Если `resourcename` — `Nothing`, не вызов <xref:System.IDisposable.Dispose%2A> производится, и исключение не возникает.</span><span class="sxs-lookup"><span data-stu-id="2659d-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>  
  
## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="2659d-157">В блоке Using обработке структурированных исключений</span><span class="sxs-lookup"><span data-stu-id="2659d-157">Structured Exception Handling Within a Using Block</span></span>  
 <span data-ttu-id="2659d-158">Если необходимо обрабатывать исключения, которые могут возникнуть в `Using` блока, можно добавить полный `Try`... `Finally` конструкции, к нему.</span><span class="sxs-lookup"><span data-stu-id="2659d-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="2659d-159">Если требуется обрабатывать случаи, где `Using` инструкции не удалось получить ресурсы, можно проверить на предмет `resourcename` — `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="2659d-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="2659d-160">Структурированная обработка исключений без блока с помощью</span><span class="sxs-lookup"><span data-stu-id="2659d-160">Structured Exception Handling Instead of a Using Block</span></span>  
 <span data-ttu-id="2659d-161">Если требуется более точный контроль приобретение ресурсов, или требуется дополнительный код в `Finally` блока, можно переписать `Using` блокировки на `Try`... `Finally` построения.</span><span class="sxs-lookup"><span data-stu-id="2659d-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="2659d-162">В следующем примере показано основу `Try` и `Using` конструкций, которые эквивалентны в приобретении и реализации `resource`.</span><span class="sxs-lookup"><span data-stu-id="2659d-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>  
  
```vb  
Using resource As New resourceType   
    ' Insert code to work with resource.  
End Using  
  
' For the acquisition and disposal of resource, the following  
' Try construction is equivalent to the Using block.  
Dim resource As New resourceType  
Try   
    ' Insert code to work with resource.  
Finally   
    If resource IsNot Nothing Then  
        resource.Dispose()   
    End If  
End Try   
```  
  
> [!NOTE]
>  <span data-ttu-id="2659d-163">Код внутри `Using` блок не следует присваивать объект в `resourcename` другой переменной.</span><span class="sxs-lookup"><span data-stu-id="2659d-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="2659d-164">После выхода из `Using` блока, ресурс удаляется, а другая переменная нет доступа к ресурсу, на который он указывает.</span><span class="sxs-lookup"><span data-stu-id="2659d-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2659d-165">Пример</span><span class="sxs-lookup"><span data-stu-id="2659d-165">Example</span></span>  
 <span data-ttu-id="2659d-166">В следующем примере создается файл с именем log.txt и записывает две строки текста в файл.</span><span class="sxs-lookup"><span data-stu-id="2659d-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="2659d-167">В примере также считывает этот же файл и отображаются строки текста.</span><span class="sxs-lookup"><span data-stu-id="2659d-167">The example also reads that same file and displays the lines of text.</span></span>  
  
 <span data-ttu-id="2659d-168">Поскольку <xref:System.IO.TextWriter> и <xref:System.IO.TextReader> классы реализуют <xref:System.IDisposable> интерфейс, в коде можно использовать `Using` инструкции, чтобы убедиться, что файл правильно закрыты после записи и операций чтения.</span><span class="sxs-lookup"><span data-stu-id="2659d-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>  
  
 [!code-vb[VbVbalrStatements#50](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/using-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2659d-169">См. также</span><span class="sxs-lookup"><span data-stu-id="2659d-169">See Also</span></span>  
 <xref:System.IDisposable>  
 [<span data-ttu-id="2659d-170">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="2659d-170">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="2659d-171">Практическое руководство. Удаление системного ресурса</span><span class="sxs-lookup"><span data-stu-id="2659d-171">How to: Dispose of a System Resource</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
