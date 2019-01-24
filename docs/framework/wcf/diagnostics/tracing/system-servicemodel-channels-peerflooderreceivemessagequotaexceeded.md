---
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.date: 03/30/2017
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
ms.openlocfilehash: 3ce6b3021f47708c222c3ec5a88d474d17106748
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54500997"
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a><span data-ttu-id="563a6-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="563a6-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span></span>
<span data-ttu-id="563a6-103">Скорость получения входящих сообщений слишком высока.</span><span class="sxs-lookup"><span data-stu-id="563a6-103">The inbound receive rate of messages is too high.</span></span>  
  
## <a name="description"></a><span data-ttu-id="563a6-104">Описание</span><span class="sxs-lookup"><span data-stu-id="563a6-104">Description</span></span>  
 <span data-ttu-id="563a6-105">Эта трассировка возникает при попытке обработки входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="563a6-105">This trace occurs when attempting to process inbound messages.</span></span> <span data-ttu-id="563a6-106">Не удалось перенаправить сообщение конкретному соседнему узлу, так как была превышена квота, заданная для этого узла.</span><span class="sxs-lookup"><span data-stu-id="563a6-106">A message could not be forwarded to a specific neighbor because the quota set for that neighbor has been exceeded.</span></span> <span data-ttu-id="563a6-107">Это происходит, если соседнему узлу, который не отвечает, не удается очистить журнал ожидания сообщений для этого узла.</span><span class="sxs-lookup"><span data-stu-id="563a6-107">This occurs when an unresponsive neighbor fails to clear a backlog of messages pending for that neighbor.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="563a6-108">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="563a6-108">Troubleshooting</span></span>  
 <span data-ttu-id="563a6-109">Необходимо снизить частоту отправки сообщений в этой сетке.</span><span class="sxs-lookup"><span data-stu-id="563a6-109">Reduce the rate at which messages are sent within the mesh.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="563a6-110">См. также</span><span class="sxs-lookup"><span data-stu-id="563a6-110">See also</span></span>
- [<span data-ttu-id="563a6-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="563a6-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="563a6-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="563a6-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="563a6-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="563a6-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
