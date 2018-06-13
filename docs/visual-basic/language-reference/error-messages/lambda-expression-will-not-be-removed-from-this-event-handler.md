---
title: Лямбда-выражение не будет удалено из этого обработчика событий
ms.date: 07/20/2015
f1_keywords:
- bc42326
- vbc42326
helpviewer_keywords:
- BC42326
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
ms.openlocfilehash: 69228bbb5f659a8e500e85dea1ef87cb43b0356e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590171"
---
# <a name="lambda-expression-will-not-be-removed-from-this-event-handler"></a><span data-ttu-id="2c28f-102">Лямбда-выражение не будет удалено из этого обработчика событий</span><span class="sxs-lookup"><span data-stu-id="2c28f-102">Lambda expression will not be removed from this event handler</span></span>
<span data-ttu-id="2c28f-103">Лямбда-выражение не удаляется из этого обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="2c28f-103">Lambda expression will not be removed from this event handler.</span></span> <span data-ttu-id="2c28f-104">Присвойте переменной лямбда-выражение и используйте переменную для добавления и удаления события.</span><span class="sxs-lookup"><span data-stu-id="2c28f-104">Assign the lambda expression to a variable and use the variable to add and remove the event.</span></span>  
  
 <span data-ttu-id="2c28f-105">При использовании лямбда-выражения с обработчиками событий, могут не отображаться ожидаемое поведение.</span><span class="sxs-lookup"><span data-stu-id="2c28f-105">When lambda expressions are used with event handlers, you may not see the behavior you expect.</span></span> <span data-ttu-id="2c28f-106">Компилятор создает новый метод для каждого определения лямбда-выражения, даже если они идентичны.</span><span class="sxs-lookup"><span data-stu-id="2c28f-106">The compiler generates a new method for each lambda expression definition, even if they are identical.</span></span> <span data-ttu-id="2c28f-107">Таким образом, следующий код отображает `False`.</span><span class="sxs-lookup"><span data-stu-id="2c28f-107">Therefore, the following code displays `False`.</span></span>  
  
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
  
 <span data-ttu-id="2c28f-108">При использовании лямбда-выражения с обработчиками событий, это может привести к непредвиденным результатам.</span><span class="sxs-lookup"><span data-stu-id="2c28f-108">When lambda expressions are used with event handlers, this may cause unexpected results.</span></span> <span data-ttu-id="2c28f-109">В следующем примере лямбда-выражения, добавленные `AddHandler` не удаляется с `RemoveHandler` инструкции.</span><span class="sxs-lookup"><span data-stu-id="2c28f-109">In the following example, the lambda expression added by `AddHandler` is not removed by the `RemoveHandler` statement.</span></span>  
  
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
  
 <span data-ttu-id="2c28f-110">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="2c28f-110">By default, this message is a warning.</span></span> <span data-ttu-id="2c28f-111">Дополнительные сведения о том, как скрыть предупреждения или как рассматривать предупреждения как ошибки см. в разделе [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="2c28f-111">For more information about how to hide warnings or treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="2c28f-112">**Идентификатор ошибки:** BC42326</span><span class="sxs-lookup"><span data-stu-id="2c28f-112">**Error ID:** BC42326</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2c28f-113">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="2c28f-113">To correct this error</span></span>  
  
-   <span data-ttu-id="2c28f-114">Чтобы избежать этого предупреждения и удалить лямбда-выражение, присвойте переменной лямбда-выражение и используйте переменную в обоих `AddHandler` и `RemoveHandler` инструкции, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2c28f-114">To avoid the warning and remove the lambda expression, assign the lambda expression to a variable and use the variable in both the `AddHandler` and `RemoveHandler` statements, as shown in the following example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2c28f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2c28f-115">See Also</span></span>  
 [<span data-ttu-id="2c28f-116">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="2c28f-116">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="2c28f-117">Неявное преобразование делегата</span><span class="sxs-lookup"><span data-stu-id="2c28f-117">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [<span data-ttu-id="2c28f-118">События</span><span class="sxs-lookup"><span data-stu-id="2c28f-118">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
