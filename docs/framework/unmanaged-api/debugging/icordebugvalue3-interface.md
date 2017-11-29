---
title: "Интерфейс ICorDebugValue3"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue3
helpviewer_keywords: ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3948a4c404036235767f8de6747966709b75bc4c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="fdc73-102">Интерфейс ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="fdc73-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="fdc73-103">Расширяет интерфейсы «ICorDebugValue» и «ICorDebugValue2» для обеспечения поддержки массивов, размер которых превышает 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="fdc73-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fdc73-104">Методы</span><span class="sxs-lookup"><span data-stu-id="fdc73-104">Methods</span></span>  
  
|<span data-ttu-id="fdc73-105">Метод</span><span class="sxs-lookup"><span data-stu-id="fdc73-105">Method</span></span>|<span data-ttu-id="fdc73-106">Описание</span><span class="sxs-lookup"><span data-stu-id="fdc73-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fdc73-107">Метод GetSize64</span><span class="sxs-lookup"><span data-stu-id="fdc73-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="fdc73-108">Возвращает размер в байтах этого `ICorDebugValue3` объекта.</span><span class="sxs-lookup"><span data-stu-id="fdc73-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdc73-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="fdc73-109">Remarks</span></span>  
 <span data-ttu-id="fdc73-110">[ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) метод возвращает размер объекта, в диапазоне от 0 до 2 147 483 647 байт.</span><span class="sxs-lookup"><span data-stu-id="fdc73-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="fdc73-111">В [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], размер массивов может превышать 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="fdc73-111">In the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="fdc73-112">`ICorDebugValue3` Интерфейса позволяет определить размер этих массивов.</span><span class="sxs-lookup"><span data-stu-id="fdc73-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdc73-113">Требования</span><span class="sxs-lookup"><span data-stu-id="fdc73-113">Requirements</span></span>  
 <span data-ttu-id="fdc73-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdc73-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdc73-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fdc73-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fdc73-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fdc73-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdc73-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdc73-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdc73-118">См. также</span><span class="sxs-lookup"><span data-stu-id="fdc73-118">See Also</span></span>  
    
    
 [<span data-ttu-id="fdc73-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="fdc73-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="fdc73-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="fdc73-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
