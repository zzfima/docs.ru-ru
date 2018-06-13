---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: 7dc1e4120caae7c4a592067f5e77ed4f56e82e6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33478170"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="f41b7-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="f41b7-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="f41b7-103">Подозрительное сообщение отклонено.</span><span class="sxs-lookup"><span data-stu-id="f41b7-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f41b7-104">Описание</span><span class="sxs-lookup"><span data-stu-id="f41b7-104">Description</span></span>  
 <span data-ttu-id="f41b7-105">Указывает, что было обнаружено и отклонено подозрительное сообщение.</span><span class="sxs-lookup"><span data-stu-id="f41b7-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="f41b7-106">Возникает, если свойство `ReceiveErrorHandling` объекта NetMsmqBinding или MsmqIntegrationBinding имеет значение `Reject`.</span><span class="sxs-lookup"><span data-stu-id="f41b7-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="f41b7-107">Отклоненные сообщение доставляется отправителя [очереди недоставленных сообщений](http://go.microsoft.com/fwlink/?LinkId=99544).</span><span class="sxs-lookup"><span data-stu-id="f41b7-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](http://go.microsoft.com/fwlink/?LinkId=99544).</span></span>  
  
 <span data-ttu-id="f41b7-108">В разделе [обработка подозрительных сообщений](http://go.microsoft.com/fwlink/?LinkId=99546) Дополнительные сведения о при сообщения становятся подозрительными и как настроить службу для их правильной обработки.</span><span class="sxs-lookup"><span data-stu-id="f41b7-108">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkId=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span> <span data-ttu-id="f41b7-109">В разделе [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548) для получения дополнительных сведений о означает отклоненных сообщений в MSMQ.</span><span class="sxs-lookup"><span data-stu-id="f41b7-109">See [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f41b7-110">См. также</span><span class="sxs-lookup"><span data-stu-id="f41b7-110">See Also</span></span>  
 [<span data-ttu-id="f41b7-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="f41b7-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="f41b7-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="f41b7-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="f41b7-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="f41b7-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="f41b7-114">Обработка подозрительных сообщений</span><span class="sxs-lookup"><span data-stu-id="f41b7-114">Poison-Message Handling</span></span>](http://go.microsoft.com/fwlink/?LinkId=99546)  
 [<span data-ttu-id="f41b7-115">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="f41b7-115">MQMarkMessageRejected</span></span>](http://go.microsoft.com/fwlink/?LinkId=99548)
