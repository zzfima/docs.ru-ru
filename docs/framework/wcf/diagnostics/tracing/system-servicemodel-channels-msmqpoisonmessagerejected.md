---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: c8e476ab90fda9214831fbd5beaba518f3e3bd20
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491432"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="006cc-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="006cc-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="006cc-103">Подозрительное сообщение отклонено.</span><span class="sxs-lookup"><span data-stu-id="006cc-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="006cc-104">Описание:</span><span class="sxs-lookup"><span data-stu-id="006cc-104">Description</span></span>  
 <span data-ttu-id="006cc-105">Указывает, что было обнаружено и отклонено подозрительное сообщение.</span><span class="sxs-lookup"><span data-stu-id="006cc-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="006cc-106">Возникает, если свойство `ReceiveErrorHandling` объекта NetMsmqBinding или MsmqIntegrationBinding имеет значение `Reject`.</span><span class="sxs-lookup"><span data-stu-id="006cc-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="006cc-107">Отклоненное сообщение доставляется отправителя [очередь недоставленных сообщений](https://go.microsoft.com/fwlink/?LinkId=99544).</span><span class="sxs-lookup"><span data-stu-id="006cc-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://go.microsoft.com/fwlink/?LinkId=99544).</span></span>  
  
 <span data-ttu-id="006cc-108">См. в разделе [обработка подозрительных сообщений](https://go.microsoft.com/fwlink/?LinkId=99546) узнать больше о при сообщения становятся подозрительными и как настроить службу для их правильной обработки.</span><span class="sxs-lookup"><span data-stu-id="006cc-108">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkId=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span> <span data-ttu-id="006cc-109">См. в разделе [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkId=99548) Дополнительные сведения о значении отклоненных сообщений в MSMQ.</span><span class="sxs-lookup"><span data-stu-id="006cc-109">See [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkId=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="006cc-110">См. также</span><span class="sxs-lookup"><span data-stu-id="006cc-110">See also</span></span>
- [<span data-ttu-id="006cc-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="006cc-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="006cc-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="006cc-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="006cc-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="006cc-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="006cc-114">Обработка подозрительных сообщений</span><span class="sxs-lookup"><span data-stu-id="006cc-114">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkId=99546)
- [<span data-ttu-id="006cc-115">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="006cc-115">MQMarkMessageRejected</span></span>](https://go.microsoft.com/fwlink/?LinkId=99548)
