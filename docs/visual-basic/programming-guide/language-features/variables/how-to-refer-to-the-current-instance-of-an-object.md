---
title: Как выполнить Ссылка на текущий экземпляр объекта (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: d166ce62a2bb0522d1ca7011aeff7afe076c2d8e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54542201"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="1907c-102">Как выполнить Ссылка на текущий экземпляр объекта (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1907c-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>
<span data-ttu-id="1907c-103">*Текущего экземпляра* объекта является экземпляром, в котором в данный момент выполняется код.</span><span class="sxs-lookup"><span data-stu-id="1907c-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="1907c-104">Использовании `Me` ключевое слово для ссылки на текущий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="1907c-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="1907c-105">Для ссылки на текущий экземпляр</span><span class="sxs-lookup"><span data-stu-id="1907c-105">To refer to the current instance</span></span>  
  
-   <span data-ttu-id="1907c-106">Использовать `Me` ключевое слово, где обычно лучше использовать имя переменной объекта.</span><span class="sxs-lookup"><span data-stu-id="1907c-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="1907c-107">Несмотря на то что `Me` ведет себя как объект переменной, нельзя объявить ее или назначать ничего ее.</span><span class="sxs-lookup"><span data-stu-id="1907c-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="1907c-108">`Me` всегда ссылается на текущий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="1907c-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1907c-109">См. также</span><span class="sxs-lookup"><span data-stu-id="1907c-109">See also</span></span>
- [<span data-ttu-id="1907c-110">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="1907c-110">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="1907c-111">Присваивание объектных переменных</span><span class="sxs-lookup"><span data-stu-id="1907c-111">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="1907c-112">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="1907c-112">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
