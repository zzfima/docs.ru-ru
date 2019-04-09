---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: ac1dacef94d6446aa407e4a390b9561d033af1bb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087485"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="53e9e-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="53e9e-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="53e9e-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="53e9e-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="53e9e-104">Описание</span><span class="sxs-lookup"><span data-stu-id="53e9e-104">Description</span></span>  
 <span data-ttu-id="53e9e-105">При обработке сообщения произошло переключение потоков.</span><span class="sxs-lookup"><span data-stu-id="53e9e-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="53e9e-106">Обработка сообщения может быть приостановлена по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="53e9e-106">Message processing can be paused by the following reasons:</span></span>  
  
-   <span data-ttu-id="53e9e-107">ConcurrencyMode является единственным или реентерабельным; служба обрабатывает другое сообщение.</span><span class="sxs-lookup"><span data-stu-id="53e9e-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
-   <span data-ttu-id="53e9e-108">Транзакция разрешена; служба обрабатывает другую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="53e9e-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
-   <span data-ttu-id="53e9e-109">Контекст синхронизации устарел.</span><span class="sxs-lookup"><span data-stu-id="53e9e-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53e9e-110">См. также</span><span class="sxs-lookup"><span data-stu-id="53e9e-110">See also</span></span>

- [<span data-ttu-id="53e9e-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="53e9e-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="53e9e-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="53e9e-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="53e9e-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="53e9e-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
