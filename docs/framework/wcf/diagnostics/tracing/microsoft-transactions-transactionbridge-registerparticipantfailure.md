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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2e3cbe9443f32ec9752198646e96cc1012d7343c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a><span data-ttu-id="efa5a-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span><span class="sxs-lookup"><span data-stu-id="efa5a-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span></span>
<span data-ttu-id="efa5a-103">Службе протокола WS-AT не удалось зарегистрировать участника для протокола управления.</span><span class="sxs-lookup"><span data-stu-id="efa5a-103">The WS-AT protocol service failed to register a participant for a control protocol.</span></span>  
  
## <a name="description"></a><span data-ttu-id="efa5a-104">Описание</span><span class="sxs-lookup"><span data-stu-id="efa5a-104">Description</span></span>  
 <span data-ttu-id="efa5a-105">Отслеживается, обнаруживает ли MSDTC недопустимый запрос на регистрацию.</span><span class="sxs-lookup"><span data-stu-id="efa5a-105">Traced if MSDTC detects an invalid Registration request.</span></span> <span data-ttu-id="efa5a-106">Это может происходить из-за множественных запросов на регистрацию завершения и внутренних ошибок.</span><span class="sxs-lookup"><span data-stu-id="efa5a-106">This can be caused by  multiple Completion registration requests and internal errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="efa5a-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="efa5a-107">Troubleshooting</span></span>  
 <span data-ttu-id="efa5a-108">Не пытайтесь зарегистрировать завершение несколько раз.</span><span class="sxs-lookup"><span data-stu-id="efa5a-108">Do not try to Register for Completion more than once.</span></span>  <span data-ttu-id="efa5a-109">Проверьте строку состояния в сообщении трассировки, чтобы определить, имеются ли элементы, с которыми можно произвести какие-либо действия.</span><span class="sxs-lookup"><span data-stu-id="efa5a-109">Also, inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efa5a-110">См. также</span><span class="sxs-lookup"><span data-stu-id="efa5a-110">See Also</span></span>  
 [<span data-ttu-id="efa5a-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="efa5a-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="efa5a-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="efa5a-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="efa5a-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="efa5a-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
