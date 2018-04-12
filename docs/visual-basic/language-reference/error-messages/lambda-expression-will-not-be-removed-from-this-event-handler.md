---
title: Лямбда-выражение не будет удалено из этого обработчика событий
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42326
- vbc42326
helpviewer_keywords:
- BC42326
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1a4c57d1f8f41d2d9ebb645d3f2628c32a2c4e4c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="lambda-expression-will-not-be-removed-from-this-event-handler"></a><span data-ttu-id="23982-102">Лямбда-выражение не будет удалено из этого обработчика событий</span><span class="sxs-lookup"><span data-stu-id="23982-102">Lambda expression will not be removed from this event handler</span></span>
<span data-ttu-id="23982-103">Лямбда-выражение не удаляется из этого обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="23982-103">Lambda expression will not be removed from this event handler.</span></span> <span data-ttu-id="23982-104">Присвойте переменной лямбда-выражение и используйте переменную для добавления и удаления события.</span><span class="sxs-lookup"><span data-stu-id="23982-104">Assign the lambda expression to a variable and use the variable to add and remove the event.</span></span>  
  
 <span data-ttu-id="23982-105">При использовании лямбда-выражения с обработчиками событий, могут не отображаться ожидаемое поведение.</span><span class="sxs-lookup"><span data-stu-id="23982-105">When lambda expressions are used with event handlers, you may not see the behavior you expect.</span></span> <span data-ttu-id="23982-106">Компилятор создает новый метод для каждого определения лямбда-выражения, даже если они идентичны.</span><span class="sxs-lookup"><span data-stu-id="23982-106">The compiler generates a new method for each lambda expression definition, even if they are identical.</span></span> <span data-ttu-id="23982-107">Таким образом, следующий код отображает `False`.</span><span class="sxs-lookup"><span data-stu-id="23982-107">Therefore, the following code displays `False`.</span></span>  
  
```vb  
Module Module1  
  
    Sub Main()  
        Dim fun1 As ChangeInteger = Function(p As Integer) p + 1  
        Dim fun2 As ChangeInteger = Function(p As Integer) p + 1  
        Console.WriteLine(fun1 = fun2)  
    End Sub  
  
    Delegate Function ChangeInteger(ByVal x As Integer) As Integer  
  
End Module  
```  
  
 <span data-ttu-id="23982-108">При использовании лямбда-выражения с обработчиками событий, это может привести к непредвиденным результатам.</span><span class="sxs-lookup"><span data-stu-id="23982-108">When lambda expressions are used with event handlers, this may cause unexpected results.</span></span> <span data-ttu-id="23982-109">В следующем примере лямбда-выражения, добавленные `AddHandler` не удаляется с `RemoveHandler` инструкции.</span><span class="sxs-lookup"><span data-stu-id="23982-109">In the following example, the lambda expression added by `AddHandler` is not removed by the `RemoveHandler` statement.</span></span>  
  
```vb  
Module Module1  
  
    Event ProcessInteger(ByVal x As Integer)  
  
    Sub Main()  
  
        ' The following line adds one listener to the event.  
        AddHandler ProcessInteger, Function(m As Integer) m  
  
        ' The following statement searches the current listeners   
        ' for a match to remove. However, this lambda is not the same  
        ' as the previous one, so nothing is removed.  
        RemoveHandler ProcessInteger, Function(m As Integer) m  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="23982-110">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="23982-110">By default, this message is a warning.</span></span> <span data-ttu-id="23982-111">Дополнительные сведения о том, как скрыть предупреждения или как рассматривать предупреждения как ошибки см. в разделе [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="23982-111">For more information about how to hide warnings or treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="23982-112">**Идентификатор ошибки:** BC42326</span><span class="sxs-lookup"><span data-stu-id="23982-112">**Error ID:** BC42326</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="23982-113">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="23982-113">To correct this error</span></span>  
  
-   <span data-ttu-id="23982-114">Чтобы избежать этого предупреждения и удалить лямбда-выражение, присвойте переменной лямбда-выражение и используйте переменную в обоих `AddHandler` и `RemoveHandler` инструкции, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="23982-114">To avoid the warning and remove the lambda expression, assign the lambda expression to a variable and use the variable in both the `AddHandler` and `RemoveHandler` statements, as shown in the following example.</span></span>  
  
```vb  
Module Module1  
  
    Event ProcessInteger(ByVal x As Integer)  
  
    Dim PrintHandler As ProcessIntegerEventHandler  
  
    Sub Main()  
  
        ' Assign the lambda expression to a variable.  
        PrintHandler = Function(m As Integer) m  
  
        ' Use the variable to add the listener.  
        AddHandler ProcessInteger, PrintHandler  
  
        ' Use the variable again when you want to remove the listener.  
        RemoveHandler ProcessInteger, PrintHandler  
  
    End Sub  
End Module  
```  
  
## <a name="see-also"></a><span data-ttu-id="23982-115">См. также</span><span class="sxs-lookup"><span data-stu-id="23982-115">See Also</span></span>  
 [<span data-ttu-id="23982-116">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="23982-116">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="23982-117">Неявное преобразование делегата</span><span class="sxs-lookup"><span data-stu-id="23982-117">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [<span data-ttu-id="23982-118">События</span><span class="sxs-lookup"><span data-stu-id="23982-118">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
