---
title: Метод ICorDebugExceptionObjectCallStackEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum::Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 3328a2c0-1e48-4a54-802a-9b474cf82c21
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c33f76b5eaa87c0b69497547732564921f662d5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099473"
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a><span data-ttu-id="b3c38-102">Метод ICorDebugExceptionObjectCallStackEnum::Next</span><span class="sxs-lookup"><span data-stu-id="b3c38-102">ICorDebugExceptionObjectCallStackEnum::Next Method</span></span>
<span data-ttu-id="b3c38-103">Возвращает заданное число [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) экземпляров, которые содержат сведения из стека вызовов объект исключения.</span><span class="sxs-lookup"><span data-stu-id="b3c38-103">Gets the specified number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances that contain information from an exception object's call stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3c38-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3c38-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3c38-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b3c38-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="b3c38-106">[in] Число [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="b3c38-106">[in] The number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="b3c38-107">[out] Массив указателей, каждый из которых указывает [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="b3c38-107">[out] An array of pointers, each of which points to a [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="b3c38-108">[out] Указатель на число [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="b3c38-108">[out] A pointer to the number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances actually returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3c38-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="b3c38-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3c38-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b3c38-110">Requirements</span></span>  
 <span data-ttu-id="b3c38-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3c38-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3c38-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b3c38-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3c38-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3c38-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b3c38-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b3c38-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b3c38-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b3c38-115">See also</span></span>

- [<span data-ttu-id="b3c38-116">Интерфейс ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="b3c38-116">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)
- [<span data-ttu-id="b3c38-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b3c38-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
