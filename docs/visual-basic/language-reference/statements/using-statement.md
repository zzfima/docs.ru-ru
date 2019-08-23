---
title: Оператор Using (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: 346a26ad5751599831d8b0d3e0497e4d488eb76c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957548"
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="922b2-102">Оператор Using (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="922b2-102">Using Statement (Visual Basic)</span></span>
<span data-ttu-id="922b2-103">Объявляет начало `Using` блока и при необходимости получает системные ресурсы, которые блокируют элементы управления.</span><span class="sxs-lookup"><span data-stu-id="922b2-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="922b2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="922b2-104">Syntax</span></span>  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a><span data-ttu-id="922b2-105">Части</span><span class="sxs-lookup"><span data-stu-id="922b2-105">Parts</span></span>  
  
|<span data-ttu-id="922b2-106">Термин</span><span class="sxs-lookup"><span data-stu-id="922b2-106">Term</span></span>|<span data-ttu-id="922b2-107">Определение</span><span class="sxs-lookup"><span data-stu-id="922b2-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="922b2-108">Требуется, если не указан `resourceexpression`.</span><span class="sxs-lookup"><span data-stu-id="922b2-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="922b2-109">Список из одного или нескольких системных ресурсов, которые `Using` управляются этим блоком, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="922b2-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="922b2-110">Требуется, если не указан `resourcelist`.</span><span class="sxs-lookup"><span data-stu-id="922b2-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="922b2-111">Ссылка на переменную или выражение, ссылающееся на системный ресурс, который `Using` должен управляться этим блоком.</span><span class="sxs-lookup"><span data-stu-id="922b2-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="922b2-112">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="922b2-112">Optional.</span></span> <span data-ttu-id="922b2-113">Блок операторов, `Using` выполняемых блоком.</span><span class="sxs-lookup"><span data-stu-id="922b2-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="922b2-114">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="922b2-114">Required.</span></span> <span data-ttu-id="922b2-115">Завершает определение `Using` блока и уничтожает все ресурсы, которыми он управляет.</span><span class="sxs-lookup"><span data-stu-id="922b2-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  
  
 <span data-ttu-id="922b2-116">Каждый ресурс в `resourcelist` части имеет следующий синтаксис и части:</span><span class="sxs-lookup"><span data-stu-id="922b2-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 <span data-ttu-id="922b2-117">-или-</span><span class="sxs-lookup"><span data-stu-id="922b2-117">-or-</span></span>  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a><span data-ttu-id="922b2-118">ресаурцелист части</span><span class="sxs-lookup"><span data-stu-id="922b2-118">resourcelist Parts</span></span>  
  
|<span data-ttu-id="922b2-119">Термин</span><span class="sxs-lookup"><span data-stu-id="922b2-119">Term</span></span>|<span data-ttu-id="922b2-120">Определение</span><span class="sxs-lookup"><span data-stu-id="922b2-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="922b2-121">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="922b2-121">Required.</span></span> <span data-ttu-id="922b2-122">Ссылочная переменная, которая ссылается на системный ресурс, `Using` который контролируется блоком.</span><span class="sxs-lookup"><span data-stu-id="922b2-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="922b2-123">Требуется, `Using` если инструкция получает ресурс.</span><span class="sxs-lookup"><span data-stu-id="922b2-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="922b2-124">Если вы уже приобрели ресурс, используйте второй альтернативный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="922b2-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="922b2-125">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="922b2-125">Required.</span></span> <span data-ttu-id="922b2-126">Класс ресурса.</span><span class="sxs-lookup"><span data-stu-id="922b2-126">The class of the resource.</span></span> <span data-ttu-id="922b2-127">Класс должен реализовывать <xref:System.IDisposable> интерфейс.</span><span class="sxs-lookup"><span data-stu-id="922b2-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="922b2-128">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="922b2-128">Optional.</span></span> <span data-ttu-id="922b2-129">Список аргументов, передаваемый конструктору для создания экземпляра `resourcetype`.</span><span class="sxs-lookup"><span data-stu-id="922b2-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="922b2-130">См. [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="922b2-130">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="922b2-131">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="922b2-131">Required.</span></span> <span data-ttu-id="922b2-132">Переменная или выражение, ссылающееся на системный ресурс, удовлетворяющий требованиям `resourcetype`.</span><span class="sxs-lookup"><span data-stu-id="922b2-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="922b2-133">Если используется второй альтернативный синтаксис, необходимо получить ресурс перед передачей управления `Using` оператору.</span><span class="sxs-lookup"><span data-stu-id="922b2-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="922b2-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="922b2-134">Remarks</span></span>  
 <span data-ttu-id="922b2-135">Иногда коду требуется неуправляемый ресурс, например файловый обработчик, оболочка COM или соединение SQL.</span><span class="sxs-lookup"><span data-stu-id="922b2-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="922b2-136">`Using` Блок гарантирует удаление одного или нескольких таких ресурсов при завершении кода с ними.</span><span class="sxs-lookup"><span data-stu-id="922b2-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="922b2-137">Это делает их доступными для использования другим кодом.</span><span class="sxs-lookup"><span data-stu-id="922b2-137">This makes them available for other code to use.</span></span>  
  
 <span data-ttu-id="922b2-138">Управляемые ресурсы удаляются сборщиком мусора .NET Framework (GC) без дополнительного написания кода для вашей части.</span><span class="sxs-lookup"><span data-stu-id="922b2-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="922b2-139">Для управляемых ресурсов `Using` блок не требуется.</span><span class="sxs-lookup"><span data-stu-id="922b2-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="922b2-140">Однако можно по-прежнему использовать `Using` блок для принудительного удаления управляемого ресурса вместо ожидания сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="922b2-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="922b2-141">Блок `Using` состоит из трех частей: приобретение, использование и утилизация.</span><span class="sxs-lookup"><span data-stu-id="922b2-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>  
  
- <span data-ttu-id="922b2-142">*Получение* означает создание переменной и ее инициализацию для ссылки на системный ресурс.</span><span class="sxs-lookup"><span data-stu-id="922b2-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="922b2-143">Инструкция может получить один или несколько ресурсов, либо можно получить ровно один ресурс, прежде чем входить в блок и передать его `Using` в инструкцию. `Using`</span><span class="sxs-lookup"><span data-stu-id="922b2-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="922b2-144">При указании `resourceexpression`необходимо получить ресурс перед передачей управления `Using` оператору.</span><span class="sxs-lookup"><span data-stu-id="922b2-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>  
  
- <span data-ttu-id="922b2-145">*Использование* означает доступ к ресурсам и выполнение действий с ними.</span><span class="sxs-lookup"><span data-stu-id="922b2-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="922b2-146">Операторы между `Using` и `End Using` представляют использование ресурсов.</span><span class="sxs-lookup"><span data-stu-id="922b2-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>  
  
- <span data-ttu-id="922b2-147">*Реализация* означает вызов <xref:System.IDisposable.Dispose%2A> метода для объекта в `resourcename`.</span><span class="sxs-lookup"><span data-stu-id="922b2-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="922b2-148">Это позволяет объекту очищать свои ресурсы.</span><span class="sxs-lookup"><span data-stu-id="922b2-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="922b2-149">Оператор уничтожает ресурсы `Using` под управлением блока. `End Using`</span><span class="sxs-lookup"><span data-stu-id="922b2-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="922b2-150">Поведение</span><span class="sxs-lookup"><span data-stu-id="922b2-150">Behavior</span></span>  
 <span data-ttu-id="922b2-151">Блок ведет себя `Try`подобно... `Using` конструкция, в `Try` которой блок `Finally` использует ресурсы, а блок удаляет их. `Finally`</span><span class="sxs-lookup"><span data-stu-id="922b2-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="922b2-152">По `Using` этой причине блок гарантирует освобождение ресурсов, независимо от того, как вы выйдете из блока.</span><span class="sxs-lookup"><span data-stu-id="922b2-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="922b2-153">Это справедливо даже в случае необработанного исключения, за исключением <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="922b2-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>  
  
 <span data-ttu-id="922b2-154">Область каждой переменной ресурса, полученной `Using` инструкцией, ограничена `Using` блоком.</span><span class="sxs-lookup"><span data-stu-id="922b2-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>  
  
 <span data-ttu-id="922b2-155">Если в `Using` инструкции указано более одного системного ресурса, то такой результат будет таким же, как если бы вложенные `Using` блоки совпадали друг с другом.</span><span class="sxs-lookup"><span data-stu-id="922b2-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>  
  
 <span data-ttu-id="922b2-156">Если `resourcename` имеет `Nothing`значение, вызов <xref:System.IDisposable.Dispose%2A> не выполняется и исключение не создается.</span><span class="sxs-lookup"><span data-stu-id="922b2-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>  
  
## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="922b2-157">Структурированная обработка исключений в блоке using</span><span class="sxs-lookup"><span data-stu-id="922b2-157">Structured Exception Handling Within a Using Block</span></span>  
 <span data-ttu-id="922b2-158">Если необходимо выполнить обработку исключения, которое может возникнуть в `Using` блоке, можно добавить полный `Try`... `Finally` его создание.</span><span class="sxs-lookup"><span data-stu-id="922b2-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="922b2-159">Если необходимо решить, когда `Using` инструкция не сможет получить ресурс, можно проверить, имеет ли `resourcename` это значение `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="922b2-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="922b2-160">Структурированная обработка исключений вместо блока using</span><span class="sxs-lookup"><span data-stu-id="922b2-160">Structured Exception Handling Instead of a Using Block</span></span>  
 <span data-ttu-id="922b2-161">Если требуется более точный контроль за приобретением ресурсов или требуется дополнительный код в `Finally` блоке, можно `Using` переписать блок как `Try`... `Finally` создание.</span><span class="sxs-lookup"><span data-stu-id="922b2-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="922b2-162">В следующем примере показаны `Try` скелеты `Using` и конструкции, эквивалентные в приобретении и утилизации `resource`.</span><span class="sxs-lookup"><span data-stu-id="922b2-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>  
  
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
> <span data-ttu-id="922b2-163">Код внутри `Using` блока не должен назначать объект в `resourcename` другую переменную.</span><span class="sxs-lookup"><span data-stu-id="922b2-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="922b2-164">При выходе из `Using` блока ресурс удаляется, а другая переменная не может получить доступ к ресурсу, на который он указывает.</span><span class="sxs-lookup"><span data-stu-id="922b2-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="922b2-165">Пример</span><span class="sxs-lookup"><span data-stu-id="922b2-165">Example</span></span>  
 <span data-ttu-id="922b2-166">В следующем примере создается файл с именем log. txt и в него записываются две строки текста.</span><span class="sxs-lookup"><span data-stu-id="922b2-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="922b2-167">В этом примере также считывается тот же файл и отображаются строки текста.</span><span class="sxs-lookup"><span data-stu-id="922b2-167">The example also reads that same file and displays the lines of text.</span></span>  
  
 <span data-ttu-id="922b2-168">Поскольку классы <xref:System.IO.TextReader> <xref:System.IDisposable> и реализуют интерфейс, код может использовать `Using` инструкции, чтобы убедиться, что файл правильно закрыт после операций записи и чтения. <xref:System.IO.TextWriter></span><span class="sxs-lookup"><span data-stu-id="922b2-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>  
  
 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]  
  
## <a name="see-also"></a><span data-ttu-id="922b2-169">См. также</span><span class="sxs-lookup"><span data-stu-id="922b2-169">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="922b2-170">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="922b2-170">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="922b2-171">Практическое руководство. Удаление системного ресурса</span><span class="sxs-lookup"><span data-stu-id="922b2-171">How to: Dispose of a System Resource</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
