---
title: Экземпляры
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: e0be9c93b5efe17235dbccd426cdd73fbb739361
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651837"
---
# <a name="instances"></a><span data-ttu-id="915ce-102">Экземпляры</span><span class="sxs-lookup"><span data-stu-id="915ce-102">Instances</span></span>
<span data-ttu-id="915ce-103">Имя счетчика: экземпляры.</span><span class="sxs-lookup"><span data-stu-id="915ce-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="915ce-104">Описание</span><span class="sxs-lookup"><span data-stu-id="915ce-104">Description</span></span>  
 <span data-ttu-id="915ce-105">Число контекстов экземпляра, которое в настоящий момент содержит служба.</span><span class="sxs-lookup"><span data-stu-id="915ce-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="915ce-106">В большинстве случаев число контекстов экземпляра идентично числу экземпляров.</span><span class="sxs-lookup"><span data-stu-id="915ce-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="915ce-107">Однако приведенные ниже сценарии являются исключением из этого правила.</span><span class="sxs-lookup"><span data-stu-id="915ce-107">However, the following scenarios are exception to this rule.</span></span>  
  
- <span data-ttu-id="915ce-108">Метод службы явным образом вызывает метод <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>.</span><span class="sxs-lookup"><span data-stu-id="915ce-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
- <span data-ttu-id="915ce-109"><xref:System.ServiceModel.ReleaseInstanceMode> применяется к экземпляру <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="915ce-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="915ce-110">См. также</span><span class="sxs-lookup"><span data-stu-id="915ce-110">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
