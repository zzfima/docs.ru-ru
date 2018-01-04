---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 960166c7c1d91bcab8420a55e633b461bf37c626
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a><span data-ttu-id="0e00c-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="0e00c-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span></span>
<span data-ttu-id="0e00c-103">Конечный автомат для перечисления координаторов перешел в конечное состояние.</span><span class="sxs-lookup"><span data-stu-id="0e00c-103">The state machine for a coordinator enlistment has entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0e00c-104">Описание:</span><span class="sxs-lookup"><span data-stu-id="0e00c-104">Description</span></span>  
 <span data-ttu-id="0e00c-105">Регистрируется, если локальный диспетчер транзакция полагает, что перечисление координаторов более высокого уровня завершило обработку 2pc.</span><span class="sxs-lookup"><span data-stu-id="0e00c-105">Traced when the local Transaction Manager believes a superior coordinator enlistment has completed 2pc processing.</span></span> <span data-ttu-id="0e00c-106">Результатом перечисления может быть значение Committed, Aborted или Forgotten.</span><span class="sxs-lookup"><span data-stu-id="0e00c-106">The outcome for the enlistment can be Committed or Aborted or Forgotten.</span></span> <span data-ttu-id="0e00c-107">Кроме того, это событие регистрируется, если на этапе подготовки локальный диспетчер транзакций голосует за режим ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="0e00c-107">It is also traced if the local Transaction Manager votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e00c-108">См. также</span><span class="sxs-lookup"><span data-stu-id="0e00c-108">See Also</span></span>  
 [<span data-ttu-id="0e00c-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="0e00c-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="0e00c-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="0e00c-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="0e00c-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="0e00c-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
