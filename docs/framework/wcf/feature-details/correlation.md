---
title: Корреляция
ms.date: 03/30/2017
ms.assetid: 60151f6c-19b7-47af-9cdc-76c2ac95f301
ms.openlocfilehash: 9dbebf6d497a5cc109400d04206d39ad76321ba3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491287"
---
# <a name="correlation"></a><span data-ttu-id="e9d8f-102">Корреляция</span><span class="sxs-lookup"><span data-stu-id="e9d8f-102">Correlation</span></span>
<span data-ttu-id="e9d8f-103">При взаимодействии приложения службы рабочего процесса с другими службами важно обеспечить передачу сообщений соответствующему экземпляру рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-103">When workflow service applications communicate with other services, it is important that messages between them are dispatched to the appropriate workflow instance.</span></span> <span data-ttu-id="e9d8f-104">Механизм для этого предоставляет корреляция.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-104">Correlation provides the mechanism for this.</span></span> <span data-ttu-id="e9d8f-105">В подразделах этого раздела приведены общие сведения о корреляции, порядке ее использования в различных сценариях служб рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-105">The topics in this section provide an overview of correlation and how to use it in different workflow service scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e9d8f-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="e9d8f-106">In This Section</span></span>  
 [<span data-ttu-id="e9d8f-107">Общие сведения о корреляции</span><span class="sxs-lookup"><span data-stu-id="e9d8f-107">Correlation Overview</span></span>](../../../../docs/framework/wcf/feature-details/correlation-overview.md)  
 <span data-ttu-id="e9d8f-108">Содержит общие сведения о типах корреляции, доступных в [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9d8f-108">Provides an overview of the types of correlation available in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="e9d8f-109">Обмен контекстом</span><span class="sxs-lookup"><span data-stu-id="e9d8f-109">Context Exchange</span></span>](../../../../docs/framework/wcf/feature-details/context-exchange-correlation.md)  
 <span data-ttu-id="e9d8f-110">Описывает корреляцию обмена контекстом.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-110">Describes context exchange correlation.</span></span>  
  
 [<span data-ttu-id="e9d8f-111">Сохраняемый дуплекс</span><span class="sxs-lookup"><span data-stu-id="e9d8f-111">Durable Duplex</span></span>](../../../../docs/framework/wcf/feature-details/durable-duplex-correlation.md)  
 <span data-ttu-id="e9d8f-112">Описывает сохраняемую дуплексную корреляцию.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-112">Describes durable duplex correlation.</span></span>  
  
 [<span data-ttu-id="e9d8f-113">На основе содержимого</span><span class="sxs-lookup"><span data-stu-id="e9d8f-113">Content Based</span></span>](../../../../docs/framework/wcf/feature-details/content-based-correlation.md)  
 <span data-ttu-id="e9d8f-114">Описывает корреляцию на основе содержимого.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-114">Describes content-based correlation.</span></span>  
  
 [<span data-ttu-id="e9d8f-115">Запрос-ответ</span><span class="sxs-lookup"><span data-stu-id="e9d8f-115">Request-Reply</span></span>](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md)  
 <span data-ttu-id="e9d8f-116">Описывает корреляцию запросов и ответов.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-116">Describes request-reply correlation.</span></span>  
  
 [<span data-ttu-id="e9d8f-117">Устранение неполадок корреляции</span><span class="sxs-lookup"><span data-stu-id="e9d8f-117">Troubleshooting Correlation</span></span>](../../../../docs/framework/wcf/feature-details/troubleshooting-correlation.md)  
 <span data-ttu-id="e9d8f-118">Предоставляет методы для устранения неполадок корреляции.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-118">Provides methods for troubleshooting correlation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d8f-119">См. также</span><span class="sxs-lookup"><span data-stu-id="e9d8f-119">See Also</span></span>  
 <xref:System.ServiceModel.Activities.CorrelationHandle>  
 <xref:System.ServiceModel.Activities.Send>  
 <xref:System.ServiceModel.Activities.Receive>  
 <xref:System.ServiceModel.CorrelationQuery>  
 [<span data-ttu-id="e9d8f-120">Корреляция по содержимому</span><span class="sxs-lookup"><span data-stu-id="e9d8f-120">Content-Based Correlation</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/content-based-correlation.md)  
 [<span data-ttu-id="e9d8f-121">Калькулятор с корреляцией</span><span class="sxs-lookup"><span data-stu-id="e9d8f-121">Correlated Calculator</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/correlated-calculator.md)
