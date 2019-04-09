---
title: Экземпляры
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: 668cfb3026b9ab7259665f5e53873a512b1e2238
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118993"
---
# <a name="instances"></a><span data-ttu-id="2dcdb-102">Экземпляры</span><span class="sxs-lookup"><span data-stu-id="2dcdb-102">Instances</span></span>
<span data-ttu-id="2dcdb-103">Имя счетчика: экземпляры.</span><span class="sxs-lookup"><span data-stu-id="2dcdb-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2dcdb-104">Описание</span><span class="sxs-lookup"><span data-stu-id="2dcdb-104">Description</span></span>  
 <span data-ttu-id="2dcdb-105">Число контекстов экземпляра, которое в настоящий момент содержит служба.</span><span class="sxs-lookup"><span data-stu-id="2dcdb-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="2dcdb-106">В большинстве случаев число контекстов экземпляра идентично числу экземпляров.</span><span class="sxs-lookup"><span data-stu-id="2dcdb-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="2dcdb-107">Однако приведенные ниже сценарии являются исключением из этого правила.</span><span class="sxs-lookup"><span data-stu-id="2dcdb-107">However, the following scenarios are exception to this rule.</span></span>  
  
-   <span data-ttu-id="2dcdb-108">Метод службы явным образом вызывает метод <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>.</span><span class="sxs-lookup"><span data-stu-id="2dcdb-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
-   <span data-ttu-id="2dcdb-109"><xref:System.ServiceModel.ReleaseInstanceMode> применяется к экземпляру <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2dcdb-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dcdb-110">См. также</span><span class="sxs-lookup"><span data-stu-id="2dcdb-110">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
