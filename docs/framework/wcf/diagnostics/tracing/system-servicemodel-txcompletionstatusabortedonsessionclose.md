---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 149a2bfac435185552c3871948b35bc860a43ae1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="602f8-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="602f8-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>
<span data-ttu-id="602f8-103">Указанная транзакция прервана, поскольку она была незавершенной на момент закрытия сеанса и атрибуту TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute задано значение "false".</span><span class="sxs-lookup"><span data-stu-id="602f8-103">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="602f8-104">Описание</span><span class="sxs-lookup"><span data-stu-id="602f8-104">Description</span></span>  
 <span data-ttu-id="602f8-105">Трассируется, если текущий активный сеанс был закрыт, транзакция не была завершена и TransactionAutoCompleteOnSessionClose имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="602f8-105">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="602f8-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="602f8-106">Troubleshooting</span></span>  
 <span data-ttu-id="602f8-107">Эта трассировка указывает о потенциальной ошибке в приложении, наличие которой требуется проверить.</span><span class="sxs-lookup"><span data-stu-id="602f8-107">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="602f8-108">См. также</span><span class="sxs-lookup"><span data-stu-id="602f8-108">See Also</span></span>  
 [<span data-ttu-id="602f8-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="602f8-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="602f8-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="602f8-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="602f8-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="602f8-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
