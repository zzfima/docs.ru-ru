---
title: Microsoft.Transactions.TransactionBridge.PreparedMessageRetry
ms.date: 03/30/2017
ms.assetid: 2194292d-bf5f-4aef-9336-cd3c4795cb71
ms.openlocfilehash: ba35f948143aff3de575e966aaec87f32f6f14b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473780"
---
# <a name="microsofttransactionstransactionbridgepreparedmessageretry"></a><span data-ttu-id="afbe0-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span><span class="sxs-lookup"><span data-stu-id="afbe0-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span></span>
<span data-ttu-id="afbe0-103">Координатору, который не отвечает, было повторно отправлено сообщение готовности.</span><span class="sxs-lookup"><span data-stu-id="afbe0-103">A prepared message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="afbe0-104">Описание</span><span class="sxs-lookup"><span data-stu-id="afbe0-104">Description</span></span>  
 <span data-ttu-id="afbe0-105">Трассируется, если локальному диспетчеру транзакций потребовалось повторно отправить сообщение готовности ("Prepared") вышестоящему координатору, так как за заданное время не был получен отклик.</span><span class="sxs-lookup"><span data-stu-id="afbe0-105">Traced if the local Transaction Manager needed to resend a Prepared message to a superior coordinator because it did not receive a response in a given amount of time/</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="afbe0-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="afbe0-106">Troubleshooting</span></span>  
 <span data-ttu-id="afbe0-107">Рассмотрите потенциальные проблемы с сетью или продуктом, которые могут препятствовать своевременной доставке отклика.</span><span class="sxs-lookup"><span data-stu-id="afbe0-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="afbe0-108">Если таких сообщений много, это может указывать на проблемы инфраструктуры или чрезмерно большое время отклика.</span><span class="sxs-lookup"><span data-stu-id="afbe0-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="afbe0-109">Обе проблемы значительно снижают пропускную способность транзакций в системе.</span><span class="sxs-lookup"><span data-stu-id="afbe0-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afbe0-110">См. также</span><span class="sxs-lookup"><span data-stu-id="afbe0-110">See Also</span></span>  
 [<span data-ttu-id="afbe0-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="afbe0-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="afbe0-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="afbe0-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="afbe0-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="afbe0-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
