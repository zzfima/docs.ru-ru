---
title: Метод ICorDebugValue2::GetExactType
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 982af81f8f3886ae26b56114cc36374279c07593
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656353"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="d4686-102">Метод ICorDebugValue2::GetExactType</span><span class="sxs-lookup"><span data-stu-id="d4686-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="d4686-103">Получает указатель интерфейса на объект «ICorDebugType», который представляет <xref:System.Type> этого значения.</span><span class="sxs-lookup"><span data-stu-id="d4686-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4686-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4686-104">Syntax</span></span>  
  
```  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4686-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d4686-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="d4686-106">[out] Указатель на адрес `ICorDebugType` , представляющий <xref:System.Type> значения, представленный этим объектом «ICorDebugValue2».</span><span class="sxs-lookup"><span data-stu-id="d4686-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4686-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="d4686-107">Remarks</span></span>  
 <span data-ttu-id="d4686-108">Универсальные шаблоны с поддержкой `GetExactType` метод заменяет оба [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) и [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) методов, каждый из которых возвращают сведения о типе значения .</span><span class="sxs-lookup"><span data-stu-id="d4686-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4686-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d4686-109">Requirements</span></span>  
 <span data-ttu-id="d4686-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4686-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4686-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4686-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4686-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4686-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4686-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4686-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4686-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d4686-114">See also</span></span>

