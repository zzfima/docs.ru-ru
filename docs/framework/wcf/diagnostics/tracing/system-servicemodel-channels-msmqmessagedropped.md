---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f2f905c345db89e909920334a7dbb524095bc46b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="da95b-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="da95b-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="da95b-103">Сообщение удалено из очереди MSMQ.</span><span class="sxs-lookup"><span data-stu-id="da95b-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="da95b-104">Описание:</span><span class="sxs-lookup"><span data-stu-id="da95b-104">Description</span></span>  
 <span data-ttu-id="da95b-105">Данная трассировка указывает, что сообщение MSMQ было отброшено.</span><span class="sxs-lookup"><span data-stu-id="da95b-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="da95b-106">Сообщения MSMQ могут быть удалены, если [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (при использовании либо с классом NetMsmqBinding, либо с классом MsmqIntegrationBinding) не удается их обработать.</span><span class="sxs-lookup"><span data-stu-id="da95b-106">MSMQ messages can be dropped when [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="da95b-107">Такие сообщения считаются подозрительными.</span><span class="sxs-lookup"><span data-stu-id="da95b-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="da95b-108">Подозрительное сообщение удаляется, если свойству `ReceiveErrorHandling` класса NetMsmqBinding или класса MsmqIntegrationBinding присвоено значение `Drop`.</span><span class="sxs-lookup"><span data-stu-id="da95b-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="da95b-109">Такое сообщение удаляется из очереди, и восстановить его после этого невозможно.</span><span class="sxs-lookup"><span data-stu-id="da95b-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="da95b-110">В разделе [обработка подозрительных сообщений](http://go.microsoft.com/fwlink/?LinkID=99546) Дополнительные сведения о при сообщения становятся подозрительными и как настроить службу для их правильной обработки.</span><span class="sxs-lookup"><span data-stu-id="da95b-110">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da95b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="da95b-111">See Also</span></span>  
 [<span data-ttu-id="da95b-112">Трассировка</span><span class="sxs-lookup"><span data-stu-id="da95b-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="da95b-113">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="da95b-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="da95b-114">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="da95b-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="da95b-115">Обработка подозрительных сообщений</span><span class="sxs-lookup"><span data-stu-id="da95b-115">Poison-Message Handling</span></span>](http://go.microsoft.com/fwlink/?LinkID=99546)
