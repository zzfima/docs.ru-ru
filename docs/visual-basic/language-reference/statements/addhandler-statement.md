---
title: "Оператор AddHandler | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
dev_langs:
- VB
helpviewer_keywords:
- AddHandler statement
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
caps.latest.revision: 15
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
ms.openlocfilehash: cd821a568a35f33c722c1631eb7fbaf8f877cf4f
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="addhandler-statement"></a><span data-ttu-id="60d01-102">Оператор AddHandler</span><span class="sxs-lookup"><span data-stu-id="60d01-102">AddHandler Statement</span></span>
<span data-ttu-id="60d01-103">Связывает событие с обработчиком событий во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="60d01-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60d01-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="60d01-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="60d01-105">Части</span><span class="sxs-lookup"><span data-stu-id="60d01-105">Parts</span></span>  
 `event`  
 <span data-ttu-id="60d01-106">Имя события для обработки.</span><span class="sxs-lookup"><span data-stu-id="60d01-106">The name of the event to handle.</span></span>  
  
 `eventhandler`  
 <span data-ttu-id="60d01-107">Имя процедуры, которая обрабатывает событие.</span><span class="sxs-lookup"><span data-stu-id="60d01-107">The name of a procedure that handles the event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60d01-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="60d01-108">Remarks</span></span>  
 <span data-ttu-id="60d01-109">`AddHandler` И `RemoveHandler` инструкции позволяют запускать и останавливать обработку события в любой момент во время выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="60d01-109">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="60d01-110">Подпись `eventhandler` процедуры должна соответствовать сигнатуре события `event`.</span><span class="sxs-lookup"><span data-stu-id="60d01-110">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="60d01-111">Как ключевое слово `Handles` так и оператор `AddHandler` позволяют задать обработку определенных событий конкретными процедурами, но между ними существуют различия.</span><span class="sxs-lookup"><span data-stu-id="60d01-111">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="60d01-112">Оператор `AddHandler` подключает процедуры к событиям во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="60d01-112">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="60d01-113">Используйте ключевое слово `Handles` при определении процедуры, чтобы указать, что она обрабатывает определенное событие.</span><span class="sxs-lookup"><span data-stu-id="60d01-113">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="60d01-114">Дополнительные сведения см. в разделе [обрабатывает](../../../visual-basic/language-reference/statements/handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="60d01-114">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60d01-115">Для пользовательских событий `AddHandler` инструкция вызывает событие `AddHandler` доступа.</span><span class="sxs-lookup"><span data-stu-id="60d01-115">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="60d01-116">Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="60d01-116">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="60d01-117">Пример</span><span class="sxs-lookup"><span data-stu-id="60d01-117">Example</span></span>  
 <span data-ttu-id="60d01-118">[!code-vb[VbVbalrEvents&17;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="60d01-118">[!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60d01-119">См. также</span><span class="sxs-lookup"><span data-stu-id="60d01-119">See Also</span></span>  
 <span data-ttu-id="60d01-120">[Оператор RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md) </span><span class="sxs-lookup"><span data-stu-id="60d01-120">[RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) </span></span>  
<span data-ttu-id="60d01-121"> [Обрабатывает](../../../visual-basic/language-reference/statements/handles-clause.md) </span><span class="sxs-lookup"><span data-stu-id="60d01-121"> [Handles](../../../visual-basic/language-reference/statements/handles-clause.md) </span></span>  
<span data-ttu-id="60d01-122"> [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md) </span><span class="sxs-lookup"><span data-stu-id="60d01-122"> [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) </span></span>  
<span data-ttu-id="60d01-123"> [События](../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="60d01-123"> [Events](../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
