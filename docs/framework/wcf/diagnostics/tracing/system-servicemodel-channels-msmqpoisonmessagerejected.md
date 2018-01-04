---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 28924f04dc83387f49c2369c2598c028f9b8d4bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="a62e6-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="a62e6-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="a62e6-103">Подозрительное сообщение отклонено.</span><span class="sxs-lookup"><span data-stu-id="a62e6-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a62e6-104">Описание:</span><span class="sxs-lookup"><span data-stu-id="a62e6-104">Description</span></span>  
 <span data-ttu-id="a62e6-105">Указывает, что было обнаружено и отклонено подозрительное сообщение.</span><span class="sxs-lookup"><span data-stu-id="a62e6-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="a62e6-106">Возникает, если свойство `ReceiveErrorHandling` объекта NetMsmqBinding или MsmqIntegrationBinding имеет значение `Reject`.</span><span class="sxs-lookup"><span data-stu-id="a62e6-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="a62e6-107">Отклоненные сообщение доставляется отправителя [очереди недоставленных сообщений](http://go.microsoft.com/fwlink/?LinkId=99544).</span><span class="sxs-lookup"><span data-stu-id="a62e6-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](http://go.microsoft.com/fwlink/?LinkId=99544).</span></span>  
  
 <span data-ttu-id="a62e6-108">В разделе [обработка подозрительных сообщений](http://go.microsoft.com/fwlink/?LinkId=99546) Дополнительные сведения о при сообщения становятся подозрительными и как настроить службу для их правильной обработки.</span><span class="sxs-lookup"><span data-stu-id="a62e6-108">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkId=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span> <span data-ttu-id="a62e6-109">В разделе [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548) для получения дополнительных сведений о означает отклоненных сообщений в MSMQ.</span><span class="sxs-lookup"><span data-stu-id="a62e6-109">See [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a62e6-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a62e6-110">See Also</span></span>  
 [<span data-ttu-id="a62e6-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="a62e6-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="a62e6-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="a62e6-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="a62e6-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="a62e6-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="a62e6-114">Обработка подозрительных сообщений</span><span class="sxs-lookup"><span data-stu-id="a62e6-114">Poison-Message Handling</span></span>](http://go.microsoft.com/fwlink/?LinkId=99546)  
 [<span data-ttu-id="a62e6-115">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="a62e6-115">MQMarkMessageRejected</span></span>](http://go.microsoft.com/fwlink/?LinkId=99548)
