---
title: Метод ICorDebugAppDomain4::GetObjectForCCW
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: 8b046eb5926bb9aa4738e8fff8e61b0b7c23a3aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088832"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="de65a-102">Метод ICorDebugAppDomain4::GetObjectForCCW</span><span class="sxs-lookup"><span data-stu-id="de65a-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="de65a-103">Возвращает управляемый объект из вызываемой оболочки COMr (CCW).</span><span class="sxs-lookup"><span data-stu-id="de65a-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de65a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="de65a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de65a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="de65a-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="de65a-106">[in] Указатель вызываемой оболочки COM (CCW).</span><span class="sxs-lookup"><span data-stu-id="de65a-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="de65a-107">заполняет Указатель на адрес объекта ICorDebugValue, который представляет управляемый объект, соответствующий заданному указателю CCW.</span><span class="sxs-lookup"><span data-stu-id="de65a-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de65a-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="de65a-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de65a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="de65a-109">Requirements</span></span>  
 <span data-ttu-id="de65a-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de65a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de65a-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de65a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de65a-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de65a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de65a-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de65a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de65a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="de65a-114">See also</span></span>

- [<span data-ttu-id="de65a-115">Интерфейс ICorDebugAppDomain4</span><span class="sxs-lookup"><span data-stu-id="de65a-115">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)
- [<span data-ttu-id="de65a-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="de65a-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
