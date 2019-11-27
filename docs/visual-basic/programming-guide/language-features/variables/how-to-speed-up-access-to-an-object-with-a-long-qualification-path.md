---
title: Практическое руководство. Увеличение скорости доступа к объекту с длинным классификационным путем
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: 83670ae6af0904156b08398024658cf504b7663f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346815"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a><span data-ttu-id="7f0e0-102">Практическое руководство. Увеличение скорости доступа к объекту с длинным классификационным путем (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f0e0-102">How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)</span></span>

<span data-ttu-id="7f0e0-103">При частом доступе к объекту, для которого требуется квалификация пути нескольких методов и свойств, можно ускорить код, не повторив классификационный путь.</span><span class="sxs-lookup"><span data-stu-id="7f0e0-103">If you frequently access an object that requires a qualification path of several methods and properties, you can speed up your code by not repeating the qualification path.</span></span>

<span data-ttu-id="7f0e0-104">Существует два способа избежать повторения пути для уточнения.</span><span class="sxs-lookup"><span data-stu-id="7f0e0-104">There are two ways you can avoid repeating the qualification path.</span></span> <span data-ttu-id="7f0e0-105">Объект можно назначить переменной или использовать в блоке `With`...`End With`.</span><span class="sxs-lookup"><span data-stu-id="7f0e0-105">You can assign the object to a variable, or you can use it in a `With`...`End With` block.</span></span>

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a><span data-ttu-id="7f0e0-106">Ускорение доступа к сильно известному объекту путем присвоения его переменной</span><span class="sxs-lookup"><span data-stu-id="7f0e0-106">To speed up access to a heavily qualified object by assigning it to a variable</span></span>

1. <span data-ttu-id="7f0e0-107">Объявите переменную типа объекта, к которому часто осуществляется доступ.</span><span class="sxs-lookup"><span data-stu-id="7f0e0-107">Declare a variable of the type of the object that you are accessing frequently.</span></span> <span data-ttu-id="7f0e0-108">Укажите классификационный путь в части инициализации объявления.</span><span class="sxs-lookup"><span data-stu-id="7f0e0-108">Specify the qualification path in the initialization part of the declaration.</span></span>

    ```vb
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl
    ```

2. <span data-ttu-id="7f0e0-109">Используйте переменную для доступа к членам объекта.</span><span class="sxs-lookup"><span data-stu-id="7f0e0-109">Use the variable to access the object's members.</span></span>

    ```vb
    ctrlActv.Text = "Test"
    ctrlActv.Location = New Point(100, 100)
    ctrlActv.Show()
    ```

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a><span data-ttu-id="7f0e0-110">Для ускорения доступа к сильно известному объекту с помощью метода with... Конец блока</span><span class="sxs-lookup"><span data-stu-id="7f0e0-110">To speed up access to a heavily qualified object by using a With...End With block</span></span>

1. <span data-ttu-id="7f0e0-111">Укажите классификационный путь в операторе `With`.</span><span class="sxs-lookup"><span data-stu-id="7f0e0-111">Put the qualification path in a `With` statement.</span></span>

    ```vb
    With someForm.ActiveForm.ActiveControl
    ```

2. <span data-ttu-id="7f0e0-112">Получите доступ к членам объекта внутри блока `With` перед инструкцией `End With`.</span><span class="sxs-lookup"><span data-stu-id="7f0e0-112">Access the object's members inside the `With` block, before the `End With` statement.</span></span>

    ```vb
        .Text = "Test"
        .Location = New Point(100, 100)
        .Show()
    End With
    ```

## <a name="see-also"></a><span data-ttu-id="7f0e0-113">См. также</span><span class="sxs-lookup"><span data-stu-id="7f0e0-113">See also</span></span>

- [<span data-ttu-id="7f0e0-114">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="7f0e0-114">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="7f0e0-115">Оператор With...End With</span><span class="sxs-lookup"><span data-stu-id="7f0e0-115">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
