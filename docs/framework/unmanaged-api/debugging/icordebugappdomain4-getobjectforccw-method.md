---
title: Метод ICorDebugAppDomain4::GetObjectForCCW
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1089668aa19747f5f694360ebb87098e2df9ad4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="d9155-102">Метод ICorDebugAppDomain4::GetObjectForCCW</span><span class="sxs-lookup"><span data-stu-id="d9155-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="d9155-103">Возвращает управляемый объект из вызываемой оболочки COMr (CCW).</span><span class="sxs-lookup"><span data-stu-id="d9155-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9155-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9155-104">Syntax</span></span>  
  
```  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9155-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d9155-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="d9155-106">[in] Указатель вызываемой оболочки COM (CCW).</span><span class="sxs-lookup"><span data-stu-id="d9155-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="d9155-107">[out] Указатель на адрес объекта «ICorDebugValue», который представляет управляемый объект, соответствующий данной указатель вызываемой оболочки COM.</span><span class="sxs-lookup"><span data-stu-id="d9155-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9155-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="d9155-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9155-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d9155-109">Requirements</span></span>  
 <span data-ttu-id="d9155-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9155-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9155-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9155-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9155-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9155-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9155-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9155-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9155-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d9155-114">See Also</span></span>  
 [<span data-ttu-id="d9155-115">Интерфейс ICorDebugAppDomain4</span><span class="sxs-lookup"><span data-stu-id="d9155-115">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 [<span data-ttu-id="d9155-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d9155-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
