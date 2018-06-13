---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: 6fb1463b811d985f54b9a99e59d1280eaa040256
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33482818"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="37603-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="37603-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="37603-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="37603-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="37603-104">Описание</span><span class="sxs-lookup"><span data-stu-id="37603-104">Description</span></span>  
 <span data-ttu-id="37603-105">При обработке сообщения произошло переключение потоков.</span><span class="sxs-lookup"><span data-stu-id="37603-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="37603-106">Обработка сообщения может быть приостановлена по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="37603-106">Message processing can be paused by the following reasons:</span></span>  
  
-   <span data-ttu-id="37603-107">ConcurrencyMode является единственным или реентерабельным; служба обрабатывает другое сообщение.</span><span class="sxs-lookup"><span data-stu-id="37603-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
-   <span data-ttu-id="37603-108">Транзакция разрешена; служба обрабатывает другую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="37603-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
-   <span data-ttu-id="37603-109">Контекст синхронизации устарел.</span><span class="sxs-lookup"><span data-stu-id="37603-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37603-110">См. также</span><span class="sxs-lookup"><span data-stu-id="37603-110">See Also</span></span>  
 [<span data-ttu-id="37603-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="37603-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="37603-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="37603-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="37603-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="37603-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
