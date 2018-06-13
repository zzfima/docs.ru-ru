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
ms.openlocfilehash: ef6fb76ca25a1255393b66c52d82cb94df2b48b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411906"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="48a84-102">Метод ICorDebugComObjectValue::GetCachedInterfacePointers</span><span class="sxs-lookup"><span data-stu-id="48a84-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>
<span data-ttu-id="48a84-103">Возвращает интерфейс необработанные указатели, кэшируются на текущем вызываемой оболочки времени выполнения (RCW).</span><span class="sxs-lookup"><span data-stu-id="48a84-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48a84-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48a84-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="48a84-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="48a84-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="48a84-106">[in] Значение, указывающее, является ли метод будет возвращать только [!INCLUDE[wrt](../../../../includes/wrt-md.md)] интерфейсы (`IInspectable` интерфейсы) или все COM-интерфейсы, кэшируемых вызываемой оболочки времени выполнения (RCW).</span><span class="sxs-lookup"><span data-stu-id="48a84-106">[in] A value that indicates whether the method will return only [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="48a84-107">[in] Количество объектов, чьи адреса должны быть получены.</span><span class="sxs-lookup"><span data-stu-id="48a84-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="48a84-108">[out] Указатель на число `CORDB_ADDRESS` значения, фактически извлеченных в `ptrs`.</span><span class="sxs-lookup"><span data-stu-id="48a84-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="48a84-109">Указатель на начальный адрес массива `CORDB_ADDRESS` значений, содержащих адреса кэшированных объектов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="48a84-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48a84-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="48a84-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48a84-111">Требования</span><span class="sxs-lookup"><span data-stu-id="48a84-111">Requirements</span></span>  
 <span data-ttu-id="48a84-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48a84-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48a84-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48a84-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48a84-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48a84-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48a84-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48a84-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48a84-116">См. также</span><span class="sxs-lookup"><span data-stu-id="48a84-116">See Also</span></span>  
 [<span data-ttu-id="48a84-117">Интерфейс ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="48a84-117">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 [<span data-ttu-id="48a84-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="48a84-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
