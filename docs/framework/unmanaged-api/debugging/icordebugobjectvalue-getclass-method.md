---
title: Метод ICorDebugObjectValue::GetClass
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetClass
helpviewer_keywords:
- ICorDebugObjectValue::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 5be25292-8357-445f-a09b-f997c0de761c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a20ab7a7ecb5d01351d0c912e08955f44b26d5f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756999"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="56f2b-102">Метод ICorDebugObjectValue::GetClass</span><span class="sxs-lookup"><span data-stu-id="56f2b-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="56f2b-103">Возвращает класс значение этого объекта.</span><span class="sxs-lookup"><span data-stu-id="56f2b-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56f2b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56f2b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56f2b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="56f2b-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="56f2b-106">[out] Указатель на адрес объекта «ICorDebugClass», который представляет класс объекта значение объекта, представленный этим объектом «ICorDebugObjectValue».</span><span class="sxs-lookup"><span data-stu-id="56f2b-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56f2b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="56f2b-107">Remarks</span></span>  
 <span data-ttu-id="56f2b-108">`GetClass` И [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) методы возвращают сведения о типе значения; они оба заменяемые поддержкой универсальных типов [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="56f2b-108">The `GetClass` and [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56f2b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="56f2b-109">Requirements</span></span>  
 <span data-ttu-id="56f2b-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56f2b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56f2b-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56f2b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56f2b-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56f2b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56f2b-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56f2b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56f2b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="56f2b-114">See also</span></span>
