---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: e80fecf508158dcb53f08b75c8f9486c13e403a4
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674801"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="10abe-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="10abe-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="10abe-103">Сообщение удалено из очереди MSMQ.</span><span class="sxs-lookup"><span data-stu-id="10abe-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="10abe-104">Описание</span><span class="sxs-lookup"><span data-stu-id="10abe-104">Description</span></span>  
 <span data-ttu-id="10abe-105">Данная трассировка указывает, что сообщение MSMQ было удалено.</span><span class="sxs-lookup"><span data-stu-id="10abe-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="10abe-106">Сообщения МСМЗ могут быть удалены, когда Windows Communication Foundation (WCF) (используется либо с NetMsmqBinding, либо msmqIntegrationBinding) не может их обрабатывать.</span><span class="sxs-lookup"><span data-stu-id="10abe-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="10abe-107">Такие сообщения считаются подозрительными.</span><span class="sxs-lookup"><span data-stu-id="10abe-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="10abe-108">Подозрительное сообщение отбрасывается, если свойству `ReceiveErrorHandling` класса NetMsmqBinding или класса MsmqIntegrationBinding присвоено значение `Drop`.</span><span class="sxs-lookup"><span data-stu-id="10abe-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="10abe-109">Такое сообщение удаляется из очереди, и восстановить его после этого невозможно.</span><span class="sxs-lookup"><span data-stu-id="10abe-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="10abe-110">Для получения дополнительной информации о том, когда сообщения становятся ядом и как настроить свой сервис для их надлежащей обработки, [см.](../../feature-details/poison-message-handling.md)</span><span class="sxs-lookup"><span data-stu-id="10abe-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10abe-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="10abe-111">See also</span></span>

- [<span data-ttu-id="10abe-112">Трассировки</span><span class="sxs-lookup"><span data-stu-id="10abe-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="10abe-113">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="10abe-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="10abe-114">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="10abe-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="10abe-115">Обработка подозрительных сообщений</span><span class="sxs-lookup"><span data-stu-id="10abe-115">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
