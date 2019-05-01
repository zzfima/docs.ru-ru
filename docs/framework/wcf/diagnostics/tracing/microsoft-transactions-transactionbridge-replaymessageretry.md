---
title: Microsoft.Transactions.TransactionBridge.ReplayMessageRetry
ms.date: 03/30/2017
ms.assetid: e5b820ae-504d-405a-926a-9effa41d2369
ms.openlocfilehash: 0c9e79709f5929e1fa123a8d1695ca720046e9e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61997528"
---
# <a name="microsofttransactionstransactionbridgereplaymessageretry"></a><span data-ttu-id="43016-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span><span class="sxs-lookup"><span data-stu-id="43016-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span></span>
<span data-ttu-id="43016-103">Координатору, который не отвечает, было повторно отправлено сообщение Replay.</span><span class="sxs-lookup"><span data-stu-id="43016-103">A replay message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="43016-104">Описание</span><span class="sxs-lookup"><span data-stu-id="43016-104">Description</span></span>  
 <span data-ttu-id="43016-105">Трассируется, если локальному диспетчеру транзакций потребовалось повторно отправить сообщение Replay вышестоящему координатору, так как за заданное время не был получен отклик.</span><span class="sxs-lookup"><span data-stu-id="43016-105">Traced if the local Transaction Manager needed to resend a Replay message to a superior coordinator because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="43016-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="43016-106">Troubleshooting</span></span>  
 <span data-ttu-id="43016-107">Рассмотрите потенциальные проблемы с сетью или продуктом, которые могут препятствовать своевременной доставке отклика.</span><span class="sxs-lookup"><span data-stu-id="43016-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="43016-108">Если таких сообщений много, это может указывать на проблемы инфраструктуры или чрезмерно большое время отклика.</span><span class="sxs-lookup"><span data-stu-id="43016-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="43016-109">Обе проблемы значительно снижают пропускную способность транзакций в системе.</span><span class="sxs-lookup"><span data-stu-id="43016-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43016-110">См. также</span><span class="sxs-lookup"><span data-stu-id="43016-110">See also</span></span>

- [<span data-ttu-id="43016-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="43016-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="43016-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="43016-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="43016-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="43016-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
