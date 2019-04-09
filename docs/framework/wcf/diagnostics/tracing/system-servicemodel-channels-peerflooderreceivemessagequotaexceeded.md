---
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.date: 03/30/2017
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
ms.openlocfilehash: 0ca3d198ce225221348ac7b405ea91ad215cd298
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190903"
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a><span data-ttu-id="ec357-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="ec357-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span></span>
<span data-ttu-id="ec357-103">Скорость получения входящих сообщений слишком высока.</span><span class="sxs-lookup"><span data-stu-id="ec357-103">The inbound receive rate of messages is too high.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ec357-104">Описание</span><span class="sxs-lookup"><span data-stu-id="ec357-104">Description</span></span>  
 <span data-ttu-id="ec357-105">Эта трассировка возникает при попытке обработки входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="ec357-105">This trace occurs when attempting to process inbound messages.</span></span> <span data-ttu-id="ec357-106">Не удалось перенаправить сообщение конкретному соседнему узлу, так как была превышена квота, заданная для этого узла.</span><span class="sxs-lookup"><span data-stu-id="ec357-106">A message could not be forwarded to a specific neighbor because the quota set for that neighbor has been exceeded.</span></span> <span data-ttu-id="ec357-107">Это происходит, если соседнему узлу, который не отвечает, не удается очистить журнал ожидания сообщений для этого узла.</span><span class="sxs-lookup"><span data-stu-id="ec357-107">This occurs when an unresponsive neighbor fails to clear a backlog of messages pending for that neighbor.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="ec357-108">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="ec357-108">Troubleshooting</span></span>  
 <span data-ttu-id="ec357-109">Необходимо снизить частоту отправки сообщений в этой сетке.</span><span class="sxs-lookup"><span data-stu-id="ec357-109">Reduce the rate at which messages are sent within the mesh.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec357-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ec357-110">See also</span></span>

- [<span data-ttu-id="ec357-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="ec357-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="ec357-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="ec357-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ec357-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="ec357-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
