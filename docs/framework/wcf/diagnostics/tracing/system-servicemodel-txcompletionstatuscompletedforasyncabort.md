---
title: System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
ms.date: 03/30/2017
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
ms.openlocfilehash: f84cc9336d6cce7d8c477a1feb6caf45b0662177
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59188478"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="070b3-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="070b3-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>
<span data-ttu-id="070b3-103">Заданная транзакция для заданной операции завершена в результате асинхронного прерывания.</span><span class="sxs-lookup"><span data-stu-id="070b3-103">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="070b3-104">Описание</span><span class="sxs-lookup"><span data-stu-id="070b3-104">Description</span></span>  
 <span data-ttu-id="070b3-105">Текущая транзакция была прервана, потому что другой участник спровоцировал прерывание, истекло время ожидания или из-за внутренней ошибки участника транзакции.</span><span class="sxs-lookup"><span data-stu-id="070b3-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="070b3-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="070b3-106">Troubleshooting</span></span>  
 <span data-ttu-id="070b3-107">Если это прерывание произошло неожиданно, проверьте системные журналы, чтобы определить истинную причину прерывания.</span><span class="sxs-lookup"><span data-stu-id="070b3-107">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="070b3-108">См. также</span><span class="sxs-lookup"><span data-stu-id="070b3-108">See also</span></span>

- [<span data-ttu-id="070b3-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="070b3-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="070b3-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="070b3-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="070b3-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="070b3-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
