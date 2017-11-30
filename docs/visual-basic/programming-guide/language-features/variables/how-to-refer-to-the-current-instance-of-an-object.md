---
title: "Практическое руководство. Ссылка на текущий экземпляр объекта (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 33ea612253b00e12f47258189da4ac7d8d98ade5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="3d46f-102">Практическое руководство. Ссылка на текущий экземпляр объекта (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d46f-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>
<span data-ttu-id="3d46f-103">*Текущего экземпляра* объекта является экземпляром, в котором в данный момент выполняется код.</span><span class="sxs-lookup"><span data-stu-id="3d46f-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="3d46f-104">Вы используете `Me` ключевое слово для ссылки на текущий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="3d46f-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="3d46f-105">Для ссылки на текущий экземпляр</span><span class="sxs-lookup"><span data-stu-id="3d46f-105">To refer to the current instance</span></span>  
  
-   <span data-ttu-id="3d46f-106">Использовать `Me` ключевое слово, где обычно лучше использовать имя переменной объекта.</span><span class="sxs-lookup"><span data-stu-id="3d46f-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="3d46f-107">Несмотря на то что `Me` ведет себя подобно объектной переменной, нельзя объявить его или ее присвоить ничего.</span><span class="sxs-lookup"><span data-stu-id="3d46f-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="3d46f-108">`Me`всегда ссылается на текущий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="3d46f-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d46f-109">См. также</span><span class="sxs-lookup"><span data-stu-id="3d46f-109">See Also</span></span>  
 [<span data-ttu-id="3d46f-110">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="3d46f-110">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="3d46f-111">Присваивание объектных переменных</span><span class="sxs-lookup"><span data-stu-id="3d46f-111">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="3d46f-112">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="3d46f-112">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
