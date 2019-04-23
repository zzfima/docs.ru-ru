---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: 7b1f6a2f4a344b566c76d0095942b84a8a4e76f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166508"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="b6818-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="b6818-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>
<span data-ttu-id="b6818-103">Указанная транзакция прервана, поскольку она была незавершенной на момент закрытия сеанса и атрибуту TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute задано значение "false".</span><span class="sxs-lookup"><span data-stu-id="b6818-103">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b6818-104">Описание</span><span class="sxs-lookup"><span data-stu-id="b6818-104">Description</span></span>  
 <span data-ttu-id="b6818-105">Трассируется, если текущий активный сеанс был закрыт, транзакция не была завершена и TransactionAutoCompleteOnSessionClose имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="b6818-105">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="b6818-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="b6818-106">Troubleshooting</span></span>  
 <span data-ttu-id="b6818-107">Эта трассировка указывает о потенциальной ошибке в приложении, наличие которой требуется проверить.</span><span class="sxs-lookup"><span data-stu-id="b6818-107">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6818-108">См. также</span><span class="sxs-lookup"><span data-stu-id="b6818-108">See also</span></span>

- [<span data-ttu-id="b6818-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="b6818-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="b6818-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="b6818-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="b6818-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="b6818-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
