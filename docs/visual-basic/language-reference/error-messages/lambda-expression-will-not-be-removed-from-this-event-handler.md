---
title: Лямбда-выражение не будет удалено из этого обработчика событий
ms.date: 07/20/2015
f1_keywords:
- bc42326
- vbc42326
helpviewer_keywords:
- BC42326
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
ms.openlocfilehash: 20e83306925e91e579aca52f2e7c209c8c686dee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946631"
---
# <a name="lambda-expression-will-not-be-removed-from-this-event-handler"></a><span data-ttu-id="baf75-102">Лямбда-выражение не будет удалено из этого обработчика событий</span><span class="sxs-lookup"><span data-stu-id="baf75-102">Lambda expression will not be removed from this event handler</span></span>
<span data-ttu-id="baf75-103">Лямбда-выражение не удаляется из этого обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="baf75-103">Lambda expression will not be removed from this event handler.</span></span> <span data-ttu-id="baf75-104">Назначьте лямбда-выражение переменной и используйте переменную для добавления и удаления события.</span><span class="sxs-lookup"><span data-stu-id="baf75-104">Assign the lambda expression to a variable and use the variable to add and remove the event.</span></span>  
  
 <span data-ttu-id="baf75-105">Когда лямбда-выражения используются с обработчиками событий, могут отсутствовать ожидаемое поведение.</span><span class="sxs-lookup"><span data-stu-id="baf75-105">When lambda expressions are used with event handlers, you may not see the behavior you expect.</span></span> <span data-ttu-id="baf75-106">Компилятор создает новый метод для каждого определения лямбда-выражения, даже если они идентичны.</span><span class="sxs-lookup"><span data-stu-id="baf75-106">The compiler generates a new method for each lambda expression definition, even if they are identical.</span></span> <span data-ttu-id="baf75-107">Таким образом, следующий код отображает `False`.</span><span class="sxs-lookup"><span data-stu-id="baf75-107">Therefore, the following code displays `False`.</span></span>  
  
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
  
 <span data-ttu-id="baf75-108">Когда лямбда-выражения используются с обработчиками событий, это может привести к непредвиденным результатам.</span><span class="sxs-lookup"><span data-stu-id="baf75-108">When lambda expressions are used with event handlers, this may cause unexpected results.</span></span> <span data-ttu-id="baf75-109">В следующем примере лямбда-выражение добавленные `AddHandler` не удалялся `RemoveHandler` инструкции.</span><span class="sxs-lookup"><span data-stu-id="baf75-109">In the following example, the lambda expression added by `AddHandler` is not removed by the `RemoveHandler` statement.</span></span>  
  
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
  
 <span data-ttu-id="baf75-110">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="baf75-110">By default, this message is a warning.</span></span> <span data-ttu-id="baf75-111">Дополнительные сведения о скрытии предупреждений и обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="baf75-111">For more information about how to hide warnings or treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="baf75-112">**Идентификатор ошибки:** BC42326</span><span class="sxs-lookup"><span data-stu-id="baf75-112">**Error ID:** BC42326</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="baf75-113">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="baf75-113">To correct this error</span></span>  
  
- <span data-ttu-id="baf75-114">Чтобы избежать предупреждения и удалить лямбда-выражение, назначьте лямбда-выражение переменной и используйте переменную в обоих `AddHandler` и `RemoveHandler` инструкции, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="baf75-114">To avoid the warning and remove the lambda expression, assign the lambda expression to a variable and use the variable in both the `AddHandler` and `RemoveHandler` statements, as shown in the following example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="baf75-115">См. также</span><span class="sxs-lookup"><span data-stu-id="baf75-115">See also</span></span>

- [<span data-ttu-id="baf75-116">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="baf75-116">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="baf75-117">Неявное преобразование делегата</span><span class="sxs-lookup"><span data-stu-id="baf75-117">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="baf75-118">События</span><span class="sxs-lookup"><span data-stu-id="baf75-118">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
