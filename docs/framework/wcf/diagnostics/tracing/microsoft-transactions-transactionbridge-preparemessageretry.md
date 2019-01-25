---
title: Microsoft.Transactions.TransactionBridge.PrepareMessageRetry
ms.date: 03/30/2017
ms.assetid: ada4baa5-b60d-46b8-ad46-4d69f8d8a9fa
ms.openlocfilehash: f168cb24d87f3159a1ea41003c2ffa7041ce8c09
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710447"
---
# <a name="microsofttransactionstransactionbridgepreparemessageretry"></a><span data-ttu-id="8e5f5-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span><span class="sxs-lookup"><span data-stu-id="8e5f5-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span></span>
<span data-ttu-id="8e5f5-103">Повторная попытка сообщения подготовки была отправлена участнику, который не отвечает.</span><span class="sxs-lookup"><span data-stu-id="8e5f5-103">A prepare message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8e5f5-104">Описание:</span><span class="sxs-lookup"><span data-stu-id="8e5f5-104">Description</span></span>  
 <span data-ttu-id="8e5f5-105">Трассируется, потребовалось ли локальному диспетчеру транзакций заново отправить сообщение подготовки подчиненному участнику, так как за заданное время не был получен отклик.</span><span class="sxs-lookup"><span data-stu-id="8e5f5-105">Traced if the local Transaction Manager needed to resend a Prepare message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="8e5f5-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="8e5f5-106">Troubleshooting</span></span>  
 <span data-ttu-id="8e5f5-107">Рассмотрите потенциальные проблемы с сетью или продуктом, которые могут препятствовать своевременной доставке отклика.</span><span class="sxs-lookup"><span data-stu-id="8e5f5-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="8e5f5-108">Если таких сообщений много, это может указывать на проблемы инфраструктуры или чрезмерно большое время отклика.</span><span class="sxs-lookup"><span data-stu-id="8e5f5-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="8e5f5-109">Обе проблемы могут значительно снизить пропускную способность транзакций в системе.</span><span class="sxs-lookup"><span data-stu-id="8e5f5-109">Both issues can drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e5f5-110">См. также</span><span class="sxs-lookup"><span data-stu-id="8e5f5-110">See also</span></span>
- [<span data-ttu-id="8e5f5-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="8e5f5-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="8e5f5-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="8e5f5-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="8e5f5-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="8e5f5-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
