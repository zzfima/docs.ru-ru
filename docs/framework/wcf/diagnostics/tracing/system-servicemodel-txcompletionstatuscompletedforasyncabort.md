---
title: System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
ms.date: 03/30/2017
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
ms.openlocfilehash: f84cc9336d6cce7d8c477a1feb6caf45b0662177
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188478"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="6c579-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="6c579-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>
<span data-ttu-id="6c579-103">Заданная транзакция для заданной операции завершена в результате асинхронного прерывания.</span><span class="sxs-lookup"><span data-stu-id="6c579-103">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6c579-104">Описание</span><span class="sxs-lookup"><span data-stu-id="6c579-104">Description</span></span>  
 <span data-ttu-id="6c579-105">Текущая транзакция была прервана, потому что другой участник спровоцировал прерывание, истекло время ожидания или из-за внутренней ошибки участника транзакции.</span><span class="sxs-lookup"><span data-stu-id="6c579-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="6c579-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="6c579-106">Troubleshooting</span></span>  
 <span data-ttu-id="6c579-107">Если это прерывание произошло неожиданно, проверьте системные журналы, чтобы определить истинную причину прерывания.</span><span class="sxs-lookup"><span data-stu-id="6c579-107">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c579-108">См. также</span><span class="sxs-lookup"><span data-stu-id="6c579-108">See also</span></span>

- [<span data-ttu-id="6c579-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="6c579-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="6c579-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="6c579-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="6c579-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="6c579-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
