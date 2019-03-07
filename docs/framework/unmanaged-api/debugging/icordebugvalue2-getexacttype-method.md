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
ms.openlocfilehash: 03d701d0801c55b6e91600f0767a6d737e4915c3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479952"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="08669-102">Метод ICorDebugValue2::GetExactType</span><span class="sxs-lookup"><span data-stu-id="08669-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="08669-103">Получает указатель интерфейса на объект «ICorDebugType», который представляет <xref:System.Type> этого значения.</span><span class="sxs-lookup"><span data-stu-id="08669-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08669-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08669-104">Syntax</span></span>  
  
```  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08669-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="08669-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="08669-106">[out] Указатель на адрес `ICorDebugType` , представляющий <xref:System.Type> значения, представленный этим объектом «ICorDebugValue2».</span><span class="sxs-lookup"><span data-stu-id="08669-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08669-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="08669-107">Remarks</span></span>  
 <span data-ttu-id="08669-108">Универсальные шаблоны с поддержкой `GetExactType` метод заменяет оба [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) и [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) методов, каждый из которых возвращают сведения о типе значения .</span><span class="sxs-lookup"><span data-stu-id="08669-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08669-109">Требования</span><span class="sxs-lookup"><span data-stu-id="08669-109">Requirements</span></span>  
 <span data-ttu-id="08669-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08669-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08669-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08669-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08669-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08669-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08669-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08669-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08669-114">См. также</span><span class="sxs-lookup"><span data-stu-id="08669-114">See also</span></span>

