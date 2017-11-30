---
title: "Объектные переменные в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 44689d649a381618e5d6c934deb2b7b9bea463ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="object-variables-in-visual-basic"></a><span data-ttu-id="555e2-102">Объектные переменные в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="555e2-102">Object Variables in Visual Basic</span></span>
<span data-ttu-id="555e2-103">Помимо хранить значения, переменные могут ссылаться на объект.</span><span class="sxs-lookup"><span data-stu-id="555e2-103">In addition to storing values directly, a variable can refer to an object.</span></span> <span data-ttu-id="555e2-104">Объект присваивается переменной по тем же причинам, которые можно присвоить любое значение переменной:</span><span class="sxs-lookup"><span data-stu-id="555e2-104">You assign an object to a variable for the same reasons you assign any value to a variable:</span></span>  
  
-   <span data-ttu-id="555e2-105">Имя переменной является часто короче и проще запомнить, чем полный путь методов и свойств, необходимых для доступа к самому объекту.</span><span class="sxs-lookup"><span data-stu-id="555e2-105">A variable name is often shorter and easier to remember than the full path of methods and properties necessary to access the object itself.</span></span>  
  
-   <span data-ttu-id="555e2-106">С помощью переменной, которая ссылается на объект является более эффективным, чем повторяющееся обращение к самому объекту через необходимые методы или свойства.</span><span class="sxs-lookup"><span data-stu-id="555e2-106">Using a variable that refers to an object is more efficient than repeatedly accessing the object itself through the necessary methods or properties.</span></span>  
  
-   <span data-ttu-id="555e2-107">Можно изменить переменную для ссылки на другие объекты во время выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="555e2-107">You can change a variable to refer to other objects while your code is running.</span></span>  
  
## <a name="making-code-shorter"></a><span data-ttu-id="555e2-108">Уменьшение размера кода</span><span class="sxs-lookup"><span data-stu-id="555e2-108">Making Code Shorter</span></span>  
 <span data-ttu-id="555e2-109">Объектные переменные можно использовать для сокращения вводимого кода.</span><span class="sxs-lookup"><span data-stu-id="555e2-109">You can use object variables to shorten the code you have to type.</span></span> <span data-ttu-id="555e2-110">В следующем примере используется полное методы и свойства для доступа к <xref:System.Windows.Forms.Control> объекта.</span><span class="sxs-lookup"><span data-stu-id="555e2-110">The following example uses the full path of methods and properties to access a <xref:System.Windows.Forms.Control> object.</span></span>  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 <span data-ttu-id="555e2-111">Можно сократить этот код и ускорения выполнения, если объектная переменная используется для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="555e2-111">You can shorten this code, and speed up execution, if you use an object variable for the control.</span></span> <span data-ttu-id="555e2-112">Следует объявить переменную объекта в определенном классе, который требуется присвоить его (`Control` в данном случае).</span><span class="sxs-lookup"><span data-stu-id="555e2-112">You should declare the object variable with the specific class that you intend to assign to it (`Control` in this case).</span></span> <span data-ttu-id="555e2-113">После того как объект переменной, с ней можно работать точно так же, как с объектом, к которому он относится.</span><span class="sxs-lookup"><span data-stu-id="555e2-113">Once you assign an object to the variable, you can treat it exactly the same as you treat the object to which it refers.</span></span> <span data-ttu-id="555e2-114">Можно задать или получить свойства объекта или использовать любой из его методов.</span><span class="sxs-lookup"><span data-stu-id="555e2-114">You can set or retrieve the properties of the object or use any of its methods.</span></span> <span data-ttu-id="555e2-115">В следующем примере переменной объекта для упрощения кода в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="555e2-115">The following example uses an object variable to simplify the code in the preceding example.</span></span>  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## <a name="see-also"></a><span data-ttu-id="555e2-116">См. также</span><span class="sxs-lookup"><span data-stu-id="555e2-116">See Also</span></span>  
 [<span data-ttu-id="555e2-117">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="555e2-117">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="555e2-118">Практическое руководство. Увеличение скорости доступа к объекту с длинным классификационным путем</span><span class="sxs-lookup"><span data-stu-id="555e2-118">How to: Speed Up Access to an Object with a Long Qualification Path</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)  
 [<span data-ttu-id="555e2-119">Объявление объектной переменной</span><span class="sxs-lookup"><span data-stu-id="555e2-119">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="555e2-120">Присваивание объектных переменных</span><span class="sxs-lookup"><span data-stu-id="555e2-120">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="555e2-121">Значения объектных переменных</span><span class="sxs-lookup"><span data-stu-id="555e2-121">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
