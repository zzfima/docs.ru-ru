---
title: "Метод ICorDebugValue::GetType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2a79ef332361fdaa3a23cc4e13daa8b4a8303d2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="8389c-102">Метод ICorDebugValue::GetType</span><span class="sxs-lookup"><span data-stu-id="8389c-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="8389c-103">Возвращает тип-примитив объекта «ICorDebugValue».</span><span class="sxs-lookup"><span data-stu-id="8389c-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8389c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8389c-104">Syntax</span></span>  
  
```  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8389c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8389c-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="8389c-106">[out] Указатель на значение перечисления «CorElementType», которое указывает тип значения.</span><span class="sxs-lookup"><span data-stu-id="8389c-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8389c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="8389c-107">Remarks</span></span>  
 <span data-ttu-id="8389c-108">Если объект сложного типа во время выполнения, этот тип можно проанализировать с помощью соответствующих подклассов `ICorDebugValue` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8389c-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="8389c-109">Например, «ICorDebugObjectValue», который наследуется от `ICorDebugValue`, представляет сложный тип.</span><span class="sxs-lookup"><span data-stu-id="8389c-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="8389c-110">`GetType` И [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) методы возвращают сведения о типе значения.</span><span class="sxs-lookup"><span data-stu-id="8389c-110">The `GetType` and [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="8389c-111">Они оба заменяемые поддержкой универсальных типов [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="8389c-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8389c-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8389c-112">Requirements</span></span>  
 <span data-ttu-id="8389c-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8389c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8389c-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8389c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8389c-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8389c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8389c-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8389c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8389c-117">См. также</span><span class="sxs-lookup"><span data-stu-id="8389c-117">See Also</span></span>  
 
