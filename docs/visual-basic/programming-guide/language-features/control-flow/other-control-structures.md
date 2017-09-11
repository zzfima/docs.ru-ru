---
title: "Другие структуры управления (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8f8bd57f193be0d7f410f7325355ffc47ab10e3f
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="163d7-102">Другие структуры управления (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="163d7-102">Other Control Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="163d7-103">предоставляет структур элементов управления, которые помогают удаления ресурсов или уменьшения числа повторений ссылок на объект.</span><span class="sxs-lookup"><span data-stu-id="163d7-103"> provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="163d7-104">С помощью... С помощью конструкции End</span><span class="sxs-lookup"><span data-stu-id="163d7-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="163d7-105">`Using...End Using` Конструкции устанавливает блок операторов, в котором следует использовать ресурсы, например SQL-соединение.</span><span class="sxs-lookup"><span data-stu-id="163d7-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="163d7-106">При необходимости можно запросить ресурс с `Using` инструкции.</span><span class="sxs-lookup"><span data-stu-id="163d7-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="163d7-107">После выхода из `Using` блока [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] автоматически удаляет ресурс, чтобы он доступен для использования другим кодом.</span><span class="sxs-lookup"><span data-stu-id="163d7-107">When you exit the `Using` block, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="163d7-108">Ресурс должен быть локальным и допускать удаление.</span><span class="sxs-lookup"><span data-stu-id="163d7-108">The resource must be local and disposable.</span></span> <span data-ttu-id="163d7-109">Дополнительные сведения см. в разделе [с помощью инструкции](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="163d7-109">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="163d7-110">С помощью... Завершение создания</span><span class="sxs-lookup"><span data-stu-id="163d7-110">With...End With Construction</span></span>  
 <span data-ttu-id="163d7-111">`With...End With` Позволяет указать ссылку на объект один раз и затем запустить последовательность операторов, доступа к его членам.</span><span class="sxs-lookup"><span data-stu-id="163d7-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="163d7-112">Это может упростить код и повысить производительность, поскольку [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не восстанавливает ссылку для каждого оператора, который обращается к ней.</span><span class="sxs-lookup"><span data-stu-id="163d7-112">This can simplify your code and improve performance because [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="163d7-113">Дополнительные сведения см. в разделе [с... Заканчивается инструкция](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="163d7-113">For more information, see [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="163d7-114">См. также</span><span class="sxs-lookup"><span data-stu-id="163d7-114">See Also</span></span>  
 <span data-ttu-id="163d7-115">[Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span><span class="sxs-lookup"><span data-stu-id="163d7-115">[Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span></span>  
<span data-ttu-id="163d7-116"> [Структуры критериев](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span><span class="sxs-lookup"><span data-stu-id="163d7-116"> [Decision Structures](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span></span>  
<span data-ttu-id="163d7-117"> [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span><span class="sxs-lookup"><span data-stu-id="163d7-117"> [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span></span>  
<span data-ttu-id="163d7-118"> [Вложенные структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) </span><span class="sxs-lookup"><span data-stu-id="163d7-118"> [Nested Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) </span></span>  
<span data-ttu-id="163d7-119"> [С помощью инструкции](../../../../visual-basic/language-reference/statements/using-statement.md) </span><span class="sxs-lookup"><span data-stu-id="163d7-119"> [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md) </span></span>  
<span data-ttu-id="163d7-120"> [Оператор With...End With](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)</span><span class="sxs-lookup"><span data-stu-id="163d7-120"> [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)</span></span>
