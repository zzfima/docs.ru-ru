---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 16b0261a53df29b1fc2049c25375c651735a524c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a><span data-ttu-id="f51d0-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span><span class="sxs-lookup"><span data-stu-id="f51d0-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span></span>
<span data-ttu-id="f51d0-103">Службе протокола WS-AT не удалось зарегистрировать участника для протокола управления.</span><span class="sxs-lookup"><span data-stu-id="f51d0-103">The WS-AT protocol service failed to register a participant for a control protocol.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f51d0-104">Описание</span><span class="sxs-lookup"><span data-stu-id="f51d0-104">Description</span></span>  
 <span data-ttu-id="f51d0-105">Отслеживается, обнаруживает ли MSDTC недопустимый запрос на регистрацию.</span><span class="sxs-lookup"><span data-stu-id="f51d0-105">Traced if MSDTC detects an invalid Registration request.</span></span> <span data-ttu-id="f51d0-106">Это может происходить из-за множественных запросов на регистрацию завершения и внутренних ошибок.</span><span class="sxs-lookup"><span data-stu-id="f51d0-106">This can be caused by  multiple Completion registration requests and internal errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="f51d0-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="f51d0-107">Troubleshooting</span></span>  
 <span data-ttu-id="f51d0-108">Не пытайтесь зарегистрировать завершение несколько раз.</span><span class="sxs-lookup"><span data-stu-id="f51d0-108">Do not try to Register for Completion more than once.</span></span>  <span data-ttu-id="f51d0-109">Проверьте строку состояния в сообщении трассировки, чтобы определить, имеются ли элементы, с которыми можно произвести какие-либо действия.</span><span class="sxs-lookup"><span data-stu-id="f51d0-109">Also, inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f51d0-110">См. также</span><span class="sxs-lookup"><span data-stu-id="f51d0-110">See Also</span></span>  
 [<span data-ttu-id="f51d0-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="f51d0-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="f51d0-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="f51d0-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="f51d0-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="f51d0-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
