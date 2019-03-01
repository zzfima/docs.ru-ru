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
ms.openlocfilehash: 4e53398f97cbd320c0c98250ac5abbc2e4e98027
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981040"
---
# <a name="removehandler-statement"></a><span data-ttu-id="3957e-102">Оператор RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="3957e-102">RemoveHandler Statement</span></span>
<span data-ttu-id="3957e-103">Удаляет связь между событием и обработчиком событий.</span><span class="sxs-lookup"><span data-stu-id="3957e-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3957e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3957e-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="3957e-105">Части</span><span class="sxs-lookup"><span data-stu-id="3957e-105">Parts</span></span>  
  
|<span data-ttu-id="3957e-106">Термин</span><span class="sxs-lookup"><span data-stu-id="3957e-106">Term</span></span>|<span data-ttu-id="3957e-107">Определение</span><span class="sxs-lookup"><span data-stu-id="3957e-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="3957e-108">Имя обрабатываемого события.</span><span class="sxs-lookup"><span data-stu-id="3957e-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="3957e-109">Имя процедуры, которая обрабатывает событие.</span><span class="sxs-lookup"><span data-stu-id="3957e-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3957e-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="3957e-110">Remarks</span></span>  
 <span data-ttu-id="3957e-111">`AddHandler` И `RemoveHandler` операторы позволяют запускать и останавливать обработку событий для конкретного события в любое время, во время выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="3957e-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3957e-112">Для пользовательских событий `RemoveHandler` инструкция вызывает события `RemoveHandler` метода доступа.</span><span class="sxs-lookup"><span data-stu-id="3957e-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="3957e-113">Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3957e-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3957e-114">Пример</span><span class="sxs-lookup"><span data-stu-id="3957e-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="3957e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="3957e-115">See also</span></span>
- [<span data-ttu-id="3957e-116">Оператор AddHandler</span><span class="sxs-lookup"><span data-stu-id="3957e-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="3957e-117">Handles</span><span class="sxs-lookup"><span data-stu-id="3957e-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="3957e-118">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="3957e-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="3957e-119">События</span><span class="sxs-lookup"><span data-stu-id="3957e-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
