---
title: System.ServiceModel.MessageProcessingPaused
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 33d05eaa94ec0efdf6d18d03d9d38bda6f0c9eb7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="8ca2c-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="8ca2c-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="8ca2c-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="8ca2c-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="8ca2c-104">Описание</span><span class="sxs-lookup"><span data-stu-id="8ca2c-104">Description</span></span>  
 <span data-ttu-id="8ca2c-105">При обработке сообщения произошло переключение потоков.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="8ca2c-106">Обработка сообщения может быть приостановлена по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="8ca2c-106">Message processing can be paused by the following reasons:</span></span>  
  
-   <span data-ttu-id="8ca2c-107">ConcurrencyMode является единственным или реентерабельным; служба обрабатывает другое сообщение.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
-   <span data-ttu-id="8ca2c-108">Транзакция разрешена; служба обрабатывает другую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
-   <span data-ttu-id="8ca2c-109">Контекст синхронизации устарел.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ca2c-110">См. также</span><span class="sxs-lookup"><span data-stu-id="8ca2c-110">See Also</span></span>  
 [<span data-ttu-id="8ca2c-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="8ca2c-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="8ca2c-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="8ca2c-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="8ca2c-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="8ca2c-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
