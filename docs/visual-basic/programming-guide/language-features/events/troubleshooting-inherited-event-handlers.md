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
ms.openlocfilehash: 91bded2f1249bfcbeeca28419ee9bcec819babf6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965428"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="987ff-102">Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="987ff-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="987ff-103">В этом разделе перечислены распространенные проблемы, связанные с обработчиками событий в наследуемых компонентах.</span><span class="sxs-lookup"><span data-stu-id="987ff-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="987ff-104">Процедуры</span><span class="sxs-lookup"><span data-stu-id="987ff-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="987ff-105">Код в обработчике событий выполняется дважды для каждого вызова</span><span class="sxs-lookup"><span data-stu-id="987ff-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
-   <span data-ttu-id="987ff-106">Производный обработчик событий не должны содержать [обрабатывает](../../../../visual-basic/language-reference/statements/handles-clause.md) предложение.</span><span class="sxs-lookup"><span data-stu-id="987ff-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="987ff-107">Метод в базовом классе уже связан с событием и будет запущен.</span><span class="sxs-lookup"><span data-stu-id="987ff-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="987ff-108">Удалить `Handles` предложение из унаследованного метода.</span><span class="sxs-lookup"><span data-stu-id="987ff-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
-   <span data-ttu-id="987ff-109">Если нет унаследованный метод `Handles` ключевое слово, убедитесь, что ваш код не содержит лишних [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) или все дополнительные методы, которые обрабатывают то же событие.</span><span class="sxs-lookup"><span data-stu-id="987ff-109">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="987ff-110">См. также</span><span class="sxs-lookup"><span data-stu-id="987ff-110">See also</span></span>
- [<span data-ttu-id="987ff-111">События</span><span class="sxs-lookup"><span data-stu-id="987ff-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
