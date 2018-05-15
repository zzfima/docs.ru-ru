---
title: Интерфейс ICorPublishProcessEnum
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum
helpviewer_keywords:
- ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd71a2bd4a52da8fa77592363e2eb7c8f5101fd3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="15592-102">Интерфейс ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="15592-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="15592-103">Подкласс [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) интерфейс, предоставляющий методы для обхода коллекцию [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) объектов.</span><span class="sxs-lookup"><span data-stu-id="15592-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="15592-104">Методы</span><span class="sxs-lookup"><span data-stu-id="15592-104">Methods</span></span>  
  
|<span data-ttu-id="15592-105">Метод</span><span class="sxs-lookup"><span data-stu-id="15592-105">Method</span></span>|<span data-ttu-id="15592-106">Описание</span><span class="sxs-lookup"><span data-stu-id="15592-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="15592-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="15592-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|<span data-ttu-id="15592-108">Возвращает заданное число `ICorPublishProcess` экземпляров из коллекции, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="15592-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15592-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="15592-109">Remarks</span></span>  
 <span data-ttu-id="15592-110">`ICorPublishProcessEnum` Интерфейс реализует методы интерфейса абстрактным, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="15592-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="15592-111">`ICorPublishProcessEnum` Создан экземпляр [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="15592-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="15592-112">Обход коллекции `ICorPublishProcess` объектов зависит от условия фильтрации, предоставленных во время `ICorPublishProcessEnum` был создан экземпляр.</span><span class="sxs-lookup"><span data-stu-id="15592-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15592-113">Требования</span><span class="sxs-lookup"><span data-stu-id="15592-113">Requirements</span></span>  
 <span data-ttu-id="15592-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15592-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15592-115">**Заголовок:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="15592-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="15592-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15592-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15592-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15592-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15592-118">См. также</span><span class="sxs-lookup"><span data-stu-id="15592-118">See Also</span></span>  
 [<span data-ttu-id="15592-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="15592-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="15592-120">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="15592-120">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
