---
title: Интерфейс ICorPublishAppDomainEnum
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum
helpviewer_keywords:
- ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f6d4af7c01f91dff77d6ba715ef845f523c7fb6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090053"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="6d02f-102">Интерфейс ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="6d02f-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="6d02f-103">Подкласс [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) интерфейс, который предоставляет методы для обхода коллекции [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) объекты, которые в настоящее время существуют внутри процесса.</span><span class="sxs-lookup"><span data-stu-id="6d02f-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6d02f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="6d02f-104">Methods</span></span>  
  
|<span data-ttu-id="6d02f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="6d02f-105">Method</span></span>|<span data-ttu-id="6d02f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="6d02f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6d02f-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="6d02f-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|<span data-ttu-id="6d02f-108">Возвращает заданное число `ICorPublishAppDomain` экземпляров из коллекции, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="6d02f-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d02f-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="6d02f-109">Remarks</span></span>  
 <span data-ttu-id="6d02f-110">`ICorPublishAppDomainEnum` Интерфейс реализует методы интерфейса абстрактный, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6d02f-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d02f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6d02f-111">Requirements</span></span>  
 <span data-ttu-id="6d02f-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d02f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d02f-113">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="6d02f-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6d02f-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d02f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d02f-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d02f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d02f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6d02f-116">See also</span></span>

- [<span data-ttu-id="6d02f-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6d02f-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="6d02f-118">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="6d02f-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
