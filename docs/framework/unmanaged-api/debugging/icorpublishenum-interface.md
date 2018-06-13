---
title: Интерфейс ICorPublishEnum
ms.date: 03/30/2017
api_name:
- ICorPublishEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum
helpviewer_keywords:
- ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b3536184fa7798ac8eabe851221ec692c126460b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424018"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="b791e-102">Интерфейс ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="b791e-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="b791e-103">Служит абстрактным базовым интерфейсом для перечислителей, которые используются в публикации сведений о процессах и доменах приложения.</span><span class="sxs-lookup"><span data-stu-id="b791e-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b791e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b791e-104">Methods</span></span>  
  
|<span data-ttu-id="b791e-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b791e-105">Method</span></span>|<span data-ttu-id="b791e-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b791e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b791e-107">Метод Clone</span><span class="sxs-lookup"><span data-stu-id="b791e-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|<span data-ttu-id="b791e-108">Создает копию объекта `ICorPublishEnum` объекта.</span><span class="sxs-lookup"><span data-stu-id="b791e-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="b791e-109">Метод GetCount</span><span class="sxs-lookup"><span data-stu-id="b791e-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|<span data-ttu-id="b791e-110">Получает число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="b791e-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="b791e-111">Метод Reset</span><span class="sxs-lookup"><span data-stu-id="b791e-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|<span data-ttu-id="b791e-112">Перемещает курсор в начало перечисления.</span><span class="sxs-lookup"><span data-stu-id="b791e-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="b791e-113">Метод Skip</span><span class="sxs-lookup"><span data-stu-id="b791e-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|<span data-ttu-id="b791e-114">Перемещение курсора вперед в перечислении указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="b791e-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b791e-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="b791e-115">Remarks</span></span>  
 <span data-ttu-id="b791e-116">Следующие перечислители являются производными от `ICorPublishEnum`:</span><span class="sxs-lookup"><span data-stu-id="b791e-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
-   [<span data-ttu-id="b791e-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="b791e-117">ICorPublishAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
-   [<span data-ttu-id="b791e-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="b791e-118">ICorPublishProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="b791e-119">Требования</span><span class="sxs-lookup"><span data-stu-id="b791e-119">Requirements</span></span>  
 <span data-ttu-id="b791e-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b791e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b791e-121">**Заголовок:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="b791e-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b791e-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b791e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b791e-123">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b791e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b791e-124">См. также</span><span class="sxs-lookup"><span data-stu-id="b791e-124">See Also</span></span>  
 [<span data-ttu-id="b791e-125">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="b791e-125">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)  
 [<span data-ttu-id="b791e-126">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b791e-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
