---
title: "Экземпляры"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 87423c3de551cb9fbf8c5a7756e2f0f999129a3b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="instances"></a><span data-ttu-id="07449-102">Экземпляры</span><span class="sxs-lookup"><span data-stu-id="07449-102">Instances</span></span>
<span data-ttu-id="07449-103">Имя счетчика: Instances.</span><span class="sxs-lookup"><span data-stu-id="07449-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="07449-104">Описание</span><span class="sxs-lookup"><span data-stu-id="07449-104">Description</span></span>  
 <span data-ttu-id="07449-105">Число контекстов экземпляра, которое в настоящий момент содержит служба.</span><span class="sxs-lookup"><span data-stu-id="07449-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="07449-106">В большинстве случаев число контекстов экземпляра идентично числу экземпляров.</span><span class="sxs-lookup"><span data-stu-id="07449-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="07449-107">Однако приведенные ниже сценарии являются исключением из этого правила.</span><span class="sxs-lookup"><span data-stu-id="07449-107">However, the following scenarios are exception to this rule.</span></span>  
  
-   <span data-ttu-id="07449-108">Метод службы явным образом вызывает метод <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>.</span><span class="sxs-lookup"><span data-stu-id="07449-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
-   <span data-ttu-id="07449-109"><xref:System.ServiceModel.ReleaseInstanceMode> применяется к экземпляру <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="07449-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07449-110">См. также</span><span class="sxs-lookup"><span data-stu-id="07449-110">See Also</span></span>  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
