---
title: Microsoft.Transactions.TransactionBridge.PreparedMessageRetry
ms.date: 03/30/2017
ms.assetid: 2194292d-bf5f-4aef-9336-cd3c4795cb71
ms.openlocfilehash: d8acdb2f94e752860025ee2963aa78682b43b079
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216916"
---
# <a name="microsofttransactionstransactionbridgepreparedmessageretry"></a><span data-ttu-id="eca6e-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span><span class="sxs-lookup"><span data-stu-id="eca6e-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span></span>
<span data-ttu-id="eca6e-103">Координатору, который не отвечает, было повторно отправлено сообщение готовности.</span><span class="sxs-lookup"><span data-stu-id="eca6e-103">A prepared message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="eca6e-104">Описание</span><span class="sxs-lookup"><span data-stu-id="eca6e-104">Description</span></span>  
 <span data-ttu-id="eca6e-105">Трассируется, если локальному диспетчеру транзакций потребовалось повторно отправить сообщение готовности ("Prepared") вышестоящему координатору, так как за заданное время не был получен отклик.</span><span class="sxs-lookup"><span data-stu-id="eca6e-105">Traced if the local Transaction Manager needed to resend a Prepared message to a superior coordinator because it did not receive a response in a given amount of time/</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="eca6e-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="eca6e-106">Troubleshooting</span></span>  
 <span data-ttu-id="eca6e-107">Рассмотрите потенциальные проблемы с сетью или продуктом, которые могут препятствовать своевременной доставке отклика.</span><span class="sxs-lookup"><span data-stu-id="eca6e-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="eca6e-108">Если таких сообщений много, это может указывать на проблемы инфраструктуры или чрезмерно большое время отклика.</span><span class="sxs-lookup"><span data-stu-id="eca6e-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="eca6e-109">Обе проблемы значительно снижают пропускную способность транзакций в системе.</span><span class="sxs-lookup"><span data-stu-id="eca6e-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eca6e-110">См. также</span><span class="sxs-lookup"><span data-stu-id="eca6e-110">See also</span></span>

- [<span data-ttu-id="eca6e-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="eca6e-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="eca6e-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="eca6e-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="eca6e-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="eca6e-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
