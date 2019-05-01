---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: bffaed4976d82202eaea9ce50f6d389548fdabfd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61998014"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a><span data-ttu-id="d7372-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="d7372-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span></span>
<span data-ttu-id="d7372-103">Конечный автомат для перечисления координаторов перешел в конечное состояние.</span><span class="sxs-lookup"><span data-stu-id="d7372-103">The state machine for a coordinator enlistment has entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d7372-104">Описание</span><span class="sxs-lookup"><span data-stu-id="d7372-104">Description</span></span>  
 <span data-ttu-id="d7372-105">Регистрируется, если локальный диспетчер транзакция полагает, что перечисление координаторов более высокого уровня завершило обработку 2pc.</span><span class="sxs-lookup"><span data-stu-id="d7372-105">Traced when the local Transaction Manager believes a superior coordinator enlistment has completed 2pc processing.</span></span> <span data-ttu-id="d7372-106">Результатом перечисления может быть значение Committed, Aborted или Forgotten.</span><span class="sxs-lookup"><span data-stu-id="d7372-106">The outcome for the enlistment can be Committed or Aborted or Forgotten.</span></span> <span data-ttu-id="d7372-107">Кроме того, это событие регистрируется, если на этапе подготовки локальный диспетчер транзакций голосует за режим ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="d7372-107">It is also traced if the local Transaction Manager votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7372-108">См. также</span><span class="sxs-lookup"><span data-stu-id="d7372-108">See also</span></span>

- [<span data-ttu-id="d7372-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="d7372-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="d7372-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="d7372-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d7372-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="d7372-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
