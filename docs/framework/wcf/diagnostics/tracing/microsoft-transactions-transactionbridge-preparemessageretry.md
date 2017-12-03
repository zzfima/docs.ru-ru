---
title: Microsoft.Transactions.TransactionBridge.PrepareMessageRetry
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ada4baa5-b60d-46b8-ad46-4d69f8d8a9fa
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7b53620a08d21d40a230f82b3b2b3ea3cd05feea
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="microsofttransactionstransactionbridgepreparemessageretry"></a><span data-ttu-id="b72e7-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span><span class="sxs-lookup"><span data-stu-id="b72e7-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span></span>
<span data-ttu-id="b72e7-103">Повторная попытка сообщения подготовки была отправлена участнику, который не отвечает.</span><span class="sxs-lookup"><span data-stu-id="b72e7-103">A prepare message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b72e7-104">Описание</span><span class="sxs-lookup"><span data-stu-id="b72e7-104">Description</span></span>  
 <span data-ttu-id="b72e7-105">Трассируется, потребовалось ли локальному диспетчеру транзакций заново отправить сообщение подготовки подчиненному участнику, так как за заданное время не был получен отклик.</span><span class="sxs-lookup"><span data-stu-id="b72e7-105">Traced if the local Transaction Manager needed to resend a Prepare message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="b72e7-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="b72e7-106">Troubleshooting</span></span>  
 <span data-ttu-id="b72e7-107">Рассмотрите потенциальные проблемы с сетью или продуктом, которые могут препятствовать своевременной доставке отклика.</span><span class="sxs-lookup"><span data-stu-id="b72e7-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="b72e7-108">Если таких сообщений много, это может указывать на проблемы инфраструктуры или чрезмерно большое время отклика.</span><span class="sxs-lookup"><span data-stu-id="b72e7-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="b72e7-109">Обе проблемы могут значительно снизить пропускную способность транзакций в системе.</span><span class="sxs-lookup"><span data-stu-id="b72e7-109">Both issues can drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b72e7-110">См. также</span><span class="sxs-lookup"><span data-stu-id="b72e7-110">See Also</span></span>  
 [<span data-ttu-id="b72e7-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="b72e7-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="b72e7-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="b72e7-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="b72e7-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="b72e7-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
