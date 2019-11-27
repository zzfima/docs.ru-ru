---
title: Практическое руководство. Ссылка на текущий экземпляр объекта
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 62b22a54904a45380052d3d81d9415517d4f8d3b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346885"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="d777e-102">Практическое руководство. Ссылка на текущий экземпляр объекта (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d777e-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>
<span data-ttu-id="d777e-103">*Текущим экземпляром* объекта является экземпляр, в котором в данный момент выполняется код.</span><span class="sxs-lookup"><span data-stu-id="d777e-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="d777e-104">Для ссылки на текущий экземпляр используется ключевое слово `Me`.</span><span class="sxs-lookup"><span data-stu-id="d777e-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="d777e-105">Ссылка на текущий экземпляр</span><span class="sxs-lookup"><span data-stu-id="d777e-105">To refer to the current instance</span></span>  
  
- <span data-ttu-id="d777e-106">Используйте ключевое слово `Me`, в котором обычно используется имя объектной переменной.</span><span class="sxs-lookup"><span data-stu-id="d777e-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="d777e-107">Хотя `Me` ведет себя как объектная переменная, вы не можете объявить ее или присвоить ей что-либо.</span><span class="sxs-lookup"><span data-stu-id="d777e-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="d777e-108">`Me` всегда ссылается на текущий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="d777e-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d777e-109">См. также</span><span class="sxs-lookup"><span data-stu-id="d777e-109">See also</span></span>

- [<span data-ttu-id="d777e-110">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="d777e-110">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="d777e-111">Присваивание объектных переменных</span><span class="sxs-lookup"><span data-stu-id="d777e-111">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="d777e-112">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="d777e-112">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
