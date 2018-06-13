---
title: Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: f6355cf7fc2e43651c1112d048220a8179968c76
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646335"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="ff8f8-102">Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ff8f8-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="ff8f8-103">В этом разделе перечислены распространенные проблемы, связанные с обработчиками событий в наследуемых компонентах.</span><span class="sxs-lookup"><span data-stu-id="ff8f8-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="ff8f8-104">Процедуры</span><span class="sxs-lookup"><span data-stu-id="ff8f8-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="ff8f8-105">Код в обработчик событий выполняется дважды для каждого вызова</span><span class="sxs-lookup"><span data-stu-id="ff8f8-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
-   <span data-ttu-id="ff8f8-106">Наследуемый обработчик события не должны содержать [обрабатывает](../../../../visual-basic/language-reference/statements/handles-clause.md) предложения.</span><span class="sxs-lookup"><span data-stu-id="ff8f8-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="ff8f8-107">Метод в базовом классе уже связан с событием и будет запущен.</span><span class="sxs-lookup"><span data-stu-id="ff8f8-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="ff8f8-108">Удалить `Handles` предложения из унаследованного метода.</span><span class="sxs-lookup"><span data-stu-id="ff8f8-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]  
  
-   <span data-ttu-id="ff8f8-109">Если производный метод не имеет `Handles` ключевое слово, убедитесь, что код не содержит лишних [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) или любые дополнительные методы, обрабатывающие того же события.</span><span class="sxs-lookup"><span data-stu-id="ff8f8-109">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff8f8-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ff8f8-110">See Also</span></span>  
 [<span data-ttu-id="ff8f8-111">События</span><span class="sxs-lookup"><span data-stu-id="ff8f8-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
