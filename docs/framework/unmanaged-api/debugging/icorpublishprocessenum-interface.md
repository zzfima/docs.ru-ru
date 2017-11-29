---
title: "Интерфейс ICorPublishProcessEnum"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcessEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcessEnum
helpviewer_keywords: ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 66e31911289d1ef8b590a0b7e7896adfa4998adc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="de5f9-102">Интерфейс ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="de5f9-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="de5f9-103">Подкласс [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) интерфейс, предоставляющий методы для обхода коллекцию [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) объектов.</span><span class="sxs-lookup"><span data-stu-id="de5f9-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de5f9-104">Методы</span><span class="sxs-lookup"><span data-stu-id="de5f9-104">Methods</span></span>  
  
|<span data-ttu-id="de5f9-105">Метод</span><span class="sxs-lookup"><span data-stu-id="de5f9-105">Method</span></span>|<span data-ttu-id="de5f9-106">Описание</span><span class="sxs-lookup"><span data-stu-id="de5f9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de5f9-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="de5f9-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|<span data-ttu-id="de5f9-108">Возвращает заданное число `ICorPublishProcess` экземпляров из коллекции, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="de5f9-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de5f9-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="de5f9-109">Remarks</span></span>  
 <span data-ttu-id="de5f9-110">`ICorPublishProcessEnum` Интерфейс реализует методы интерфейса абстрактным, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="de5f9-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="de5f9-111">`ICorPublishProcessEnum` Создан экземпляр [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="de5f9-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="de5f9-112">Обход коллекции `ICorPublishProcess` объектов зависит от условия фильтрации, предоставленных во время `ICorPublishProcessEnum` был создан экземпляр.</span><span class="sxs-lookup"><span data-stu-id="de5f9-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de5f9-113">Требования</span><span class="sxs-lookup"><span data-stu-id="de5f9-113">Requirements</span></span>  
 <span data-ttu-id="de5f9-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de5f9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de5f9-115">**Заголовок:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="de5f9-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="de5f9-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de5f9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de5f9-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de5f9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de5f9-118">См. также</span><span class="sxs-lookup"><span data-stu-id="de5f9-118">See Also</span></span>  
 [<span data-ttu-id="de5f9-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="de5f9-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="de5f9-120">Компонентный класс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="de5f9-120">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
