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
ms.openlocfilehash: 95532d6721467b482b1d79d611f8055b606bb4a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413512"
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="e2e4d-102">Метод ICorDebugHeapValue::IsValid</span><span class="sxs-lookup"><span data-stu-id="e2e4d-102">ICorDebugHeapValue::IsValid Method</span></span>
<span data-ttu-id="e2e4d-103">Возвращает значение, указывающее, допустим ли объект, представленный в этом ICorDebugHeapValue.</span><span class="sxs-lookup"><span data-stu-id="e2e4d-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="e2e4d-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="e2e4d-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2e4d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2e4d-105">Syntax</span></span>  
  
```  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2e4d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e2e4d-106">Parameters</span></span>  
 `pbValid`  
 <span data-ttu-id="e2e4d-107">[out] Указатель на значение Boolean, указывающее, допустим ли это значение в куче.</span><span class="sxs-lookup"><span data-stu-id="e2e4d-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2e4d-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="e2e4d-108">Remarks</span></span>  
 <span data-ttu-id="e2e4d-109">Значение является недопустимым, если удален сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="e2e4d-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="e2e4d-110">Этот метод использовать не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="e2e4d-110">This method has been deprecated.</span></span> <span data-ttu-id="e2e4d-111">В .NET Framework 2.0 все значения являются допустимыми до [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) вызывается во время которого значения становятся недействительными.</span><span class="sxs-lookup"><span data-stu-id="e2e4d-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2e4d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e2e4d-112">Requirements</span></span>  
 <span data-ttu-id="e2e4d-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2e4d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2e4d-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2e4d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2e4d-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2e4d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2e4d-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2e4d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
