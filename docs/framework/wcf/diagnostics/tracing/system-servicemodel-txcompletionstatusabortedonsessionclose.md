---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: 7b1f6a2f4a344b566c76d0095942b84a8a4e76f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991631"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="1f6b1-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="1f6b1-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>
<span data-ttu-id="1f6b1-103">Указанная транзакция прервана, поскольку она была незавершенной на момент закрытия сеанса и атрибуту TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute задано значение "false".</span><span class="sxs-lookup"><span data-stu-id="1f6b1-103">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1f6b1-104">Описание</span><span class="sxs-lookup"><span data-stu-id="1f6b1-104">Description</span></span>  
 <span data-ttu-id="1f6b1-105">Трассируется, если текущий активный сеанс был закрыт, транзакция не была завершена и TransactionAutoCompleteOnSessionClose имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="1f6b1-105">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="1f6b1-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="1f6b1-106">Troubleshooting</span></span>  
 <span data-ttu-id="1f6b1-107">Эта трассировка указывает о потенциальной ошибке в приложении, наличие которой требуется проверить.</span><span class="sxs-lookup"><span data-stu-id="1f6b1-107">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f6b1-108">См. также</span><span class="sxs-lookup"><span data-stu-id="1f6b1-108">See also</span></span>

- [<span data-ttu-id="1f6b1-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="1f6b1-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="1f6b1-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="1f6b1-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="1f6b1-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="1f6b1-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
