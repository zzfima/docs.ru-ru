---
title: "Метод ICorDebugExceptionObjectCallStackEnum::Next"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugExceptionObjectCallStackEnum::Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugExceptionObjectCallStackEnum::Next
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 3328a2c0-1e48-4a54-802a-9b474cf82c21
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8a5d17bc46f6c2cab0d0d44f42e7b4741f67dbc4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a><span data-ttu-id="11a8e-102">Метод ICorDebugExceptionObjectCallStackEnum::Next</span><span class="sxs-lookup"><span data-stu-id="11a8e-102">ICorDebugExceptionObjectCallStackEnum::Next Method</span></span>
<span data-ttu-id="11a8e-103">Возвращает заданное число [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) экземпляров, содержащих данные из стека вызовов объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="11a8e-103">Gets the specified number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances that contain information from an exception object's call stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a8e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11a8e-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11a8e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="11a8e-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="11a8e-106">[in] Число [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="11a8e-106">[in] The number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="11a8e-107">[out] Массив указателей, каждый из которых указывает на [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="11a8e-107">[out] An array of pointers, each of which points to a [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="11a8e-108">[out] Указатель на число [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) фактически возвращаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="11a8e-108">[out] A pointer to the number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances actually returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11a8e-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="11a8e-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11a8e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="11a8e-110">Requirements</span></span>  
 <span data-ttu-id="11a8e-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11a8e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11a8e-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11a8e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11a8e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11a8e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11a8e-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11a8e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a8e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="11a8e-115">See Also</span></span>  
 [<span data-ttu-id="11a8e-116">Интерфейс ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="11a8e-116">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
 [<span data-ttu-id="11a8e-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="11a8e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
