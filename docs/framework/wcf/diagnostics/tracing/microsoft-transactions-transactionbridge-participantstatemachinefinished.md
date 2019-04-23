---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: 7f37cb5d9ee3d2d9d56519f785388f278b3333b9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170733"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="0ac0b-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="0ac0b-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="0ac0b-103">Конечный автомат для перечисления участников перешел в конечное состояние.</span><span class="sxs-lookup"><span data-stu-id="0ac0b-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0ac0b-104">Описание</span><span class="sxs-lookup"><span data-stu-id="0ac0b-104">Description</span></span>  
 <span data-ttu-id="0ac0b-105">Трассируется, когда перечисление подчиненных участников завершило обработку 2pc.</span><span class="sxs-lookup"><span data-stu-id="0ac0b-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="0ac0b-106">Результатом для перечисления может быть значение Committed или Aborted.</span><span class="sxs-lookup"><span data-stu-id="0ac0b-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="0ac0b-107">Кроме того, это событие регистрируется, если на этапе подготовки любой из участников голосует за режим ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="0ac0b-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ac0b-108">См. также</span><span class="sxs-lookup"><span data-stu-id="0ac0b-108">See also</span></span>

- [<span data-ttu-id="0ac0b-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="0ac0b-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="0ac0b-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="0ac0b-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="0ac0b-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="0ac0b-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
