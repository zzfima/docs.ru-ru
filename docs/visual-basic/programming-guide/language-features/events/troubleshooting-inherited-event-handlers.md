---
title: "Устранение неполадок с унаследованными обработчиками событий в Visual Basic | Документы Microsoft"
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
- troubleshooting events
- inherited events
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
caps.latest.revision: 11
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
ms.openlocfilehash: f64395975821226d42664bbf78b04120d49a38bc
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="84873-102">Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="84873-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="84873-103">В этом разделе перечислены распространенные проблемы, связанные с обработчиками событий в наследуемых компонентах.</span><span class="sxs-lookup"><span data-stu-id="84873-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="84873-104">Процедуры</span><span class="sxs-lookup"><span data-stu-id="84873-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="84873-105">Код в обработчике событий выполняется дважды для каждого вызова</span><span class="sxs-lookup"><span data-stu-id="84873-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
-   <span data-ttu-id="84873-106">Наследуемый обработчик события не должен содержать [обрабатывает](../../../../visual-basic/language-reference/statements/handles-clause.md) предложения.</span><span class="sxs-lookup"><span data-stu-id="84873-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="84873-107">Метод в базовом классе уже связан с событием и будет запускаться соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="84873-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="84873-108">Удалить `Handles` предложения из унаследованного метода.</span><span class="sxs-lookup"><span data-stu-id="84873-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     <span data-ttu-id="84873-109">[!code-vb[VbVbalrEvents&#32;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="84873-109">[!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]</span></span>  
  
-   <span data-ttu-id="84873-110">Если нет унаследованного метода `Handles` ключевое слово, убедитесь, что код не содержит лишних [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) или все дополнительные методы обработки одного события.</span><span class="sxs-lookup"><span data-stu-id="84873-110">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84873-111">См. также</span><span class="sxs-lookup"><span data-stu-id="84873-111">See Also</span></span>  
 [<span data-ttu-id="84873-112">События</span><span class="sxs-lookup"><span data-stu-id="84873-112">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
