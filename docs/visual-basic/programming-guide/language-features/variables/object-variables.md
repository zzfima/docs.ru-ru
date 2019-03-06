---
title: Объектные переменные в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: cc5be13293a89e73d1790e94a99d7936f1711e12
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352975"
---
# <a name="object-variables-in-visual-basic"></a><span data-ttu-id="ea9cd-102">Объектные переменные в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ea9cd-102">Object Variables in Visual Basic</span></span>

<span data-ttu-id="ea9cd-103">В дополнение к хранить значения, переменные могут ссылаться на объект.</span><span class="sxs-lookup"><span data-stu-id="ea9cd-103">In addition to storing values directly, a variable can refer to an object.</span></span> <span data-ttu-id="ea9cd-104">Объект присваивается переменной по тем же причинам, которые можно присвоить любое значение переменной:</span><span class="sxs-lookup"><span data-stu-id="ea9cd-104">You assign an object to a variable for the same reasons you assign any value to a variable:</span></span>

- <span data-ttu-id="ea9cd-105">Имя переменной часто короче и легче для запоминания, чем полный путь к методы и свойства, необходимые для доступа к самому объекту.</span><span class="sxs-lookup"><span data-stu-id="ea9cd-105">A variable name is often shorter and easier to remember than the full path of methods and properties necessary to access the object itself.</span></span>

- <span data-ttu-id="ea9cd-106">Использование переменной, которая ссылается на объект является более эффективным, чем несколько раз доступ к самому объекту через необходимые методы или свойства.</span><span class="sxs-lookup"><span data-stu-id="ea9cd-106">Using a variable that refers to an object is more efficient than repeatedly accessing the object itself through the necessary methods or properties.</span></span>

- <span data-ttu-id="ea9cd-107">Можно изменить переменную для ссылки на другие объекты во время выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="ea9cd-107">You can change a variable to refer to other objects while your code is running.</span></span>

## <a name="making-code-shorter"></a><span data-ttu-id="ea9cd-108">Уменьшение размера кода</span><span class="sxs-lookup"><span data-stu-id="ea9cd-108">Making Code Shorter</span></span>

<span data-ttu-id="ea9cd-109">Объектные переменные можно использовать для сокращения кода необходимо вводить.</span><span class="sxs-lookup"><span data-stu-id="ea9cd-109">You can use object variables to shorten the code you have to type.</span></span> <span data-ttu-id="ea9cd-110">В следующем примере используется полный путь к методы и свойства для доступа к <xref:System.Windows.Forms.Control> объекта.</span><span class="sxs-lookup"><span data-stu-id="ea9cd-110">The following example uses the full path of methods and properties to access a <xref:System.Windows.Forms.Control> object.</span></span>

```vb
' Assume Me is a valid Form, or replace Me with a valid Form.
Me.ActiveForm.ActiveControl.Text = "Test"
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)
Me.ActiveForm.ActiveControl.Show()
```

<span data-ttu-id="ea9cd-111">Можно сократить этот код и ускорить его выполнение при использовании переменной объекта для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ea9cd-111">You can shorten this code, and speed up execution, if you use an object variable for the control.</span></span> <span data-ttu-id="ea9cd-112">Следует объявить переменную объекта с определенный класс, который планируется назначить для него (`Control` в данном случае).</span><span class="sxs-lookup"><span data-stu-id="ea9cd-112">You should declare the object variable with the specific class that you intend to assign to it (`Control` in this case).</span></span> <span data-ttu-id="ea9cd-113">После того как объект переменной, с ней можно работать точно так же, как обрабатывать объект, к которому он относится.</span><span class="sxs-lookup"><span data-stu-id="ea9cd-113">Once you assign an object to the variable, you can treat it exactly the same as you treat the object to which it refers.</span></span> <span data-ttu-id="ea9cd-114">Можно задать или получить свойства объекта или использовать любой из его методов.</span><span class="sxs-lookup"><span data-stu-id="ea9cd-114">You can set or retrieve the properties of the object or use any of its methods.</span></span> <span data-ttu-id="ea9cd-115">В следующем примере переменной объекта используется для упрощения кода в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="ea9cd-115">The following example uses an object variable to simplify the code in the preceding example.</span></span>

```vb
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl
ctrlActv.Text = "Test"
ctrlActv.Location = New Point(100, 100)
ctrlActv.Show()
```

## <a name="see-also"></a><span data-ttu-id="ea9cd-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ea9cd-116">See also</span></span>

- [<span data-ttu-id="ea9cd-117">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="ea9cd-117">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="ea9cd-118">Практическое руководство. Увеличение скорости доступа к объекту с длинным классификационным путем</span><span class="sxs-lookup"><span data-stu-id="ea9cd-118">How to: Speed Up Access to an Object with a Long Qualification Path</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)
- [<span data-ttu-id="ea9cd-119">Объявление объектной переменной</span><span class="sxs-lookup"><span data-stu-id="ea9cd-119">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="ea9cd-120">Присваивание объектных переменных</span><span class="sxs-lookup"><span data-stu-id="ea9cd-120">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="ea9cd-121">Значения объектных переменных</span><span class="sxs-lookup"><span data-stu-id="ea9cd-121">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
