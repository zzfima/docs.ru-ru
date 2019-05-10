---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: 7dcdb9fdd6a283f692897cbbb49cd1f2d1dd661e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586793"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="edd28-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="edd28-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="edd28-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="edd28-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="edd28-104">Описание</span><span class="sxs-lookup"><span data-stu-id="edd28-104">Description</span></span>  
 <span data-ttu-id="edd28-105">При обработке сообщения произошло переключение потоков.</span><span class="sxs-lookup"><span data-stu-id="edd28-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="edd28-106">Обработка сообщения может быть приостановлена по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="edd28-106">Message processing can be paused by the following reasons:</span></span>  
  
- <span data-ttu-id="edd28-107">ConcurrencyMode является единственным или реентерабельным; служба обрабатывает другое сообщение.</span><span class="sxs-lookup"><span data-stu-id="edd28-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
- <span data-ttu-id="edd28-108">Транзакция разрешена; служба обрабатывает другую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="edd28-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
- <span data-ttu-id="edd28-109">Контекст синхронизации устарел.</span><span class="sxs-lookup"><span data-stu-id="edd28-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edd28-110">См. также</span><span class="sxs-lookup"><span data-stu-id="edd28-110">See also</span></span>

- [<span data-ttu-id="edd28-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="edd28-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="edd28-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="edd28-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="edd28-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="edd28-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
