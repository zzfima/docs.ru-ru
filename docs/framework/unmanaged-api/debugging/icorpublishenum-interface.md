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
ms.openlocfilehash: 7d083655326333f18ee98f8e84fff2ed182dde6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103454"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="411ee-102">Интерфейс ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="411ee-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="411ee-103">Служит абстрактным базовым интерфейсом для перечислителей, используемых в публикации сведений о процессах и доменах приложений.</span><span class="sxs-lookup"><span data-stu-id="411ee-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="411ee-104">Методы</span><span class="sxs-lookup"><span data-stu-id="411ee-104">Methods</span></span>  
  
|<span data-ttu-id="411ee-105">Метод</span><span class="sxs-lookup"><span data-stu-id="411ee-105">Method</span></span>|<span data-ttu-id="411ee-106">Описание</span><span class="sxs-lookup"><span data-stu-id="411ee-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="411ee-107">Метод Clone</span><span class="sxs-lookup"><span data-stu-id="411ee-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|<span data-ttu-id="411ee-108">Создает копию этого объекта `ICorPublishEnum`.</span><span class="sxs-lookup"><span data-stu-id="411ee-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="411ee-109">Метод GetCount</span><span class="sxs-lookup"><span data-stu-id="411ee-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|<span data-ttu-id="411ee-110">Возвращает число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="411ee-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="411ee-111">Метод Reset</span><span class="sxs-lookup"><span data-stu-id="411ee-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|<span data-ttu-id="411ee-112">Перемещает курсор в начало перечисления.</span><span class="sxs-lookup"><span data-stu-id="411ee-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="411ee-113">Метод Skip</span><span class="sxs-lookup"><span data-stu-id="411ee-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|<span data-ttu-id="411ee-114">Перемещает курсор вперед в перечислении на указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="411ee-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="411ee-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="411ee-115">Remarks</span></span>  
 <span data-ttu-id="411ee-116">Следующие перечислители являются производными от `ICorPublishEnum`:</span><span class="sxs-lookup"><span data-stu-id="411ee-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
- [<span data-ttu-id="411ee-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="411ee-117">ICorPublishAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
- [<span data-ttu-id="411ee-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="411ee-118">ICorPublishProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="411ee-119">Требования</span><span class="sxs-lookup"><span data-stu-id="411ee-119">Requirements</span></span>  
 <span data-ttu-id="411ee-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="411ee-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="411ee-121">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="411ee-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="411ee-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="411ee-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="411ee-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="411ee-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="411ee-124">См. также</span><span class="sxs-lookup"><span data-stu-id="411ee-124">See also</span></span>

- [<span data-ttu-id="411ee-125">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="411ee-125">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
- [<span data-ttu-id="411ee-126">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="411ee-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
