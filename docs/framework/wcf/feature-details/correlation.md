---
title: "Корреляция"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60151f6c-19b7-47af-9cdc-76c2ac95f301
caps.latest.revision: "26"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d15609db250e4743ae2a7a1b6c3c355600704f02
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="correlation"></a><span data-ttu-id="3d63c-102">Корреляция</span><span class="sxs-lookup"><span data-stu-id="3d63c-102">Correlation</span></span>
<span data-ttu-id="3d63c-103">При взаимодействии приложения службы рабочего процесса с другими службами важно обеспечить передачу сообщений соответствующему экземпляру рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="3d63c-103">When workflow service applications communicate with other services, it is important that messages between them are dispatched to the appropriate workflow instance.</span></span> <span data-ttu-id="3d63c-104">Механизм для этого предоставляет корреляция.</span><span class="sxs-lookup"><span data-stu-id="3d63c-104">Correlation provides the mechanism for this.</span></span> <span data-ttu-id="3d63c-105">В подразделах этого раздела приведены общие сведения о корреляции, порядке ее использования в различных сценариях служб рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="3d63c-105">The topics in this section provide an overview of correlation and how to use it in different workflow service scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3d63c-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="3d63c-106">In This Section</span></span>  
 [<span data-ttu-id="3d63c-107">Общие сведения о корреляции</span><span class="sxs-lookup"><span data-stu-id="3d63c-107">Correlation Overview</span></span>](../../../../docs/framework/wcf/feature-details/correlation-overview.md)  
 <span data-ttu-id="3d63c-108">Содержит общие сведения о типах корреляции, доступных в [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d63c-108">Provides an overview of the types of correlation available in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="3d63c-109">Обмен контекстом</span><span class="sxs-lookup"><span data-stu-id="3d63c-109">Context Exchange</span></span>](../../../../docs/framework/wcf/feature-details/context-exchange-correlation.md)  
 <span data-ttu-id="3d63c-110">Описывает корреляцию обмена контекстом.</span><span class="sxs-lookup"><span data-stu-id="3d63c-110">Describes context exchange correlation.</span></span>  
  
 [<span data-ttu-id="3d63c-111">Сохраняемый дуплекс</span><span class="sxs-lookup"><span data-stu-id="3d63c-111">Durable Duplex</span></span>](../../../../docs/framework/wcf/feature-details/durable-duplex-correlation.md)  
 <span data-ttu-id="3d63c-112">Описывает сохраняемую дуплексную корреляцию.</span><span class="sxs-lookup"><span data-stu-id="3d63c-112">Describes durable duplex correlation.</span></span>  
  
 [<span data-ttu-id="3d63c-113">На основе содержимого</span><span class="sxs-lookup"><span data-stu-id="3d63c-113">Content Based</span></span>](../../../../docs/framework/wcf/feature-details/content-based-correlation.md)  
 <span data-ttu-id="3d63c-114">Описывает корреляцию на основе содержимого.</span><span class="sxs-lookup"><span data-stu-id="3d63c-114">Describes content-based correlation.</span></span>  
  
 [<span data-ttu-id="3d63c-115">Запрос ответ</span><span class="sxs-lookup"><span data-stu-id="3d63c-115">Request-Reply</span></span>](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md)  
 <span data-ttu-id="3d63c-116">Описывает корреляцию запросов и ответов.</span><span class="sxs-lookup"><span data-stu-id="3d63c-116">Describes request-reply correlation.</span></span>  
  
 [<span data-ttu-id="3d63c-117">Устранение неполадок корреляции</span><span class="sxs-lookup"><span data-stu-id="3d63c-117">Troubleshooting Correlation</span></span>](../../../../docs/framework/wcf/feature-details/troubleshooting-correlation.md)  
 <span data-ttu-id="3d63c-118">Предоставляет методы для устранения неполадок корреляции.</span><span class="sxs-lookup"><span data-stu-id="3d63c-118">Provides methods for troubleshooting correlation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d63c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="3d63c-119">See Also</span></span>  
 <xref:System.ServiceModel.Activities.CorrelationHandle>  
 <xref:System.ServiceModel.Activities.Send>  
 <xref:System.ServiceModel.Activities.Receive>  
 <xref:System.ServiceModel.CorrelationQuery>  
 [<span data-ttu-id="3d63c-120">Корреляция по содержимому</span><span class="sxs-lookup"><span data-stu-id="3d63c-120">Content-Based Correlation</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/content-based-correlation.md)  
 [<span data-ttu-id="3d63c-121">Калькулятор с корреляцией</span><span class="sxs-lookup"><span data-stu-id="3d63c-121">Correlated Calculator</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/correlated-calculator.md)
