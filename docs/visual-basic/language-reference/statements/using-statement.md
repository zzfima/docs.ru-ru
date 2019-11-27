---
title: Оператор Using
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: 6ec0e228b3898f66f27e322b5db2dd7f3bf3d7d6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352761"
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="0766e-102">Оператор Using (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0766e-102">Using Statement (Visual Basic)</span></span>

<span data-ttu-id="0766e-103">Объявляет начало блока `Using` и при необходимости получает системные ресурсы, управляющие блоком.</span><span class="sxs-lookup"><span data-stu-id="0766e-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>

## <a name="syntax"></a><span data-ttu-id="0766e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0766e-104">Syntax</span></span>

```vb
Using { resourcelist | resourceexpression }
    [ statements ]
End Using
```

## <a name="parts"></a><span data-ttu-id="0766e-105">Части</span><span class="sxs-lookup"><span data-stu-id="0766e-105">Parts</span></span>

|<span data-ttu-id="0766e-106">Термин</span><span class="sxs-lookup"><span data-stu-id="0766e-106">Term</span></span>|<span data-ttu-id="0766e-107">Определение</span><span class="sxs-lookup"><span data-stu-id="0766e-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="0766e-108">Требуется, если `resourceexpression`не предоставлены.</span><span class="sxs-lookup"><span data-stu-id="0766e-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="0766e-109">Список из одного или нескольких системных ресурсов, которые этот `Using` блокируют элементы управления, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="0766e-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="0766e-110">Требуется, если `resourcelist`не предоставлены.</span><span class="sxs-lookup"><span data-stu-id="0766e-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="0766e-111">Ссылка на переменную или выражение, ссылающееся на системный ресурс, который должен управляться этим блоком `Using`.</span><span class="sxs-lookup"><span data-stu-id="0766e-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="0766e-112">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="0766e-112">Optional.</span></span> <span data-ttu-id="0766e-113">Блок инструкций, выполняемых блоком `Using`.</span><span class="sxs-lookup"><span data-stu-id="0766e-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="0766e-114">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="0766e-114">Required.</span></span> <span data-ttu-id="0766e-115">Завершает определение блока `Using` и уничтожает все ресурсы, которыми он управляет.</span><span class="sxs-lookup"><span data-stu-id="0766e-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  

 <span data-ttu-id="0766e-116">Каждый ресурс в `resourcelist` части имеет следующий синтаксис и части:</span><span class="sxs-lookup"><span data-stu-id="0766e-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>

 `resourcename As New resourcetype [ ( [ arglist ] ) ]`

 <span data-ttu-id="0766e-117">\- или -</span><span class="sxs-lookup"><span data-stu-id="0766e-117">-or-</span></span>

 `resourcename As resourcetype = resourceexpression`

## <a name="resourcelist-parts"></a><span data-ttu-id="0766e-118">ресаурцелист части</span><span class="sxs-lookup"><span data-stu-id="0766e-118">resourcelist Parts</span></span>

|<span data-ttu-id="0766e-119">Термин</span><span class="sxs-lookup"><span data-stu-id="0766e-119">Term</span></span>|<span data-ttu-id="0766e-120">Определение</span><span class="sxs-lookup"><span data-stu-id="0766e-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="0766e-121">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="0766e-121">Required.</span></span> <span data-ttu-id="0766e-122">Ссылочная переменная, которая ссылается на системный ресурс, который `Using` блочным элементам управления.</span><span class="sxs-lookup"><span data-stu-id="0766e-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="0766e-123">Требуется, если инструкция `Using` получает ресурс.</span><span class="sxs-lookup"><span data-stu-id="0766e-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="0766e-124">Если вы уже приобрели ресурс, используйте второй альтернативный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="0766e-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="0766e-125">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="0766e-125">Required.</span></span> <span data-ttu-id="0766e-126">Класс ресурса.</span><span class="sxs-lookup"><span data-stu-id="0766e-126">The class of the resource.</span></span> <span data-ttu-id="0766e-127">Класс должен реализовывать интерфейс <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="0766e-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="0766e-128">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="0766e-128">Optional.</span></span> <span data-ttu-id="0766e-129">Список аргументов, передаваемый конструктору для создания экземпляра `resourcetype`.</span><span class="sxs-lookup"><span data-stu-id="0766e-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="0766e-130">См. [список параметров](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="0766e-130">See [Parameter List](parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="0766e-131">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="0766e-131">Required.</span></span> <span data-ttu-id="0766e-132">Переменная или выражение, ссылающиеся на системный ресурс, удовлетворяющий требованиям `resourcetype`.</span><span class="sxs-lookup"><span data-stu-id="0766e-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="0766e-133">Если используется второй альтернативный синтаксис, необходимо получить ресурс перед передачей управления в оператор `Using`.</span><span class="sxs-lookup"><span data-stu-id="0766e-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0766e-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="0766e-134">Remarks</span></span>

 <span data-ttu-id="0766e-135">Иногда коду требуется неуправляемый ресурс, например файловый обработчик, оболочка COM или соединение SQL.</span><span class="sxs-lookup"><span data-stu-id="0766e-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="0766e-136">Блок `Using` гарантирует удаление одного или нескольких таких ресурсов при завершении кода с ними.</span><span class="sxs-lookup"><span data-stu-id="0766e-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="0766e-137">Это делает их доступными для использования другим кодом.</span><span class="sxs-lookup"><span data-stu-id="0766e-137">This makes them available for other code to use.</span></span>

 <span data-ttu-id="0766e-138">Управляемые ресурсы удаляются сборщиком мусора .NET Framework (GC) без дополнительного написания кода для вашей части.</span><span class="sxs-lookup"><span data-stu-id="0766e-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="0766e-139">Для управляемых ресурсов не требуется блок `Using`.</span><span class="sxs-lookup"><span data-stu-id="0766e-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="0766e-140">Однако можно по-прежнему использовать блок `Using` для принудительного удаления управляемого ресурса вместо ожидания сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="0766e-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>

 <span data-ttu-id="0766e-141">Блок `Using` состоит из трех частей: приобретение, использование и утилизация.</span><span class="sxs-lookup"><span data-stu-id="0766e-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>

- <span data-ttu-id="0766e-142">*Получение* означает создание переменной и ее инициализацию для ссылки на системный ресурс.</span><span class="sxs-lookup"><span data-stu-id="0766e-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="0766e-143">Инструкция `Using` может получить один или несколько ресурсов, либо можно получить ровно один ресурс, прежде чем вводить блок и предоставлять его в инструкцию `Using`.</span><span class="sxs-lookup"><span data-stu-id="0766e-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="0766e-144">При указании `resourceexpression`необходимо получить ресурс перед передачей управления в инструкцию `Using`.</span><span class="sxs-lookup"><span data-stu-id="0766e-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>

- <span data-ttu-id="0766e-145">*Использование* означает доступ к ресурсам и выполнение действий с ними.</span><span class="sxs-lookup"><span data-stu-id="0766e-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="0766e-146">Операторы между `Using` и `End Using` представляют использование ресурсов.</span><span class="sxs-lookup"><span data-stu-id="0766e-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>

- <span data-ttu-id="0766e-147">*Реализация* означает вызов метода <xref:System.IDisposable.Dispose%2A> для объекта в `resourcename`.</span><span class="sxs-lookup"><span data-stu-id="0766e-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="0766e-148">Это позволяет объекту очищать свои ресурсы.</span><span class="sxs-lookup"><span data-stu-id="0766e-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="0766e-149">Оператор `End Using` уничтожает ресурсы в элементе управления блока `Using`.</span><span class="sxs-lookup"><span data-stu-id="0766e-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>

## <a name="behavior"></a><span data-ttu-id="0766e-150">Поведение</span><span class="sxs-lookup"><span data-stu-id="0766e-150">Behavior</span></span>

 <span data-ttu-id="0766e-151">Блок `Using` ведет себя как `Try`...`Finally` конструкция, в которой блок `Try` использует ресурсы и уничтожает блок `Finally`.</span><span class="sxs-lookup"><span data-stu-id="0766e-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="0766e-152">По этой причине блок `Using` гарантирует освобождение ресурсов, независимо от того, как вы выйдете из блока.</span><span class="sxs-lookup"><span data-stu-id="0766e-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="0766e-153">Это справедливо даже в случае необработанного исключения, за исключением <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="0766e-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>

 <span data-ttu-id="0766e-154">Область каждой переменной ресурса, полученной инструкцией `Using`, ограничена блоком `Using`.</span><span class="sxs-lookup"><span data-stu-id="0766e-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>

 <span data-ttu-id="0766e-155">Если в инструкции `Using` указано более одного системного ресурса, то результат будет таким же, как если бы вложенный `Using` блокировал один из них.</span><span class="sxs-lookup"><span data-stu-id="0766e-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>

 <span data-ttu-id="0766e-156">Если `resourcename` `Nothing`, вызов <xref:System.IDisposable.Dispose%2A> не выполняется и исключение не создается.</span><span class="sxs-lookup"><span data-stu-id="0766e-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>

## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="0766e-157">Структурированная обработка исключений в блоке using</span><span class="sxs-lookup"><span data-stu-id="0766e-157">Structured Exception Handling Within a Using Block</span></span>

 <span data-ttu-id="0766e-158">Если необходимо выполнить обработку исключения, которое может возникнуть в блоке `Using`, можно добавить в него полную `Try`...`Finally`.</span><span class="sxs-lookup"><span data-stu-id="0766e-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="0766e-159">Если вам нужно решить, где при получении ресурса не удалось выполнить инструкцию `Using`, можно проверить, `Nothing`ли `resourcename`.</span><span class="sxs-lookup"><span data-stu-id="0766e-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>

## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="0766e-160">Структурированная обработка исключений вместо блока using</span><span class="sxs-lookup"><span data-stu-id="0766e-160">Structured Exception Handling Instead of a Using Block</span></span>

 <span data-ttu-id="0766e-161">Если требуется более точный контроль за приобретением ресурсов или требуется дополнительный код в блоке `Finally`, можно переписать блок `Using` как конструкцию `Try`...`Finally`.</span><span class="sxs-lookup"><span data-stu-id="0766e-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="0766e-162">В следующем примере показана скелетная конструкция `Try` и `Using`, которые эквивалентны при получении и утилизации `resource`.</span><span class="sxs-lookup"><span data-stu-id="0766e-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>

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
> <span data-ttu-id="0766e-163">Код в блоке `Using` не должен назначать объект в `resourcename` другой переменной.</span><span class="sxs-lookup"><span data-stu-id="0766e-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="0766e-164">При выходе из блока `Using` ресурс удаляется, а другая переменная не может получить доступ к ресурсу, на который он указывает.</span><span class="sxs-lookup"><span data-stu-id="0766e-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>

## <a name="example"></a><span data-ttu-id="0766e-165">Пример</span><span class="sxs-lookup"><span data-stu-id="0766e-165">Example</span></span>

 <span data-ttu-id="0766e-166">В следующем примере создается файл с именем log. txt и в него записываются две строки текста.</span><span class="sxs-lookup"><span data-stu-id="0766e-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="0766e-167">В примере также считывается тот же файл и отображаются строки текста:</span><span class="sxs-lookup"><span data-stu-id="0766e-167">The example also reads that same file and displays the lines of text:</span></span>

 <span data-ttu-id="0766e-168">Поскольку классы <xref:System.IO.TextWriter> и <xref:System.IO.TextReader> реализуют интерфейс <xref:System.IDisposable>, код может использовать `Using` операторы, чтобы гарантировать корректное закрытие файла после операций записи и чтения.</span><span class="sxs-lookup"><span data-stu-id="0766e-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>

 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]

## <a name="see-also"></a><span data-ttu-id="0766e-169">См. также</span><span class="sxs-lookup"><span data-stu-id="0766e-169">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="0766e-170">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="0766e-170">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="0766e-171">Практическое руководство. Удаление системного ресурса</span><span class="sxs-lookup"><span data-stu-id="0766e-171">How to: Dispose of a System Resource</span></span>](../../programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
