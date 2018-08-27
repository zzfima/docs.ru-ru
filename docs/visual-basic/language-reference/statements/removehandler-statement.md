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
ms.openlocfilehash: c1e6ffec64bc01936955a2e94aa9c110b317109f
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925170"
---
# <a name="removehandler-statement"></a><span data-ttu-id="2f17b-102">Оператор RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="2f17b-102">RemoveHandler Statement</span></span>
<span data-ttu-id="2f17b-103">Удаляет связь между событием и обработчиком событий.</span><span class="sxs-lookup"><span data-stu-id="2f17b-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f17b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f17b-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="2f17b-105">Части</span><span class="sxs-lookup"><span data-stu-id="2f17b-105">Parts</span></span>  
  
|<span data-ttu-id="2f17b-106">Термин</span><span class="sxs-lookup"><span data-stu-id="2f17b-106">Term</span></span>|<span data-ttu-id="2f17b-107">Определение</span><span class="sxs-lookup"><span data-stu-id="2f17b-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="2f17b-108">Имя обрабатываемого события.</span><span class="sxs-lookup"><span data-stu-id="2f17b-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="2f17b-109">Имя процедуры, которая обрабатывает событие.</span><span class="sxs-lookup"><span data-stu-id="2f17b-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f17b-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="2f17b-110">Remarks</span></span>  
 <span data-ttu-id="2f17b-111">`AddHandler` И `RemoveHandler` операторы позволяют запускать и останавливать обработку событий для конкретного события в любое время, во время выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="2f17b-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f17b-112">Для пользовательских событий `RemoveHandler` инструкция вызывает события `RemoveHandler` метода доступа.</span><span class="sxs-lookup"><span data-stu-id="2f17b-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="2f17b-113">Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2f17b-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f17b-114">Пример</span><span class="sxs-lookup"><span data-stu-id="2f17b-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2f17b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2f17b-115">See Also</span></span>  
 [<span data-ttu-id="2f17b-116">Оператор AddHandler</span><span class="sxs-lookup"><span data-stu-id="2f17b-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [<span data-ttu-id="2f17b-117">Handles</span><span class="sxs-lookup"><span data-stu-id="2f17b-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="2f17b-118">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="2f17b-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="2f17b-119">События</span><span class="sxs-lookup"><span data-stu-id="2f17b-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
