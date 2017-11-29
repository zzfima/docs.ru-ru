---
title: Microsoft.Transactions.TransactionBridge.CommitMessageRetry
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4abe01f0-6398-4fba-b2f3-c054b7f7e971
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: be874cc0b3fb15f80bb5cd6b97174b515703385c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgecommitmessageretry"></a><span data-ttu-id="95fbc-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span><span class="sxs-lookup"><span data-stu-id="95fbc-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span></span>
<span data-ttu-id="95fbc-103">Повторная попытка сообщения фиксации была отправлена участнику, который не отвечает.</span><span class="sxs-lookup"><span data-stu-id="95fbc-103">A commit message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="95fbc-104">Описание</span><span class="sxs-lookup"><span data-stu-id="95fbc-104">Description</span></span>  
 <span data-ttu-id="95fbc-105">Трассируется, если локальному диспетчеру транзакций потребовалось заново отправить сообщение фиксации подчиненному участнику, так как за заданное время не был получен отклик.</span><span class="sxs-lookup"><span data-stu-id="95fbc-105">Traced if the local Transaction Manager needed to resend a Commit message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="95fbc-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="95fbc-106">Troubleshooting</span></span>  
 <span data-ttu-id="95fbc-107">Рассмотрите потенциальные проблемы с сетью или продуктом, которые могут препятствовать своевременной доставке отклика.</span><span class="sxs-lookup"><span data-stu-id="95fbc-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="95fbc-108">Если таких сообщений много, это может указывать на проблемы инфраструктуры или чрезмерно большое время отклика.</span><span class="sxs-lookup"><span data-stu-id="95fbc-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="95fbc-109">Обе проблемы значительно снижают пропускную способность транзакций в системе.</span><span class="sxs-lookup"><span data-stu-id="95fbc-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95fbc-110">См. также</span><span class="sxs-lookup"><span data-stu-id="95fbc-110">See Also</span></span>  
 [<span data-ttu-id="95fbc-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="95fbc-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="95fbc-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="95fbc-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="95fbc-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="95fbc-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
