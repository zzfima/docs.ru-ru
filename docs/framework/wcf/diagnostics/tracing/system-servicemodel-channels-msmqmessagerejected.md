---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3194409ef6daf417d3643eed20afa18944e29ad3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="ce428-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="ce428-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="ce428-103">MSMQ отклонила сообщение.</span><span class="sxs-lookup"><span data-stu-id="ce428-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ce428-104">Описание</span><span class="sxs-lookup"><span data-stu-id="ce428-104">Description</span></span>  
 <span data-ttu-id="ce428-105">Эта трассировка указывает, что сообщение MSMQ было отклонено.</span><span class="sxs-lookup"><span data-stu-id="ce428-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="ce428-106">Сообщения MSMQ могут быть отклонены, если [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (используемый либо с классом NetMsmqBinding, либо с классом MsmqIntegrationBinding) не способен их обработать.</span><span class="sxs-lookup"><span data-stu-id="ce428-106">MSMQ messages can be rejected when [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="ce428-107">Такие сообщения считаются подозрительными.</span><span class="sxs-lookup"><span data-stu-id="ce428-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="ce428-108">Подозрительное сообщение отклоняется, если свойству `ReceiveErrorHandling` класса NetMsmqBinding или класса MsmqIntegrationBinding присвоено значение `Reject`.</span><span class="sxs-lookup"><span data-stu-id="ce428-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="ce428-109">Отклоненные сообщение доставляется отправителя [очереди недоставленных сообщений](http://go.microsoft.com/fwlink/?LinkID=99544).</span><span class="sxs-lookup"><span data-stu-id="ce428-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](http://go.microsoft.com/fwlink/?LinkID=99544).</span></span>  
  
 <span data-ttu-id="ce428-110">В разделе [обработка подозрительных сообщений](http://go.microsoft.com/fwlink/?LinkID=99546) Дополнительные сведения о при сообщения становятся подозрительными и как настроить службу для их правильной обработки.</span><span class="sxs-lookup"><span data-stu-id="ce428-110">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
 <span data-ttu-id="ce428-111">В разделе [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548) для получения дополнительных сведений о означает отклоненных сообщений в MSMQ.</span><span class="sxs-lookup"><span data-stu-id="ce428-111">See [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce428-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ce428-112">See Also</span></span>  
 [<span data-ttu-id="ce428-113">Трассировка</span><span class="sxs-lookup"><span data-stu-id="ce428-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="ce428-114">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="ce428-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="ce428-115">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="ce428-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="ce428-116">Обработка подозрительных сообщений</span><span class="sxs-lookup"><span data-stu-id="ce428-116">Poison-Message Handling</span></span>](http://go.microsoft.com/fwlink/?LinkID=99546)  
 [<span data-ttu-id="ce428-117">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="ce428-117">MQMarkMessageRejected</span></span>](http://go.microsoft.com/fwlink/?LinkID=99548)
