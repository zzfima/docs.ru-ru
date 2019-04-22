---
title: Предложение Handles (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Handles
- vb.Handles
helpviewer_keywords:
- Handles keyword [Visual Basic]
ms.assetid: 1b051c0e-f499-42f6-acb5-6f4f27824b40
ms.openlocfilehash: 50a449ea8a5131c878cf703f44695cd2e2304444
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842581"
---
# <a name="handles-clause-visual-basic"></a><span data-ttu-id="b1166-102">Предложение Handles (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1166-102">Handles Clause (Visual Basic)</span></span>
<span data-ttu-id="b1166-103">Заявляет, что процедура обрабатывает указанное событие.</span><span class="sxs-lookup"><span data-stu-id="b1166-103">Declares that a procedure handles a specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1166-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1166-104">Syntax</span></span>  
  
```  
proceduredeclaration Handles eventlist  
```  
  
## <a name="parts"></a><span data-ttu-id="b1166-105">Части</span><span class="sxs-lookup"><span data-stu-id="b1166-105">Parts</span></span>  
 `proceduredeclaration`  
 <span data-ttu-id="b1166-106">Объявление процедуры `Sub` для процедуры, которая будет обрабатывать событие.</span><span class="sxs-lookup"><span data-stu-id="b1166-106">The `Sub` procedure declaration for the procedure that will handle the event.</span></span>  
  
 `eventlist`  
 <span data-ttu-id="b1166-107">Список событий, обрабатываемых `proceduredeclaration`, с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="b1166-107">List of the events for `proceduredeclaration` to handle, separated by commas.</span></span> <span data-ttu-id="b1166-108">События должны вызываться базовым классом для текущего класса либо объектом, объявленным с помощью ключевого слова `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="b1166-108">The events must be raised by either the base class for the current class, or by an object declared using the `WithEvents` keyword.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1166-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="b1166-109">Remarks</span></span>  
 <span data-ttu-id="b1166-110">Используйте ключевое слово `Handles` в конце объявления процедуры, чтобы она обрабатывала события, вызванные переменной объекта, которая объявлена с помощью ключевого слова `WithEvents` .</span><span class="sxs-lookup"><span data-stu-id="b1166-110">Use the `Handles` keyword at the end of a procedure declaration to cause it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span> <span data-ttu-id="b1166-111">Ключевое слово `Handles` может также использоваться в производном классе для обработки событий из базового класса.</span><span class="sxs-lookup"><span data-stu-id="b1166-111">The `Handles` keyword can also be used in a derived class to handle events from a base class.</span></span>  
  
 <span data-ttu-id="b1166-112">Как ключевое слово `Handles` так и оператор `AddHandler` позволяют задать обработку определенных событий конкретными процедурами, но между ними существуют различия.</span><span class="sxs-lookup"><span data-stu-id="b1166-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="b1166-113">Используйте ключевое слово `Handles` при определении процедуры, чтобы указать, что она обрабатывает определенное событие.</span><span class="sxs-lookup"><span data-stu-id="b1166-113">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="b1166-114">Оператор `AddHandler` подключает процедуры к событиям во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b1166-114">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="b1166-115">Дополнительные сведения см. в разделе [оператор AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b1166-115">For more information, see [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span>  
  
 <span data-ttu-id="b1166-116">Для пользовательских событий приложение вызывает метод доступа `AddHandler` события во время добавления процедуры в качестве обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="b1166-116">For custom events, the application invokes the event's `AddHandler` accessor when it adds the procedure as an event handler.</span></span> <span data-ttu-id="b1166-117">Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b1166-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1166-118">Пример</span><span class="sxs-lookup"><span data-stu-id="b1166-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#2)]  
  
 <span data-ttu-id="b1166-119">В следующем примере показано, как производный класс может использовать оператор `Handles` для обработки события из базового класса.</span><span class="sxs-lookup"><span data-stu-id="b1166-119">The following example demonstrates how a derived class can use the `Handles` statement to handle an event from a base class.</span></span>  
  
 [!code-vb[VbVbalrEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="b1166-120">Пример</span><span class="sxs-lookup"><span data-stu-id="b1166-120">Example</span></span>  
 <span data-ttu-id="b1166-121">В следующем примере показаны два обработчика событий кнопки для **приложение WPF** проекта.</span><span class="sxs-lookup"><span data-stu-id="b1166-121">The following example contains two button event handlers for a **WPF Application** project.</span></span>  
  
 [!code-vb[VbVbalrEvents#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/class3.vb#41)]  
  
## <a name="example"></a><span data-ttu-id="b1166-122">Пример</span><span class="sxs-lookup"><span data-stu-id="b1166-122">Example</span></span>  
 <span data-ttu-id="b1166-123">Следующий пример эквивалентен предыдущему примеру:</span><span class="sxs-lookup"><span data-stu-id="b1166-123">The following example is equivalent to the previous example.</span></span> <span data-ttu-id="b1166-124">`eventlist` в предложении `Handles` содержит события для обеих кнопок.</span><span class="sxs-lookup"><span data-stu-id="b1166-124">The `eventlist` in the `Handles` clause contains the events for both buttons.</span></span>  
  
 [!code-vb[VbVbalrEvents#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/class3.vb#42)]  
  
## <a name="see-also"></a><span data-ttu-id="b1166-125">См. также</span><span class="sxs-lookup"><span data-stu-id="b1166-125">See also</span></span>

- [<span data-ttu-id="b1166-126">WithEvents</span><span class="sxs-lookup"><span data-stu-id="b1166-126">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
- [<span data-ttu-id="b1166-127">Оператор AddHandler</span><span class="sxs-lookup"><span data-stu-id="b1166-127">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="b1166-128">Оператор RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="b1166-128">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="b1166-129">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="b1166-129">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="b1166-130">Оператор RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="b1166-130">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
- [<span data-ttu-id="b1166-131">События</span><span class="sxs-lookup"><span data-stu-id="b1166-131">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
