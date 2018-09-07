---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 07bef8b391a03f2c011e1d1a7c7fb4fad908e022
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44067809"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="ae9a5-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="ae9a5-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="ae9a5-103">Сообщение удалено из очереди MSMQ.</span><span class="sxs-lookup"><span data-stu-id="ae9a5-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ae9a5-104">Описание</span><span class="sxs-lookup"><span data-stu-id="ae9a5-104">Description</span></span>  
 <span data-ttu-id="ae9a5-105">Данная трассировка указывает, что сообщение MSMQ было отброшено.</span><span class="sxs-lookup"><span data-stu-id="ae9a5-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="ae9a5-106">Сообщения MSMQ может быть удален, когда Windows Communication Foundation (WCF) (используется с классом NetMsmqBinding или MsmqIntegrationBinding) не может их обработать.</span><span class="sxs-lookup"><span data-stu-id="ae9a5-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="ae9a5-107">Такие сообщения считаются подозрительными.</span><span class="sxs-lookup"><span data-stu-id="ae9a5-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="ae9a5-108">Подозрительное сообщение удаляется, если свойству `ReceiveErrorHandling` класса NetMsmqBinding или класса MsmqIntegrationBinding присвоено значение `Drop`.</span><span class="sxs-lookup"><span data-stu-id="ae9a5-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="ae9a5-109">Такое сообщение удаляется из очереди, и восстановить его после этого невозможно.</span><span class="sxs-lookup"><span data-stu-id="ae9a5-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="ae9a5-110">См. в разделе [обработка подозрительных сообщений](https://go.microsoft.com/fwlink/?LinkID=99546) узнать больше о при сообщения становятся подозрительными и как настроить службу для их правильной обработки.</span><span class="sxs-lookup"><span data-stu-id="ae9a5-110">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae9a5-111">См. также</span><span class="sxs-lookup"><span data-stu-id="ae9a5-111">See Also</span></span>  
 [<span data-ttu-id="ae9a5-112">Трассировка</span><span class="sxs-lookup"><span data-stu-id="ae9a5-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="ae9a5-113">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="ae9a5-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="ae9a5-114">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="ae9a5-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="ae9a5-115">Обработка подозрительных сообщений</span><span class="sxs-lookup"><span data-stu-id="ae9a5-115">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkID=99546)
