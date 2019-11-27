---
title: Объектные переменные
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: 7eb860bc732f923316b8ce1d7b94ecdb368bfec3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351781"
---
# <a name="object-variables-in-visual-basic"></a><span data-ttu-id="bf280-102">Объектные переменные в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bf280-102">Object Variables in Visual Basic</span></span>

<span data-ttu-id="bf280-103">Помимо непосредственного хранения значений, переменная может ссылаться на объект.</span><span class="sxs-lookup"><span data-stu-id="bf280-103">In addition to storing values directly, a variable can refer to an object.</span></span> <span data-ttu-id="bf280-104">Объект присваивается переменной по тем же причинам, что вы присваиваете переменной значение.</span><span class="sxs-lookup"><span data-stu-id="bf280-104">You assign an object to a variable for the same reasons you assign any value to a variable:</span></span>

- <span data-ttu-id="bf280-105">Имя переменной часто короче и проще в запоминании, чем полный путь к методам и свойствам, необходимым для доступа к самому объекту.</span><span class="sxs-lookup"><span data-stu-id="bf280-105">A variable name is often shorter and easier to remember than the full path of methods and properties necessary to access the object itself.</span></span>

- <span data-ttu-id="bf280-106">Использование переменной, ссылающейся на объект, является более эффективным, чем многократный доступ к самому объекту через необходимые методы или свойства.</span><span class="sxs-lookup"><span data-stu-id="bf280-106">Using a variable that refers to an object is more efficient than repeatedly accessing the object itself through the necessary methods or properties.</span></span>

- <span data-ttu-id="bf280-107">Вы можете изменить переменную, чтобы она ссылалась на другие объекты во время выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="bf280-107">You can change a variable to refer to other objects while your code is running.</span></span>

## <a name="making-code-shorter"></a><span data-ttu-id="bf280-108">Сокращение кода</span><span class="sxs-lookup"><span data-stu-id="bf280-108">Making Code Shorter</span></span>

<span data-ttu-id="bf280-109">Переменные объекта можно использовать для сокращения кода, который необходимо ввести.</span><span class="sxs-lookup"><span data-stu-id="bf280-109">You can use object variables to shorten the code you have to type.</span></span> <span data-ttu-id="bf280-110">В следующем примере используется полный путь к методам и свойствам для доступа к объекту <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="bf280-110">The following example uses the full path of methods and properties to access a <xref:System.Windows.Forms.Control> object.</span></span>

```vb
' Assume Me is a valid Form, or replace Me with a valid Form.
Me.ActiveForm.ActiveControl.Text = "Test"
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)
Me.ActiveForm.ActiveControl.Show()
```

<span data-ttu-id="bf280-111">Этот код можно сократить и ускорить выполнение, если для элемента управления используется объектная переменная.</span><span class="sxs-lookup"><span data-stu-id="bf280-111">You can shorten this code, and speed up execution, if you use an object variable for the control.</span></span> <span data-ttu-id="bf280-112">Необходимо объявить объектную переменную с конкретным классом, который вы хотите присвоить ему (в данном случае`Control`).</span><span class="sxs-lookup"><span data-stu-id="bf280-112">You should declare the object variable with the specific class that you intend to assign to it (`Control` in this case).</span></span> <span data-ttu-id="bf280-113">После присвоения объекта переменной ее можно обрабатывать точно так же, как и объект, к которому он относится.</span><span class="sxs-lookup"><span data-stu-id="bf280-113">Once you assign an object to the variable, you can treat it exactly the same as you treat the object to which it refers.</span></span> <span data-ttu-id="bf280-114">Можно задать или получить свойства объекта или использовать любой из его методов.</span><span class="sxs-lookup"><span data-stu-id="bf280-114">You can set or retrieve the properties of the object or use any of its methods.</span></span> <span data-ttu-id="bf280-115">В следующем примере используется объектная переменная для упрощения кода в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="bf280-115">The following example uses an object variable to simplify the code in the preceding example.</span></span>

```vb
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl
ctrlActv.Text = "Test"
ctrlActv.Location = New Point(100, 100)
ctrlActv.Show()
```

## <a name="see-also"></a><span data-ttu-id="bf280-116">См. также</span><span class="sxs-lookup"><span data-stu-id="bf280-116">See also</span></span>

- [<span data-ttu-id="bf280-117">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="bf280-117">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="bf280-118">Практическое руководство. Увеличение скорости доступа к объекту с длинным классификационным путем</span><span class="sxs-lookup"><span data-stu-id="bf280-118">How to: Speed Up Access to an Object with a Long Qualification Path</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)
- [<span data-ttu-id="bf280-119">Объявление объектной переменной</span><span class="sxs-lookup"><span data-stu-id="bf280-119">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="bf280-120">Присваивание объектных переменных</span><span class="sxs-lookup"><span data-stu-id="bf280-120">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="bf280-121">Значения объектных переменных</span><span class="sxs-lookup"><span data-stu-id="bf280-121">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
