---
title: Метод ICorDebugHeapValue::IsValid
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue.IsValid
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e1edb1d25a62a9a689c397339740e563d986c8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700233"
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="941a4-102">Метод ICorDebugHeapValue::IsValid</span><span class="sxs-lookup"><span data-stu-id="941a4-102">ICorDebugHeapValue::IsValid Method</span></span>
<span data-ttu-id="941a4-103">Получает значение, указывающее, является ли допустимым объект, представленный этой ICorDebugHeapValue.</span><span class="sxs-lookup"><span data-stu-id="941a4-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="941a4-104">Этот метод был объявлен устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="941a4-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="941a4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="941a4-105">Syntax</span></span>  
  
```  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="941a4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="941a4-106">Parameters</span></span>  
 `pbValid`  
 <span data-ttu-id="941a4-107">[out] Указатель на логическое значение, указывающее, допустим ли это значение в куче.</span><span class="sxs-lookup"><span data-stu-id="941a4-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="941a4-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="941a4-108">Remarks</span></span>  
 <span data-ttu-id="941a4-109">Значение является недопустимым, если удален сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="941a4-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="941a4-110">Этот метод использовать не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="941a4-110">This method has been deprecated.</span></span> <span data-ttu-id="941a4-111">В .NET Framework 2.0, все значения являются действительными до [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) вызывается во время которого значения становятся недействительными.</span><span class="sxs-lookup"><span data-stu-id="941a4-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="941a4-112">Требования</span><span class="sxs-lookup"><span data-stu-id="941a4-112">Requirements</span></span>  
 <span data-ttu-id="941a4-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="941a4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="941a4-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="941a4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="941a4-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="941a4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="941a4-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="941a4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
