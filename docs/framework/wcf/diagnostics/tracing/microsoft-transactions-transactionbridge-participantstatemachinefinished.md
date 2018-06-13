---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: 85b8cc4e5044cc7c87ea784e09c160cc527dddaa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473536"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="6f953-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="6f953-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="6f953-103">Конечный автомат для перечисления участников перешел в конечное состояние.</span><span class="sxs-lookup"><span data-stu-id="6f953-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6f953-104">Описание</span><span class="sxs-lookup"><span data-stu-id="6f953-104">Description</span></span>  
 <span data-ttu-id="6f953-105">Трассируется, когда перечисление подчиненных участников завершило обработку 2pc.</span><span class="sxs-lookup"><span data-stu-id="6f953-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="6f953-106">Результатом для перечисления может быть значение Committed или Aborted.</span><span class="sxs-lookup"><span data-stu-id="6f953-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="6f953-107">Кроме того, это событие регистрируется, если на этапе подготовки любой из участников голосует за режим ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="6f953-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f953-108">См. также</span><span class="sxs-lookup"><span data-stu-id="6f953-108">See Also</span></span>  
 [<span data-ttu-id="6f953-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="6f953-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="6f953-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="6f953-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="6f953-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="6f953-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
