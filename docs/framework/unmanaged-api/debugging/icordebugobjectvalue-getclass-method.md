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
ms.openlocfilehash: 0d403fe24f368a5cd05358cd589023a4c8710a37
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587428"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="7d64f-102">Метод ICorDebugObjectValue::GetClass</span><span class="sxs-lookup"><span data-stu-id="7d64f-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="7d64f-103">Возвращает класс значение этого объекта.</span><span class="sxs-lookup"><span data-stu-id="7d64f-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d64f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d64f-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7d64f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7d64f-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="7d64f-106">[out] Указатель на адрес объекта «ICorDebugClass», который представляет класс объекта значение объекта, представленный этим объектом «ICorDebugObjectValue».</span><span class="sxs-lookup"><span data-stu-id="7d64f-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d64f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="7d64f-107">Remarks</span></span>  
 <span data-ttu-id="7d64f-108">`GetClass` И [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) методы возвращают сведения о типе значения; они оба заменяемые поддержкой универсальных типов [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="7d64f-108">The `GetClass` and [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d64f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7d64f-109">Requirements</span></span>  
 <span data-ttu-id="7d64f-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d64f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d64f-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d64f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d64f-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d64f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d64f-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d64f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d64f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7d64f-114">See also</span></span>


