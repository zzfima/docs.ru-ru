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
ms.openlocfilehash: c1e2b557a5e5794c50986b1af8ec39faba845cc9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125515"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="2ef20-102">Метод ICorDebugComObjectValue::GetCachedInterfacePointers</span><span class="sxs-lookup"><span data-stu-id="2ef20-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>
<span data-ttu-id="2ef20-103">Возвращает необработанные указатели интерфейса, кэшированные в текущей вызываемой оболочке времени выполнения (RCW).</span><span class="sxs-lookup"><span data-stu-id="2ef20-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ef20-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ef20-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ef20-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2ef20-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="2ef20-106">окне Значение, указывающее, будет ли метод возвращать только среда выполнения Windows интерфейсы (интерфейсы`IInspectable`) или все COM-интерфейсы, которые кэшируются вызываемой оболочкой времени выполнения (RCW).</span><span class="sxs-lookup"><span data-stu-id="2ef20-106">[in] A value that indicates whether the method will return only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="2ef20-107">окне Число объектов, адреса которых необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="2ef20-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="2ef20-108">заполняет Указатель на число значений `CORDB_ADDRESS`, фактически возвращаемых в `ptrs`.</span><span class="sxs-lookup"><span data-stu-id="2ef20-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="2ef20-109">Указатель на начальный адрес массива `CORDB_ADDRESS` значений, содержащих адреса кэшированных объектов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2ef20-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ef20-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="2ef20-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ef20-111">Требования</span><span class="sxs-lookup"><span data-stu-id="2ef20-111">Requirements</span></span>  
 <span data-ttu-id="2ef20-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ef20-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ef20-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ef20-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ef20-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ef20-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ef20-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ef20-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ef20-116">См. также</span><span class="sxs-lookup"><span data-stu-id="2ef20-116">See also</span></span>

- [<span data-ttu-id="2ef20-117">Интерфейс ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="2ef20-117">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="2ef20-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2ef20-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
