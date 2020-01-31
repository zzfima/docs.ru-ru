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
ms.openlocfilehash: f54bb99df60d7b3fb7bb98de75fbae210597e45c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790616"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="6f5ba-102">Интерфейс ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="6f5ba-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="6f5ba-103">Служит абстрактным базовым интерфейсом для перечислителей, используемых в публикации сведений о процессах и доменах приложений.</span><span class="sxs-lookup"><span data-stu-id="6f5ba-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6f5ba-104">Методы</span><span class="sxs-lookup"><span data-stu-id="6f5ba-104">Methods</span></span>  
  
|<span data-ttu-id="6f5ba-105">Метод</span><span class="sxs-lookup"><span data-stu-id="6f5ba-105">Method</span></span>|<span data-ttu-id="6f5ba-106">Описание</span><span class="sxs-lookup"><span data-stu-id="6f5ba-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6f5ba-107">Метод Clone</span><span class="sxs-lookup"><span data-stu-id="6f5ba-107">Clone Method</span></span>](icorpublishenum-clone-method.md)|<span data-ttu-id="6f5ba-108">Создает копию этого объекта `ICorPublishEnum`.</span><span class="sxs-lookup"><span data-stu-id="6f5ba-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="6f5ba-109">Метод GetCount</span><span class="sxs-lookup"><span data-stu-id="6f5ba-109">GetCount Method</span></span>](icorpublishenum-getcount-method.md)|<span data-ttu-id="6f5ba-110">Возвращает число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="6f5ba-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="6f5ba-111">Метод Reset</span><span class="sxs-lookup"><span data-stu-id="6f5ba-111">Reset Method</span></span>](icorpublishenum-reset-method.md)|<span data-ttu-id="6f5ba-112">Перемещает курсор в начало перечисления.</span><span class="sxs-lookup"><span data-stu-id="6f5ba-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="6f5ba-113">Метод Skip</span><span class="sxs-lookup"><span data-stu-id="6f5ba-113">Skip Method</span></span>](icorpublishenum-skip-method.md)|<span data-ttu-id="6f5ba-114">Перемещает курсор вперед в перечислении на указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="6f5ba-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f5ba-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="6f5ba-115">Remarks</span></span>  
 <span data-ttu-id="6f5ba-116">Следующие перечислители являются производными от `ICorPublishEnum`:</span><span class="sxs-lookup"><span data-stu-id="6f5ba-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
- [<span data-ttu-id="6f5ba-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="6f5ba-117">ICorPublishAppDomainEnum</span></span>](icorpublishappdomainenum-interface.md)  
  
- [<span data-ttu-id="6f5ba-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="6f5ba-118">ICorPublishProcessEnum</span></span>](icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="6f5ba-119">Требования</span><span class="sxs-lookup"><span data-stu-id="6f5ba-119">Requirements</span></span>  
 <span data-ttu-id="6f5ba-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f5ba-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f5ba-121">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="6f5ba-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6f5ba-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f5ba-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f5ba-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f5ba-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f5ba-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="6f5ba-124">See also</span></span>

- [<span data-ttu-id="6f5ba-125">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="6f5ba-125">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
- [<span data-ttu-id="6f5ba-126">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6f5ba-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
