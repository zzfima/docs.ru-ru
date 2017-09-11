---
title: "Оператор RemoveHandler | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
dev_langs:
- VB
helpviewer_keywords:
- RemoveHandler keyword
- RemoveHandler statement
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
caps.latest.revision: 14
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
ms.openlocfilehash: 6e614a1dce4894dcd18509854f3cae149665cbf0
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="removehandler-statement"></a><span data-ttu-id="2f005-102">Оператор RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="2f005-102">RemoveHandler Statement</span></span>
<span data-ttu-id="2f005-103">Удаляет связь между событием и обработчиком событий.</span><span class="sxs-lookup"><span data-stu-id="2f005-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f005-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f005-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="2f005-105">Части</span><span class="sxs-lookup"><span data-stu-id="2f005-105">Parts</span></span>  
  
|<span data-ttu-id="2f005-106">Термин</span><span class="sxs-lookup"><span data-stu-id="2f005-106">Term</span></span>|<span data-ttu-id="2f005-107">Определение</span><span class="sxs-lookup"><span data-stu-id="2f005-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="2f005-108">Имя обрабатываемого события.</span><span class="sxs-lookup"><span data-stu-id="2f005-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="2f005-109">Имя процедуры, которая обрабатывает событие.</span><span class="sxs-lookup"><span data-stu-id="2f005-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f005-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="2f005-110">Remarks</span></span>  
 <span data-ttu-id="2f005-111">`AddHandler` И `RemoveHandler` инструкции позволяют запускать и останавливать обработку события для конкретного события в любой момент во время выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="2f005-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f005-112">Для пользовательских событий `RemoveHandler` инструкция вызывает событие `RemoveHandler` доступа.</span><span class="sxs-lookup"><span data-stu-id="2f005-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="2f005-113">Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2f005-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f005-114">Пример</span><span class="sxs-lookup"><span data-stu-id="2f005-114">Example</span></span>  
 <span data-ttu-id="2f005-115">[!code-vb[VbVbalrEvents&17;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2f005-115">[!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f005-116">См. также</span><span class="sxs-lookup"><span data-stu-id="2f005-116">See Also</span></span>  
 <span data-ttu-id="2f005-117">[Оператор AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md) </span><span class="sxs-lookup"><span data-stu-id="2f005-117">[AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md) </span></span>  
<span data-ttu-id="2f005-118"> [Обрабатывает](../../../visual-basic/language-reference/statements/handles-clause.md) </span><span class="sxs-lookup"><span data-stu-id="2f005-118"> [Handles](../../../visual-basic/language-reference/statements/handles-clause.md) </span></span>  
<span data-ttu-id="2f005-119"> [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md) </span><span class="sxs-lookup"><span data-stu-id="2f005-119"> [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) </span></span>  
<span data-ttu-id="2f005-120"> [События](../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="2f005-120"> [Events](../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
