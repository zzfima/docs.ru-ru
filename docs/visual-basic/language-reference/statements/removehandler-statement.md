---
title: Оператор RemoveHandler (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 27cdd2753507c6fc4d5c5041607e2ccb425b81b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560624"
---
# <a name="removehandler-statement"></a><span data-ttu-id="b4a4c-102">Оператор RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="b4a4c-102">RemoveHandler Statement</span></span>
<span data-ttu-id="b4a4c-103">Удаляет связь между событием и обработчиком событий.</span><span class="sxs-lookup"><span data-stu-id="b4a4c-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4a4c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4a4c-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="b4a4c-105">Части</span><span class="sxs-lookup"><span data-stu-id="b4a4c-105">Parts</span></span>  
  
|<span data-ttu-id="b4a4c-106">Термин</span><span class="sxs-lookup"><span data-stu-id="b4a4c-106">Term</span></span>|<span data-ttu-id="b4a4c-107">Определение</span><span class="sxs-lookup"><span data-stu-id="b4a4c-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="b4a4c-108">Имя обрабатываемого события.</span><span class="sxs-lookup"><span data-stu-id="b4a4c-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="b4a4c-109">Имя процедуры, которая обрабатывает событие.</span><span class="sxs-lookup"><span data-stu-id="b4a4c-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4a4c-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="b4a4c-110">Remarks</span></span>  
 <span data-ttu-id="b4a4c-111">`AddHandler` И `RemoveHandler` операторы позволяют запускать и останавливать обработку событий для конкретного события в любое время, во время выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="b4a4c-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4a4c-112">Для пользовательских событий `RemoveHandler` инструкция вызывает события `RemoveHandler` метода доступа.</span><span class="sxs-lookup"><span data-stu-id="b4a4c-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="b4a4c-113">Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b4a4c-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4a4c-114">Пример</span><span class="sxs-lookup"><span data-stu-id="b4a4c-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b4a4c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b4a4c-115">See also</span></span>
- [<span data-ttu-id="b4a4c-116">Оператор AddHandler</span><span class="sxs-lookup"><span data-stu-id="b4a4c-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="b4a4c-117">Handles</span><span class="sxs-lookup"><span data-stu-id="b4a4c-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="b4a4c-118">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="b4a4c-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="b4a4c-119">События</span><span class="sxs-lookup"><span data-stu-id="b4a4c-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
