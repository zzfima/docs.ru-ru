---
title: Практическое руководство. Ссылка на текущий экземпляр объекта (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 6c216dbc59bcad7a9f24bb01f856c3d29c288dbb
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005654"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="90829-102">Практическое руководство. Ссылка на текущий экземпляр объекта (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90829-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>
<span data-ttu-id="90829-103">*Текущим экземпляром* объекта является экземпляр, в котором в данный момент выполняется код.</span><span class="sxs-lookup"><span data-stu-id="90829-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="90829-104">Для ссылки на текущий экземпляр используется ключевое слово `Me`.</span><span class="sxs-lookup"><span data-stu-id="90829-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="90829-105">Ссылка на текущий экземпляр</span><span class="sxs-lookup"><span data-stu-id="90829-105">To refer to the current instance</span></span>  
  
- <span data-ttu-id="90829-106">Используйте ключевое слово `Me`, где обычно используется имя объектной переменной.</span><span class="sxs-lookup"><span data-stu-id="90829-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="90829-107">Хотя `Me` ведет себя как объектная переменная, вы не можете объявить ее или присвоить ей ничего.</span><span class="sxs-lookup"><span data-stu-id="90829-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="90829-108">`Me` всегда относится к текущему экземпляру.</span><span class="sxs-lookup"><span data-stu-id="90829-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90829-109">См. также</span><span class="sxs-lookup"><span data-stu-id="90829-109">See also</span></span>

- [<span data-ttu-id="90829-110">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="90829-110">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="90829-111">Присваивание объектных переменных</span><span class="sxs-lookup"><span data-stu-id="90829-111">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="90829-112">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="90829-112">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
