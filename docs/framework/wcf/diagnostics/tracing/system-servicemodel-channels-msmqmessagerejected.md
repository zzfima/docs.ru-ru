---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 0addf987eac62c750a3c418e1b1c431d3f9bc1b0
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2018
ms.locfileid: "44707832"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="b6e82-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="b6e82-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="b6e82-103">MSMQ отклонила сообщение.</span><span class="sxs-lookup"><span data-stu-id="b6e82-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b6e82-104">Описание</span><span class="sxs-lookup"><span data-stu-id="b6e82-104">Description</span></span>  
 <span data-ttu-id="b6e82-105">Данная Трассировка показывает, что сообщение MSMQ было отклонено.</span><span class="sxs-lookup"><span data-stu-id="b6e82-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="b6e82-106">Сообщения MSMQ можно отклонить, когда Windows Communication Foundation (WCF) (используется с классом NetMsmqBinding или MsmqIntegrationBinding) не может их обработать.</span><span class="sxs-lookup"><span data-stu-id="b6e82-106">MSMQ messages can be rejected when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="b6e82-107">Такие сообщения считаются подозрительными.</span><span class="sxs-lookup"><span data-stu-id="b6e82-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="b6e82-108">Подозрительное сообщение отклоняется, если свойству `ReceiveErrorHandling` класса NetMsmqBinding или класса MsmqIntegrationBinding присвоено значение `Reject`.</span><span class="sxs-lookup"><span data-stu-id="b6e82-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="b6e82-109">Отклоненное сообщение доставляется отправителя [очередь недоставленных сообщений](https://go.microsoft.com/fwlink/?LinkID=99544).</span><span class="sxs-lookup"><span data-stu-id="b6e82-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://go.microsoft.com/fwlink/?LinkID=99544).</span></span>  
  
 <span data-ttu-id="b6e82-110">См. в разделе [обработка подозрительных сообщений](https://go.microsoft.com/fwlink/?LinkID=99546) узнать больше о при сообщения становятся подозрительными и как настроить службу для их правильной обработки.</span><span class="sxs-lookup"><span data-stu-id="b6e82-110">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
 <span data-ttu-id="b6e82-111">См. в разделе [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkID=99548) Дополнительные сведения о значении отклоненных сообщений в MSMQ.</span><span class="sxs-lookup"><span data-stu-id="b6e82-111">See [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkID=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6e82-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b6e82-112">See Also</span></span>  
 [<span data-ttu-id="b6e82-113">Трассировка</span><span class="sxs-lookup"><span data-stu-id="b6e82-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="b6e82-114">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="b6e82-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="b6e82-115">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="b6e82-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="b6e82-116">Обработка подозрительных сообщений</span><span class="sxs-lookup"><span data-stu-id="b6e82-116">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkID=99546)  
 [<span data-ttu-id="b6e82-117">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="b6e82-117">MQMarkMessageRejected</span></span>](https://go.microsoft.com/fwlink/?LinkID=99548)
