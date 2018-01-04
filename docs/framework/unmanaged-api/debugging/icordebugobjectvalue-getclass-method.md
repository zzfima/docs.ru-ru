---
title: "Метод ICorDebugObjectValue::GetClass"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectValue.GetClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectValue::GetClass
helpviewer_keywords:
- ICorDebugObjectValue::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 5be25292-8357-445f-a09b-f997c0de761c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6135dd3806d72b59ce858fab9d0a0b6c3b1f11b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="8fd37-102">Метод ICorDebugObjectValue::GetClass</span><span class="sxs-lookup"><span data-stu-id="8fd37-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="8fd37-103">Возвращает класс значение этого объекта.</span><span class="sxs-lookup"><span data-stu-id="8fd37-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fd37-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8fd37-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8fd37-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8fd37-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="8fd37-106">[out] Указатель на адрес объекта «ICorDebugClass», который представляет класс значение объекта, представленного этим объектом «ICorDebugObjectValue».</span><span class="sxs-lookup"><span data-stu-id="8fd37-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8fd37-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="8fd37-107">Remarks</span></span>  
 <span data-ttu-id="8fd37-108">`GetClass` И [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) методы возвращают сведения о типе значения; они оба заменяемые поддержкой универсальных типов [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="8fd37-108">The `GetClass` and [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fd37-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8fd37-109">Requirements</span></span>  
 <span data-ttu-id="8fd37-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fd37-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fd37-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8fd37-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8fd37-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8fd37-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8fd37-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fd37-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fd37-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8fd37-114">See Also</span></span>  
    
 
