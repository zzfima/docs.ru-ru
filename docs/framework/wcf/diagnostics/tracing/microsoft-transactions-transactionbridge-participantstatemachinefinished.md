---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: 7f37cb5d9ee3d2d9d56519f785388f278b3333b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61997884"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="8c0b0-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="8c0b0-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="8c0b0-103">Конечный автомат для перечисления участников перешел в конечное состояние.</span><span class="sxs-lookup"><span data-stu-id="8c0b0-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8c0b0-104">Описание</span><span class="sxs-lookup"><span data-stu-id="8c0b0-104">Description</span></span>  
 <span data-ttu-id="8c0b0-105">Трассируется, когда перечисление подчиненных участников завершило обработку 2pc.</span><span class="sxs-lookup"><span data-stu-id="8c0b0-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="8c0b0-106">Результатом для перечисления может быть значение Committed или Aborted.</span><span class="sxs-lookup"><span data-stu-id="8c0b0-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="8c0b0-107">Кроме того, это событие регистрируется, если на этапе подготовки любой из участников голосует за режим ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="8c0b0-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c0b0-108">См. также</span><span class="sxs-lookup"><span data-stu-id="8c0b0-108">See also</span></span>

- [<span data-ttu-id="8c0b0-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="8c0b0-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="8c0b0-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="8c0b0-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="8c0b0-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="8c0b0-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
