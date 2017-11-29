---
title: Microsoft.Transactions.TransactionBridge.PreparedMessageRetry
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2194292d-bf5f-4aef-9336-cd3c4795cb71
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 88ee90abb10e9f5e09deecb3d3d66c54dc289592
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgepreparedmessageretry"></a><span data-ttu-id="f456f-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span><span class="sxs-lookup"><span data-stu-id="f456f-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span></span>
<span data-ttu-id="f456f-103">Координатору, который не отвечает, было повторно отправлено сообщение готовности.</span><span class="sxs-lookup"><span data-stu-id="f456f-103">A prepared message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f456f-104">Описание</span><span class="sxs-lookup"><span data-stu-id="f456f-104">Description</span></span>  
 <span data-ttu-id="f456f-105">Трассируется, если локальному диспетчеру транзакций потребовалось повторно отправить сообщение готовности ("Prepared") вышестоящему координатору, так как за заданное время не был получен отклик.</span><span class="sxs-lookup"><span data-stu-id="f456f-105">Traced if the local Transaction Manager needed to resend a Prepared message to a superior coordinator because it did not receive a response in a given amount of time/</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="f456f-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="f456f-106">Troubleshooting</span></span>  
 <span data-ttu-id="f456f-107">Рассмотрите потенциальные проблемы с сетью или продуктом, которые могут препятствовать своевременной доставке отклика.</span><span class="sxs-lookup"><span data-stu-id="f456f-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="f456f-108">Если таких сообщений много, это может указывать на проблемы инфраструктуры или чрезмерно большое время отклика.</span><span class="sxs-lookup"><span data-stu-id="f456f-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="f456f-109">Обе проблемы значительно снижают пропускную способность транзакций в системе.</span><span class="sxs-lookup"><span data-stu-id="f456f-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f456f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="f456f-110">See Also</span></span>  
 [<span data-ttu-id="f456f-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="f456f-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="f456f-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="f456f-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="f456f-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="f456f-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
