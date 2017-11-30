---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4cecacdcc9ec1155fbb374bb763f6858da6ccc57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="276c2-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="276c2-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="276c2-103">Не удается переместить или удалить сообщение.</span><span class="sxs-lookup"><span data-stu-id="276c2-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="276c2-104">Описание</span><span class="sxs-lookup"><span data-stu-id="276c2-104">Description</span></span>  
 <span data-ttu-id="276c2-105">Эта трассировка показывает, что при попытке переместить, удалить или отклонить сообщение MSMQ произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="276c2-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="276c2-106">Сообщения MSMQ используются [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (при использовании с привязкой NetMsmqBinding или MsmqIntegrationBinding). Эта трассировка относится к выбранному значению свойства `ReceiveErrorHandling` привязки NetMsmqBinding или MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="276c2-106">MSMQ messages are employed by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="276c2-107">Эта трассировка не указывает на общий сбой системы.</span><span class="sxs-lookup"><span data-stu-id="276c2-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="276c2-108">Однако она показывает, что выбранное средство удаления подозрительного сообщения не подходит для сообщения.</span><span class="sxs-lookup"><span data-stu-id="276c2-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="276c2-109">В разделе [обработка подозрительных сообщений](http://go.microsoft.com/fwlink/?LinkID=99546) Дополнительные сведения о при сообщения становятся подозрительными и как настроить службу для их правильной обработки.</span><span class="sxs-lookup"><span data-stu-id="276c2-109">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="276c2-110">См. также</span><span class="sxs-lookup"><span data-stu-id="276c2-110">See Also</span></span>  
 [<span data-ttu-id="276c2-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="276c2-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="276c2-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="276c2-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="276c2-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="276c2-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
