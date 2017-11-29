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
ms.openlocfilehash: dee9f110647230e54df527959651dc5b2fb73b3f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="a20e2-102">Метод ICorDebugObjectValue::GetClass</span><span class="sxs-lookup"><span data-stu-id="a20e2-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="a20e2-103">Возвращает класс значение этого объекта.</span><span class="sxs-lookup"><span data-stu-id="a20e2-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a20e2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a20e2-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a20e2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a20e2-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="a20e2-106">[out] Указатель на адрес объекта «ICorDebugClass», который представляет класс значение объекта, представленного этим объектом «ICorDebugObjectValue».</span><span class="sxs-lookup"><span data-stu-id="a20e2-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a20e2-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="a20e2-107">Remarks</span></span>  
 <span data-ttu-id="a20e2-108">`GetClass` И [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) методы возвращают сведения о типе значения; они оба заменяемые поддержкой универсальных типов [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="a20e2-108">The `GetClass` and [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a20e2-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a20e2-109">Requirements</span></span>  
 <span data-ttu-id="a20e2-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a20e2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a20e2-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a20e2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a20e2-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a20e2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a20e2-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a20e2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a20e2-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a20e2-114">See Also</span></span>  
    
 
