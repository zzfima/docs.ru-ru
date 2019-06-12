---
title: Метод ICorDebugComObjectValue::GetCachedInterfacePointers
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfacePointers
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers
helpviewer_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers method [.NET Framework debugging]
- GetCachedInterfacePointers method, ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 08dbd558-bd39-4263-94c2-71e70687aaf0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a77e7f20aba1908a63d77b4ccada7fabacf55f7
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025848"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="48d58-102">Метод ICorDebugComObjectValue::GetCachedInterfacePointers</span><span class="sxs-lookup"><span data-stu-id="48d58-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>
<span data-ttu-id="48d58-103">Возвращает интерфейс необработанные указатели, кэшируются на текущем вызываемой оболочки времени выполнения (RCW).</span><span class="sxs-lookup"><span data-stu-id="48d58-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48d58-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48d58-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48d58-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="48d58-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="48d58-106">[in] Значение, указывающее, является ли этот метод возвращает только интерфейсы среды выполнения Windows (`IInspectable` интерфейсы) или все интерфейсами COM, кэшируемых вызываемой оболочки времени выполнения (RCW).</span><span class="sxs-lookup"><span data-stu-id="48d58-106">[in] A value that indicates whether the method will return only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="48d58-107">[in] Количество объектов, чьи адреса должны быть получены.</span><span class="sxs-lookup"><span data-stu-id="48d58-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="48d58-108">[out] Указатель на число `CORDB_ADDRESS` значения, фактически возвращенных в `ptrs`.</span><span class="sxs-lookup"><span data-stu-id="48d58-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="48d58-109">Указатель на начальный адрес массива `CORDB_ADDRESS` значений, содержащих адреса кэшированных объектов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="48d58-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48d58-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="48d58-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48d58-111">Требования</span><span class="sxs-lookup"><span data-stu-id="48d58-111">Requirements</span></span>  
 <span data-ttu-id="48d58-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48d58-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48d58-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48d58-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48d58-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48d58-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48d58-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48d58-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48d58-116">См. также</span><span class="sxs-lookup"><span data-stu-id="48d58-116">See also</span></span>

- [<span data-ttu-id="48d58-117">Интерфейс ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="48d58-117">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="48d58-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="48d58-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
