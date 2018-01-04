---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1385995165308cb1c2f2e6bd6c8a800a88b7b79e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a><span data-ttu-id="0b7f8-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span><span class="sxs-lookup"><span data-stu-id="0b7f8-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span></span>
<span data-ttu-id="0b7f8-103">Истекло время ожидания службой протокола WS-AT ответа на результативное сообщение от неустойчивого участника.</span><span class="sxs-lookup"><span data-stu-id="0b7f8-103">The WS-AT protocol service timed out waiting for a response to an outcome message from a volatile participant.</span></span> <span data-ttu-id="0b7f8-104">При возвращении участника результат транзакции будет поставлен под сомнение.</span><span class="sxs-lookup"><span data-stu-id="0b7f8-104">The transaction outcome may be in doubt if the participant returns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0b7f8-105">Описание:</span><span class="sxs-lookup"><span data-stu-id="0b7f8-105">Description</span></span>  
 <span data-ttu-id="0b7f8-106">Трассируется, когда неустойчивый участник принял решение зафиксировать или прервать транзакцию, однако не ответил на сообщение Commit или Rollback в течение заданного времени.</span><span class="sxs-lookup"><span data-stu-id="0b7f8-106">Traced when a Volatile participant has decided to Commit or Abort but has not responded to a Commit or Rollback request within a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="0b7f8-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="0b7f8-107">Troubleshooting</span></span>  
 <span data-ttu-id="0b7f8-108">Убедитесь, что все неустойчивые участники имеют возможность ответить в течение заданного времени.</span><span class="sxs-lookup"><span data-stu-id="0b7f8-108">Ensure that all Volatile participants are able to respond within the given amount of time.</span></span> <span data-ttu-id="0b7f8-109">Период времени по умолчанию - 180 секунд.</span><span class="sxs-lookup"><span data-stu-id="0b7f8-109">The default time period is 180 seconds.</span></span>  <span data-ttu-id="0b7f8-110">Если этого недостаточно, увеличьте значение политики таймера `VolatileOutcomeDelay` для протокола WS-AT.</span><span class="sxs-lookup"><span data-stu-id="0b7f8-110">If this is insufficient, increase the `VolatileOutcomeDelay` timer policy for WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b7f8-111">См. также</span><span class="sxs-lookup"><span data-stu-id="0b7f8-111">See Also</span></span>  
 [<span data-ttu-id="0b7f8-112">Трассировка</span><span class="sxs-lookup"><span data-stu-id="0b7f8-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="0b7f8-113">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="0b7f8-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="0b7f8-114">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="0b7f8-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
