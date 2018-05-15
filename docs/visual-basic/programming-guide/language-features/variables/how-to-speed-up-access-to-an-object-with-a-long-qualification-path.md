---
title: Практическое руководство. Увеличение скорости доступа к объекту с длинным классификационным путем (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: d52d13feb0f85065c0623b5937f558b841c036dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a><span data-ttu-id="51486-102">Практическое руководство. Увеличение скорости доступа к объекту с длинным классификационным путем (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51486-102">How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)</span></span>
<span data-ttu-id="51486-103">При частом обращении к объект, который требуется указать путь квалификации несколько методов и свойств, можно ускорить код, не повторяя классификационный путь.</span><span class="sxs-lookup"><span data-stu-id="51486-103">If you frequently access an object that requires a qualification path of several methods and properties, you can speed up your code by not repeating the qualification path.</span></span>  
  
 <span data-ttu-id="51486-104">Повторение классификационного пути можно избежать двумя способами.</span><span class="sxs-lookup"><span data-stu-id="51486-104">There are two ways you can avoid repeating the qualification path.</span></span> <span data-ttu-id="51486-105">Объект может быть присвоен переменной, или можно использовать его в `With`... `End With` блок.</span><span class="sxs-lookup"><span data-stu-id="51486-105">You can assign the object to a variable, or you can use it in a `With`...`End With` block.</span></span>  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a><span data-ttu-id="51486-106">Для ускорения доступа к объекту сильно полное путем присвоения переменной</span><span class="sxs-lookup"><span data-stu-id="51486-106">To speed up access to a heavily qualified object by assigning it to a variable</span></span>  
  
1.  <span data-ttu-id="51486-107">Объявите переменную типа объекта, к которому часто осуществляется доступ.</span><span class="sxs-lookup"><span data-stu-id="51486-107">Declare a variable of the type of the object that you are accessing frequently.</span></span> <span data-ttu-id="51486-108">Укажите классификационный путь в части инициализации объявления.</span><span class="sxs-lookup"><span data-stu-id="51486-108">Specify the qualification path in the initialization part of the declaration.</span></span>  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2.  <span data-ttu-id="51486-109">Используйте переменную для доступа к членам объекта.</span><span class="sxs-lookup"><span data-stu-id="51486-109">Use the variable to access the object's members.</span></span>  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a><span data-ttu-id="51486-110">Для ускорения доступа к сильно уточненное с помощью With... End With-блок</span><span class="sxs-lookup"><span data-stu-id="51486-110">To speed up access to a heavily qualified object by using a With...End With block</span></span>  
  
1.  <span data-ttu-id="51486-111">Поместите классификационный пусть `With` инструкции.</span><span class="sxs-lookup"><span data-stu-id="51486-111">Put the qualification path in a `With` statement.</span></span>  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2.  <span data-ttu-id="51486-112">Доступ к членам объекта внутри `With` блокировать перед `End With` инструкции.</span><span class="sxs-lookup"><span data-stu-id="51486-112">Access the object's members inside the `With` block, before the `End With` statement.</span></span>  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="51486-113">См. также</span><span class="sxs-lookup"><span data-stu-id="51486-113">See Also</span></span>  
 [<span data-ttu-id="51486-114">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="51486-114">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="51486-115">Оператор With...End With</span><span class="sxs-lookup"><span data-stu-id="51486-115">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
