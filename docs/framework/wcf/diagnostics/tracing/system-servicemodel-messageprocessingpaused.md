---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: ba067303d861bbd7d88c67f6fd868bd808e07dfd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528684"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="b75f3-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="b75f3-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="b75f3-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="b75f3-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="b75f3-104">Описание</span><span class="sxs-lookup"><span data-stu-id="b75f3-104">Description</span></span>  
 <span data-ttu-id="b75f3-105">При обработке сообщения произошло переключение потоков.</span><span class="sxs-lookup"><span data-stu-id="b75f3-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="b75f3-106">Обработка сообщения может быть приостановлена по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="b75f3-106">Message processing can be paused by the following reasons:</span></span>  
  
-   <span data-ttu-id="b75f3-107">ConcurrencyMode является единственным или реентерабельным; служба обрабатывает другое сообщение.</span><span class="sxs-lookup"><span data-stu-id="b75f3-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
-   <span data-ttu-id="b75f3-108">Транзакция разрешена; служба обрабатывает другую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="b75f3-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
-   <span data-ttu-id="b75f3-109">Контекст синхронизации устарел.</span><span class="sxs-lookup"><span data-stu-id="b75f3-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b75f3-110">См. также</span><span class="sxs-lookup"><span data-stu-id="b75f3-110">See also</span></span>
- [<span data-ttu-id="b75f3-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="b75f3-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="b75f3-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="b75f3-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="b75f3-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="b75f3-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
