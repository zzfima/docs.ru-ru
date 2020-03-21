---
title: Метод ICorDebugAppDomain4::GetObjectForCCW
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: 10d32314e46aba4f030b294cadc3cbb36e8742f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179052"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="caf3e-102">Метод ICorDebugAppDomain4::GetObjectForCCW</span><span class="sxs-lookup"><span data-stu-id="caf3e-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="caf3e-103">Возвращает управляемый объект из вызываемой оболочки COMr (CCW).</span><span class="sxs-lookup"><span data-stu-id="caf3e-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caf3e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="caf3e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="caf3e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="caf3e-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="caf3e-106">[in] Указатель вызываемой оболочки COM (CCW).</span><span class="sxs-lookup"><span data-stu-id="caf3e-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="caf3e-107">(ваут) Указатель на адрес объекта "ICorDebugValue", представляющего управляемый объект, соответствующий данному указателю CCW.</span><span class="sxs-lookup"><span data-stu-id="caf3e-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="caf3e-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="caf3e-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caf3e-109">Требования</span><span class="sxs-lookup"><span data-stu-id="caf3e-109">Requirements</span></span>  
 <span data-ttu-id="caf3e-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="caf3e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caf3e-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="caf3e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="caf3e-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="caf3e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="caf3e-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caf3e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caf3e-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="caf3e-114">See also</span></span>

- [<span data-ttu-id="caf3e-115">Интерфейс ICorDebugAppDomain4</span><span class="sxs-lookup"><span data-stu-id="caf3e-115">ICorDebugAppDomain4 Interface</span></span>](icordebugappdomain4-interface.md)
- [<span data-ttu-id="caf3e-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="caf3e-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
