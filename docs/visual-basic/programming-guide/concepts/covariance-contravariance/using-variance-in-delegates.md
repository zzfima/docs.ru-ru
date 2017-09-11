---
title: "Использование вариативности в делегатах (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 620fd61000e42d68f566e441d023d73a036000ae
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="using-variance-in-delegates-visual-basic"></a><span data-ttu-id="aae76-102">Использование вариативности в делегатах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aae76-102">Using Variance in Delegates (Visual Basic)</span></span>
<span data-ttu-id="aae76-103">При назначении метода делегату, *Ковариация* и *контравариация* обеспечивают гибкость сопоставления типа делегата с сигнатурой метода.</span><span class="sxs-lookup"><span data-stu-id="aae76-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="aae76-104">Ковариация позволяет методу иметь тип возвращаемого значения, более производный, чем указано в делегате.</span><span class="sxs-lookup"><span data-stu-id="aae76-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="aae76-105">Контрвариация использовать метод с типами параметров, которые являются менее производным, чем у типа делегата.</span><span class="sxs-lookup"><span data-stu-id="aae76-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="aae76-106">Пример 1: ковариация</span><span class="sxs-lookup"><span data-stu-id="aae76-106">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="aae76-107">Описание</span><span class="sxs-lookup"><span data-stu-id="aae76-107">Description</span></span>  
 <span data-ttu-id="aae76-108">В этом примере демонстрируется использование делегатов с методами, типы возвращаемых значений, которые являются производными от типа возвращаемого значения в сигнатуре делегата.</span><span class="sxs-lookup"><span data-stu-id="aae76-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="aae76-109">Тип данных, возвращаемый `DogsHandler` типа `Dogs`, который является производным от `Mammals` типа, определенного в делегате.</span><span class="sxs-lookup"><span data-stu-id="aae76-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="aae76-110">Код</span><span class="sxs-lookup"><span data-stu-id="aae76-110">Code</span></span>  
  
```vb  
Class Mammals  
End Class  
  
Class Dogs  
    Inherits Mammals  
End Class  
Class Test  
    Public Delegate Function HandlerMethod() As Mammals  
    Public Shared Function MammalsHandler() As Mammals  
        Return Nothing  
    End Function  
    Public Shared Function DogsHandler() As Dogs  
        Return Nothing  
    End Function  
    Sub Test()  
        Dim handlerMammals As HandlerMethod = AddressOf MammalsHandler  
        ' Covariance enables this assignment.  
        Dim handlerDogs As HandlerMethod = AddressOf DogsHandler  
    End Sub  
End Class  
```  
  
## <a name="example-2-contravariance"></a><span data-ttu-id="aae76-111">Пример 2: контрвариация</span><span class="sxs-lookup"><span data-stu-id="aae76-111">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="aae76-112">Описание</span><span class="sxs-lookup"><span data-stu-id="aae76-112">Description</span></span>  
 <span data-ttu-id="aae76-113">В этом примере демонстрируется использование делегатов с методами, параметры типа которых являются базовыми типами типа параметра подписи делегата.</span><span class="sxs-lookup"><span data-stu-id="aae76-113">This example demonstrates how delegates can be used with methods that have parameters of a type that are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="aae76-114">Контравариация можно использовать один обработчик событий вместо отдельных обработчиков.</span><span class="sxs-lookup"><span data-stu-id="aae76-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="aae76-115">Например, можно создать обработчик событий, который принимает `EventArgs` входной параметр и использовать его с `Button.MouseClick` событие, которое отправляет `MouseEventArgs` типа в качестве параметра, а также с `TextBox.KeyDown` событие, которое отправляет `KeyEventArgs` параметр.</span><span class="sxs-lookup"><span data-stu-id="aae76-115">For example, you can create an event handler that accepts an `EventArgs` input parameter and use it with a `Button.MouseClick` event that sends a `MouseEventArgs` type as a parameter, and also with a `TextBox.KeyDown` event that sends a `KeyEventArgs` parameter.</span></span>  
  
### <a name="code"></a><span data-ttu-id="aae76-116">Код</span><span class="sxs-lookup"><span data-stu-id="aae76-116">Code</span></span>  
  
```vb  
' Event hander that accepts a parameter of the EventArgs type.  
Private Sub MultiHandler(ByVal sender As Object,  
                         ByVal e As System.EventArgs)  
    Label1.Text = DateTime.Now  
End Sub  
  
Private Sub Form1_Load(ByVal sender As System.Object,  
    ByVal e As System.EventArgs) Handles MyBase.Load  
  
    ' You can use a method that has an EventArgs parameter,  
    ' although the event expects the KeyEventArgs parameter.  
    AddHandler Button1.KeyDown, AddressOf MultiHandler  
  
    ' You can use the same method   
    ' for the event that expects the MouseEventArgs parameter.  
    AddHandler Button1.MouseClick, AddressOf MultiHandler  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="aae76-117">См. также</span><span class="sxs-lookup"><span data-stu-id="aae76-117">See Also</span></span>  
 <span data-ttu-id="aae76-118">[Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) </span><span class="sxs-lookup"><span data-stu-id="aae76-118">[Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) </span></span>  
<span data-ttu-id="aae76-119"> [Использование вариативности в Func и Action универсальные делегаты (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span><span class="sxs-lookup"><span data-stu-id="aae76-119"> [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span></span>
