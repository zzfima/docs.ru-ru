---
title: Как выполнить Вызов метода делегата (Visual Basic)
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: 42d56fca7e1d33c071db2e7e38935aa00caa5b7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676215"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a><span data-ttu-id="e9729-102">Как выполнить Вызов метода делегата (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9729-102">How to: Invoke a Delegate Method (Visual Basic)</span></span>
<span data-ttu-id="e9729-103">В этом примере показано, как связать метод с делегатом, а затем вызвать метод через делегат.</span><span class="sxs-lookup"><span data-stu-id="e9729-103">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="e9729-104">Создание делегата и согласование процедур</span><span class="sxs-lookup"><span data-stu-id="e9729-104">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="e9729-105">Создать делегат с именем `MySubDelegate`.</span><span class="sxs-lookup"><span data-stu-id="e9729-105">Create a delegate named `MySubDelegate`.</span></span>  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  <span data-ttu-id="e9729-106">Объявите класс, который содержит метод с сигнатурой делегата.</span><span class="sxs-lookup"><span data-stu-id="e9729-106">Declare a class that contains a method with the same signature as the delegate.</span></span>  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  <span data-ttu-id="e9729-107">Определите метод, который создает экземпляр делегата и вызывает метод, связанный с делегатом, вызвав встроенный `Invoke` метод.</span><span class="sxs-lookup"><span data-stu-id="e9729-107">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span></span>  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e9729-108">См. также</span><span class="sxs-lookup"><span data-stu-id="e9729-108">See also</span></span>

- [<span data-ttu-id="e9729-109">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="e9729-109">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="e9729-110">Делегаты</span><span class="sxs-lookup"><span data-stu-id="e9729-110">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="e9729-111">События</span><span class="sxs-lookup"><span data-stu-id="e9729-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="e9729-112">Многопоточные приложения</span><span class="sxs-lookup"><span data-stu-id="e9729-112">Multithreaded Applications</span></span>](../../../../standard/threading/using-threads-and-threading.md)
