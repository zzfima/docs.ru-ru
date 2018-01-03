---
title: "Метод ICorDebugAppDomain4::GetObjectForCCW"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d459c9ea807114c4f63995ba8fbbb288ea5463b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="aeffd-102">Метод ICorDebugAppDomain4::GetObjectForCCW</span><span class="sxs-lookup"><span data-stu-id="aeffd-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="aeffd-103">Возвращает управляемый объект из вызываемой оболочки COM (CCW).</span><span class="sxs-lookup"><span data-stu-id="aeffd-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aeffd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aeffd-104">Syntax</span></span>  
  
```  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aeffd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="aeffd-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="aeffd-106">[in] Указатель вызываемой оболочки COM (CCW).</span><span class="sxs-lookup"><span data-stu-id="aeffd-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="aeffd-107">[out] Указатель на адрес объекта «ICorDebugValue», который представляет управляемый объект, соответствующий данной указатель вызываемой оболочки COM.</span><span class="sxs-lookup"><span data-stu-id="aeffd-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aeffd-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="aeffd-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aeffd-109">Требования</span><span class="sxs-lookup"><span data-stu-id="aeffd-109">Requirements</span></span>  
 <span data-ttu-id="aeffd-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aeffd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aeffd-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aeffd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aeffd-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aeffd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aeffd-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aeffd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aeffd-114">См. также</span><span class="sxs-lookup"><span data-stu-id="aeffd-114">See Also</span></span>  
 [<span data-ttu-id="aeffd-115">Интерфейс ICorDebugAppDomain4</span><span class="sxs-lookup"><span data-stu-id="aeffd-115">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 [<span data-ttu-id="aeffd-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="aeffd-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
