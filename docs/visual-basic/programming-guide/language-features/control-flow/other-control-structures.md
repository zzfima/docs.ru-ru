---
title: Другие структуры управления (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: a383d0c95de5286cce722c05bd8888d5acffb173
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590004"
---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="48269-102">Другие структуры управления (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48269-102">Other Control Structures (Visual Basic)</span></span>
<span data-ttu-id="48269-103">Visual Basic предоставляет структур управления, которые помогут вам удаления ресурсов, или уменьшите количество раз, вам необходимо будет повторить ссылку на объект.</span><span class="sxs-lookup"><span data-stu-id="48269-103">Visual Basic provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="48269-104">С помощью... С помощью конструкции</span><span class="sxs-lookup"><span data-stu-id="48269-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="48269-105">`Using...End Using` Конструкции устанавливает блок операторов, в котором следует использовать ресурсы, например подключение к SQL.</span><span class="sxs-lookup"><span data-stu-id="48269-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="48269-106">При необходимости можно запросить ресурс с `Using` инструкции.</span><span class="sxs-lookup"><span data-stu-id="48269-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="48269-107">После выхода из `Using` блока, Visual Basic автоматически удаляет ресурс, чтобы он доступен для использования другим кодом.</span><span class="sxs-lookup"><span data-stu-id="48269-107">When you exit the `Using` block, Visual Basic automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="48269-108">Ресурс должен быть локальный и высвобождаемого.</span><span class="sxs-lookup"><span data-stu-id="48269-108">The resource must be local and disposable.</span></span> <span data-ttu-id="48269-109">Дополнительные сведения см. в разделе [Оператор using](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="48269-109">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="48269-110">С помощью... Завершить с помощью конструкции</span><span class="sxs-lookup"><span data-stu-id="48269-110">With...End With Construction</span></span>  
 <span data-ttu-id="48269-111">`With...End With` Позволяет указать ссылку на объект один раз и затем выполнить ряд инструкций, которые обращаются к его члены.</span><span class="sxs-lookup"><span data-stu-id="48269-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="48269-112">Это можно упростить код и повысить производительность, поскольку Visual Basic не восстанавливает ссылку для каждого оператора, который обращается к ней.</span><span class="sxs-lookup"><span data-stu-id="48269-112">This can simplify your code and improve performance because Visual Basic does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="48269-113">Дополнительные сведения см. в разделе [с... Завершить с помощью инструкции](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="48269-113">For more information, see [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48269-114">См. также</span><span class="sxs-lookup"><span data-stu-id="48269-114">See also</span></span>
- [<span data-ttu-id="48269-115">Поток управления</span><span class="sxs-lookup"><span data-stu-id="48269-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="48269-116">Структуры решений</span><span class="sxs-lookup"><span data-stu-id="48269-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="48269-117">Циклические структуры</span><span class="sxs-lookup"><span data-stu-id="48269-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="48269-118">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="48269-118">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="48269-119">Оператор Using</span><span class="sxs-lookup"><span data-stu-id="48269-119">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)
- [<span data-ttu-id="48269-120">Оператор With...End With</span><span class="sxs-lookup"><span data-stu-id="48269-120">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
