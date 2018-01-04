---
title: "Интерфейс ICorPublishAppDomainEnum"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishAppDomainEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishAppDomainEnum
helpviewer_keywords: ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f84a93053744f059eb3fdd06e2fb69e098e24ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="06094-102">Интерфейс ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="06094-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="06094-103">Подкласс [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) интерфейс, предоставляющий методы для обхода коллекцию [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) объекты, которые в настоящее время существует внутри процесса.</span><span class="sxs-lookup"><span data-stu-id="06094-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="06094-104">Методы</span><span class="sxs-lookup"><span data-stu-id="06094-104">Methods</span></span>  
  
|<span data-ttu-id="06094-105">Метод</span><span class="sxs-lookup"><span data-stu-id="06094-105">Method</span></span>|<span data-ttu-id="06094-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="06094-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="06094-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="06094-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|<span data-ttu-id="06094-108">Возвращает заданное число `ICorPublishAppDomain` экземпляров из коллекции, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="06094-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06094-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="06094-109">Remarks</span></span>  
 <span data-ttu-id="06094-110">`ICorPublishAppDomainEnum` Интерфейс реализует методы интерфейса абстрактным, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="06094-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06094-111">Требования</span><span class="sxs-lookup"><span data-stu-id="06094-111">Requirements</span></span>  
 <span data-ttu-id="06094-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06094-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06094-113">**Заголовок:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="06094-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="06094-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06094-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06094-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06094-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06094-116">См. также</span><span class="sxs-lookup"><span data-stu-id="06094-116">See Also</span></span>  
 [<span data-ttu-id="06094-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="06094-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="06094-118">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="06094-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
