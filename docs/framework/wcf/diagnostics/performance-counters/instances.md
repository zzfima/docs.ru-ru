---
title: Экземпляры
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: a95acf8e775e0802dc0ed781c562fa6373995a70
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473046"
---
# <a name="instances"></a><span data-ttu-id="7252a-102">Экземпляры</span><span class="sxs-lookup"><span data-stu-id="7252a-102">Instances</span></span>
<span data-ttu-id="7252a-103">Имя счетчика: Instances.</span><span class="sxs-lookup"><span data-stu-id="7252a-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7252a-104">Описание</span><span class="sxs-lookup"><span data-stu-id="7252a-104">Description</span></span>  
 <span data-ttu-id="7252a-105">Число контекстов экземпляра, которое в настоящий момент содержит служба.</span><span class="sxs-lookup"><span data-stu-id="7252a-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="7252a-106">В большинстве случаев число контекстов экземпляра идентично числу экземпляров.</span><span class="sxs-lookup"><span data-stu-id="7252a-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="7252a-107">Однако приведенные ниже сценарии являются исключением из этого правила.</span><span class="sxs-lookup"><span data-stu-id="7252a-107">However, the following scenarios are exception to this rule.</span></span>  
  
-   <span data-ttu-id="7252a-108">Метод службы явным образом вызывает метод <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>.</span><span class="sxs-lookup"><span data-stu-id="7252a-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
-   <span data-ttu-id="7252a-109"><xref:System.ServiceModel.ReleaseInstanceMode> применяется к экземпляру <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="7252a-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7252a-110">См. также</span><span class="sxs-lookup"><span data-stu-id="7252a-110">See Also</span></span>  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
